---
layout: default
title: Home
nav_order: 1
description: "Welcome to TinyCRM Documentation"
permalink: /
---

# TinyCRM Documentation

Welcome to the TinyCRM documentation! This comprehensive guide will help you understand and use all features of the TinyCRM system.

**Website**: [https://www.tinycrmgo.com](https://www.tinycrmgo.com)

## 📚 Documentation Structure

### [Quick Start Guide](quick-start.md)
Get up and running with TinyCRM in 5 minutes. Perfect for new users who want to start immediately.

### [User Guide](user-guide.md)
Complete user manual covering all features available to regular users:
- Dashboard Overview
- Lead Management (Lead Pool, My Leads, Customers)
- Invoice Management
- Product Management
- Personal Settings

### [Administrator Guide](admin-guide.md)
Comprehensive guide for administrators and tenant admins:
- User Management
- Subscription Management
- File Management
- System Configuration
- Permission Management

### [Subscription & Billing](subscription.md)
Detailed documentation about SaaS subscription and billing features:
- Plan Types (Starter, Pro, Business)
- Billing Cycles (Monthly, Yearly)
- Upgrade Rules
- Payment Processing

### [FAQ](faq.md)
Frequently asked questions and troubleshooting tips.

---

## 🎯 System Overview

TinyCRM is a multi-tenant SaaS Customer Relationship Management system designed to help businesses manage:

- **Lead Management**: Capture, track, and convert leads
- **Customer Management**: Maintain comprehensive customer profiles
- **Invoice & Order Management**: Create invoices, manage orders, and track payments
- **Product Management**: Organize and manage your product catalog
- **Team Collaboration**: Multi-user support with role-based permissions

## 🏗️ System Architecture

```
┌─────────────┐
│   Tenant    │
└──────┬──────┘
       │
   ┌───┴───┬──────────────┐
   │       │              │
┌──▼──┐ ┌──▼──┐    ┌─────▼─────┐
│Users│ │Sub. │    │Plan Limits│
└──┬──┘ └─────┘    └─────┬─────┘
   │                     │
   │    ┌───────────────┼───────┐
   │    │               │       │
┌──▼──┐┌▼──┐ ┌─────────▼──┐ ┌─▼────┐
│Lead ││My │ │  Customers  │ │Invo. │
│Pool ││Leads│ └──────┬─────┘ └──┬───┘
└─────┘└────┘         │          │
                      │          │
                  ┌───▼──────────▼───┐
                  │    Products       │
                  └──────────────────┘
```

## 📋 Key Concepts

### Lead Flow
```
Lead Pool → My Leads → Customers
   (Public)   (Assigned)  (Converted)
```

### User Roles
- **Admin**: Full system access
- **Tenant Admin**: Manage tenant users and settings
- **Regular User**: Access to assigned leads and customers

### Subscription Plans
| Plan | Features |
|------|----------|
| Starter | Basic lead and customer management |
| Pro | Advanced features with higher limits |
| Business | Full feature access with maximum limits |

## 🚀 Getting Started

1. **New User?** Start with the [Quick Start Guide](quick-start.md)
2. **Need Details?** Read the [User Guide](user-guide.md)
3. **Administrator?** Check the [Administrator Guide](admin-guide.md)
4. **Have Questions?** Visit the [FAQ](faq.md)

## 📞 Support

For additional support or questions not covered in this documentation, please contact:

**Website**: [https://www.tinycrmgo.com](https://www.tinycrmgo.com)

**Email**: contact@tinycrmgo.com

You can also contact your system administrator for assistance.

---

*Last Updated: January 2025*
