

---

# SaaS 订阅与计费产品手册（Product & Engineering）

## 1. 设计目标

* 支持 **多租户（Tenant）** 的 SaaS 订阅计费
* 套餐固定：Starter / Pro / Business
* 支付周期仅支持：**月付 / 年付**
* 支持试用、升级
* **不支持降级**
* **不支持用户自行取消（仅客服）**

---

## 2. 核心业务对象

### 2.1 租户（Tenant）

* **计费主体**
* 一个租户在同一时间 **仅允许存在一个有效订阅**

你提供的表作为 **核心主表**： 已经存在不用改

```sql
CREATE TABLE `crm_tenant` (
  `id` int NOT NULL AUTO_INCREMENT COMMENT 'Tenant ID',
  `name` varchar(255) NOT NULL COMMENT 'Organization/Company Name',
  `slug` varchar(100) DEFAULT NULL COMMENT 'Tenant Identifier (unique)',
  `email` varchar(255) DEFAULT NULL COMMENT 'Contact Email',
  `phone` varchar(50) DEFAULT NULL COMMENT 'Contact Phone',
  `address` text COMMENT 'Address',
  `tax_number` varchar(100) DEFAULT NULL COMMENT 'Tax ID Number',
  `status` tinyint NOT NULL DEFAULT '1' COMMENT 'Status: 1=active, 0=suspended',
  `owner_id` int DEFAULT NULL COMMENT 'Primary Admin User ID',
  `created_at`  int NOT NULL,
  `updated_at`  int NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_tenant_slug` (`slug`)
) COMMENT='Tenant/Organization Table';
```

---

## 3. 套餐与周期定义

### 3.1 套餐定义（逻辑层）

| plan     | name     |
| -------- | -------- |
| starter  | Starter  |
| pro      | Pro      |
| business | Business |

规则：

* 套餐等级：starter < pro < business
* 仅允许向上升级

---

### 3.2 付费周期

| code    | 说明 |
| ------- | -- |
| monthly | 月付 |
| yearly  | 年付 |

---

## 4. 订阅状态模型

| 状态       | 说明       |
| -------- | -------- |
| trialing | 试用中      |
| active   | 已激活      |
| expired  | 已到期      |
| canceled | 已取消（仅客服） |

---

## 5. 升级与计费规则

### 5.1 升级原则

* 任意时间可升级
* 升级后：

  * 权限立即生效
  * **到期时间不变**
* 不允许降级

---

### 5.2 差价补扣公式（Proration）

```text
upgrade_amount =
(new_plan_price - current_plan_price)
× (remaining_days / total_days)
```

---

## 6. 取消规则

* ❌ 用户端不提供取消入口
* ✔️ 仅客服 / Admin 可操作
* 是否退款由人工判断

---

# 数据库表结构设计（核心）

---

## 7. 套餐价格表（crm_plan）

```sql
CREATE TABLE `crm_plan` (
  `id` int NOT NULL AUTO_INCREMENT,
  `plan` varchar(50) NOT NULL COMMENT 'starter / pro / business',
  `name` varchar(100) NOT NULL,
  `monthly_price` decimal(10,2) NOT NULL COMMENT 'Monthly price',
  `yearly_price` decimal(10,2) NOT NULL COMMENT 'Yearly price',
  `level` int NOT NULL COMMENT 'Plan level, higher = more advanced',
  `status` tinyint NOT NULL DEFAULT 1 COMMENT '1=active,0=disabled',
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_plan_code` (`code`)
) COMMENT='Subscription Plans';
```

---

## 8. 租户订阅表（crm_subscription）

```sql
CREATE TABLE `crm_subscription` (
  `id` int NOT NULL AUTO_INCREMENT,
  `tenant_id` int NOT NULL COMMENT 'Tenant ID',
  `plan_code` varchar(50) NOT NULL,
  `billing_cycle` varchar(20) NOT NULL COMMENT 'monthly/yearly',
  `status` varchar(20) NOT NULL COMMENT 'trialing/active/expired/canceled',
  `started_at`  int NOT NULL,
  `ended_at`  int NOT NULL COMMENT 'Subscription expiration time',
  `trial_ends_at` int NOT NULL,
  `created_at`  int NOT NULL,
  `updated_at`  int NOT NULL,
  PRIMARY KEY (`id`),
  KEY `idx_sub_tenant` (`tenant_id`),
  CONSTRAINT `fk_sub_tenant`
    FOREIGN KEY (`tenant_id`) REFERENCES `crm_tenant` (`id`)
) COMMENT='Tenant Subscription';
```

**关键约束（逻辑层）：**

* 一个 tenant 同一时间仅允许 1 条 `status in (trialing, active)` 的订阅

---

## 9. 订单表（crm_order）

```sql
CREATE TABLE `crm_order` (
  `id` int NOT NULL AUTO_INCREMENT,
  `tenant_id` int NOT NULL,
  `subscription_id` int DEFAULT NULL,
  `order_no` varchar(64) NOT NULL COMMENT 'Unique order number',
  `order_type` varchar(20) NOT NULL COMMENT 'new/renew/upgrade',
  `amount` decimal(10,2) NOT NULL COMMENT 'Order amount',
  `currency` varchar(10) NOT NULL DEFAULT 'CNY',
  `status` varchar(20) NOT NULL COMMENT 'pending/paid/failed/refunded',
  `created_at`  int NOT NULL,
  `paid_at`  int NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `uk_order_no` (`order_no`),
  KEY `idx_order_tenant` (`tenant_id`)
) COMMENT='订阅订单 Orders';
```

---

## 10. 支付记录表（crm_payment）

```sql
CREATE TABLE `crm_payment` (
  `id` int NOT NULL AUTO_INCREMENT,
  `order_id` int NOT NULL,
  `payment_method` varchar(50) NOT NULL COMMENT 'alipay/wechat/stripe',
  `transaction_no` varchar(100) DEFAULT NULL COMMENT 'Gateway transaction ID',
  `amount` decimal(10,2) NOT NULL,
  `status` varchar(20) NOT NULL COMMENT 'success/failed',
  `paid_at`  int NOT NULL,
  PRIMARY KEY (`id`),
  KEY `idx_payment_order` (`order_id`),
  CONSTRAINT `fk_payment_order`
    FOREIGN KEY (`order_id`) REFERENCES `crm_order` (`id`)
) COMMENT='订单支付 Records';
```

---

## 11. 升级记录表（crm_subscription_upgrade）

```sql
CREATE TABLE `crm_subscription_upgrade` (
  `id` int NOT NULL AUTO_INCREMENT,
  `subscription_id` int NOT NULL,
  `from_plan` varchar(50) NOT NULL,
  `to_plan` varchar(50) NOT NULL,
  `upgrade_amount` decimal(10,2) NOT NULL,
  `created_at`  int NOT NULL,
  PRIMARY KEY (`id`),
  KEY `idx_upgrade_sub` (`subscription_id`)
) COMMENT='Subscription Upgrade History';
```

---

## 12. 推荐状态流转（研发参考）

```text
trialing → active → expired
               ↘
              canceled（客服）
```

---

## 13. 核心设计原则（必须遵守）

* 订阅主体 = tenant
* 权限判断基于 **crm_subscription.plan_code**
* 升级：

  * 永远补差价
  * 永远不延长时间
* 不允许：

  * 降级
  * 用户自行取消

---
