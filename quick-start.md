---
layout: default
title: Quick Start Guide
nav_order: 2
description: "Get up and running with TinyCRM in 5 minutes"
permalink: /quick-start/
---

# Quick Start Guide

Welcome to TinyCRM! This guide will help you get started in just 5 minutes.

## 🎯 What You'll Learn

- How to log in and navigate the system
- How to claim a lead from the Lead Pool
- How to convert a lead to a customer
- How to create your first invoice

---

## Step 1: Login

1. Navigate to the TinyCRM login page at [https://www.tinycrmgo.com](https://www.tinycrmgo.com)
2. Enter your **email** and **password**
3. Click **Login**

> 💡 **Tip**: If you forgot your password, use the "Forgot Password" link to reset it.

---

## Step 2: Explore the Dashboard

After logging in, you'll see the **Dashboard** with key statistics:

```
┌─────────────────────────────────────────┐
│  Dashboard Overview                     │
├─────────────────────────────────────────┤
│  📊 Lead Pool: 150                      │
│  👤 My Leads: 12                        │
│  🏢 Customers: 45                       │
│  💰 Revenue: $125,000                   │
└─────────────────────────────────────────┘
```

The dashboard shows:
- **Lead Pool**: Available public leads
- **My Leads**: Leads assigned to you
- **Customers**: Your converted customers
- **Revenue**: Total revenue from invoices

---

## Step 3: Claim a Lead from Lead Pool

### Lead Flow Diagram

```
Lead Flow:
┌──────────┐    Claim    ┌──────────┐
│Lead Pool │ ──────────► │My Leads  │
└──────────┘              └────┬─────┘
                                │ Convert
                                ▼
                           ┌──────────┐
                           │Customers │
                           └────┬─────┘
                                │ Create Invoice
                                ▼
                           ┌──────────┐
                           │ Invoice  │
                           └──────────┘
```

### Steps:

1. Navigate to **CRM → Lead Pool**
2. Browse available leads
3. Click **Claim** on a lead you want to work with
4. The lead moves to **My Leads**

> ✅ **Success**: The lead is now assigned to you and appears in "My Leads"

---

## Step 4: Convert Lead to Customer

1. Go to **CRM → My Leads**
2. Open a lead you want to convert
3. Click **Convert to Customer**
4. Select a **Customer Level** (1-5)
5. Click **Save**

> 💡 **Note**: Customer levels help you categorize customers by importance or relationship stage.

### Customer Levels

| Level | Description |
|-------|-------------|
| 1 | New Customer |
| 2 | Regular Customer |
| 3 | Important Customer |
| 4 | VIP Customer |
| 5 | Strategic Partner |

---

## Step 5: Create Your First Invoice

1. Navigate to **Sales → Invoices**
2. Click **Create Invoice**
3. Select a **Customer** from the dropdown
4. Add **Products**:
   - Click **Add Product**
   - Select product, quantity, and price
   - Repeat for multiple products
5. (Optional) Add **Discount** or **Fees**
6. Review the **Total Amount**
7. Click **Save**

### Invoice Creation Flow

```
Invoice Creation Steps:
┌──────────────┐
│Select Customer│
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Add Products │
└──────┬───────┘
       │
       ▼
┌──────────────────┐
│Apply Discount/Fees│
└──────┬───────────┘
       │
       ▼
┌──────────────┐
│ Review Total │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Save Invoice │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Send/Export  │
└──────────────┘
```

---

## 🎓 Next Steps

Now that you've completed the basics:

1. **Explore More Features**:
   - Read the [User Guide](user-guide.md) for detailed instructions
   - Learn about [Product Management](user-guide.md#product-management)
   - Understand [Invoice Features](user-guide.md#invoice-management)

2. **For Administrators**:
   - Check the [Administrator Guide](admin-guide.md)
   - Learn about [User Management](admin-guide.md#user-management)
   - Review [Subscription Settings](admin-guide.md#subscription-management)

3. **Common Questions**:
   - Visit the [FAQ](faq.md) for answers to common questions

---

## ⚡ Quick Reference

| Action | Location |
|--------|----------|
| View Dashboard | Dashboard (Home) |
| Claim Lead | CRM → Lead Pool → Claim |
| View My Leads | CRM → My Leads |
| Convert to Customer | My Leads → View → Convert |
| Create Invoice | Sales → Invoices → Create |
| Manage Products | Sales → Products |
| View Profile | User Menu → Profile |

---

## 🆘 Need Help?

- **Detailed Instructions**: See [User Guide](user-guide.md)
- **Troubleshooting**: Check [FAQ](faq.md)
- **Admin Functions**: Read [Administrator Guide](admin-guide.md)
- **Contact Support**: Email us at **contact@tinycrmgo.com**

---

*Happy CRM-ing! 🚀*
