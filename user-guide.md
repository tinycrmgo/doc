---
layout: default
title: User Guide
nav_order: 3
description: "Complete guide to using TinyCRM for managing leads, customers, invoices, and products"
permalink: /user-guide/
---

# User Guide

Complete guide to using TinyCRM for managing leads, customers, invoices, and products.

## Table of Contents

1. [Dashboard Overview](#dashboard-overview)
2. [Lead Management](#lead-management)
3. [Customer Management](#customer-management)
4. [Invoice Management](#invoice-management)
5. [Product Management](#product-management)
6. [Personal Settings](#personal-settings)

---

## Dashboard Overview

The Dashboard provides a comprehensive overview of your CRM activities and key metrics.

### Key Statistics

The dashboard displays:

- **Lead Pool**: Total number of available public leads
- **My Leads**: Leads assigned to you
- **Customers**: Your converted customers
- **Invoices**: Total number of invoices
- **Revenue**: Total revenue from all invoices
- **Customer Levels**: Distribution of customers by level

### Dashboard Layout

```
┌─────────────────────────────────────────────────┐
│  Dashboard                                      │
├─────────────────────────────────────────────────┤
│  📊 Statistics Cards                            │
│  ┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐          │
│  │Leads │ │My    │ │Cust. │ │Invo. │          │
│  │Pool  │ │Leads │ │      │ │      │          │
│  └──────┘ └──────┘ └──────┘ └──────┘          │
│                                                 │
│  💰 Revenue Chart                               │
│  📈 Customer Level Distribution                 │
└─────────────────────────────────────────────────┘
```

---

## Lead Management

TinyCRM uses a three-tier lead management system:

### Lead Flow Diagram

```
Lead Management Flow:
┌──────────────┐
│  Lead Pool   │ (Public Leads)
│  (Unassigned) │
└───────┬───────┘
        │ Claim
        ▼
┌──────────────┐
│  My Leads    │ (Assigned to Me)
│  (My Leads)  │
└───────┬───────┘
        │ Convert
        ▼
┌──────────────┐
│  Customers   │ (Converted Leads)
│  (Customers) │
└───────┬───────┘
        │ Create Invoice
        ▼
┌──────────────┐
│   Invoices   │
└──────────────┘
```

### 1. Lead Pool

The **Lead Pool** contains public leads available to all users in your organization.

#### Features:
- **View All Leads**: Browse all available public leads
- **Search & Filter**: Find leads by name, industry, location, etc.
- **Claim Leads**: Assign leads to yourself

#### How to Claim a Lead:

1. Navigate to **CRM → Lead Pool**
2. Browse or search for leads
3. Click **Claim** on a lead
4. The lead moves to **My Leads**

> 💡 **Note**: Once claimed, the lead is assigned to you and removed from the public pool.

### 2. My Leads

**My Leads** contains leads that have been assigned to you (either claimed from the Lead Pool or directly assigned).

#### Features:
- **View Assigned Leads**: See all leads assigned to you
- **Manage Lead Status**: Mark leads as valid or invalid
- **Convert to Customer**: Transform qualified leads into customers
- **Follow-up Tracking**: Record interactions and follow-ups
- **Contact Management**: Add and manage company contacts

#### Lead Status

| Status | Description |
|--------|-------------|
| Valid Lead | Active lead that should be pursued |
| Invalid Lead | Lead that is not worth pursuing |

#### Converting a Lead to Customer:

1. Go to **CRM → My Leads**
2. Open a lead you want to convert
3. Click **Convert to Customer**
4. Select a **Customer Level** (1-5)
5. Click **Save**

> ✅ **Success**: The lead is now a customer and can have invoices created.

### 3. Customers

**Customers** are converted leads that have an established business relationship.

#### Customer Levels

| Level | Description | Typical Use Case |
|-------|-------------|------------------|
| 1 | New Customer | Recently converted leads |
| 2 | Regular Customer | Ongoing business relationship |
| 3 | Important Customer | High-value or strategic accounts |
| 4 | VIP Customer | Premium accounts with special treatment |
| 5 | Strategic Partner | Long-term strategic relationships |

#### Customer Features:

- **Customer Profile**: Comprehensive company information
- **Invoice Management**: Create and manage invoices
- **Contact History**: Track all interactions
- **Activity Log**: View complete activity history
- **Return to Lead**: Convert customer back to lead if needed

#### Customer Management Actions:

```
Customer View
├── Edit Information
├── Set Customer Level
├── Create Invoice
├── View Activity Log
├── Manage Contacts
└── Return to Lead (if needed)
```

---

## Invoice Management

Create, manage, and track invoices for your customers.

### Invoice Workflow

```
Invoice Creation Process:
┌──────────────┐
│Create Invoice│
└──────┬───────┘
       │
       ▼
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
│Apply Discount/   │
│Fees (Optional)   │
└──────┬───────────┘
       │
       ▼
┌──────────────┐
│Review & Save  │
└──────┬───────┘
       │
       ▼
   ┌───┴───┐
   │Status│
   └───┬───┘
       │
   ┌───┼───┬──────────┐
   │   │   │          │
Open│   │Confirmed│   │Paid
   │   │          │   │
   │   │          │   │
   ▼   ▼          ▼   ▼
Edit Send      Complete
Update Export
```

### Invoice Status

| Status | Description | Actions Available |
|--------|-------------|-------------------|
| Open | Draft invoice, can be edited | Edit, Add Items, Confirm |
| Confirmed | Invoice is finalized | Send, Export PDF, View |
| Paid | Payment received | View, Export |

### Creating an Invoice

#### Step 1: Select Customer

1. Navigate to **Sales → Invoices**
2. Click **Create Invoice**
3. Select a **Customer** from the dropdown
   - Only customers (not leads) can have invoices
   - If you need to create an invoice for a lead, convert it to a customer first

#### Step 2: Add Products

1. Click **Add Product**
2. Select a product from the catalog
3. Enter **Quantity**
4. Enter **Unit Price** (or use product default price)
5. Click **Add**
6. Repeat for additional products

#### Step 3: Apply Discounts or Fees (Optional)

**Discounts:**
- Click **Apply Discount**
- Enter discount amount or percentage
- Discount is automatically calculated

**Additional Fees:**
- Click **Add Fee**
- Enter fee name and amount
- Select fee type (Additional, Tax, Shipping, etc.)

#### Step 4: Review and Save

1. Review the **Subtotal**, **Discount**, **Fees**, and **Total Amount**
2. Add any **Notes** if needed
3. Click **Save**

### Invoice Features

#### Invoice Items

- **Multiple Products**: Add unlimited products to an invoice
- **Quantity & Pricing**: Set quantity and unit price for each item
- **Automatic Calculation**: Subtotal calculated automatically

#### Discounts and Fees

```
Invoice Total Calculation:
┌─────────────────────────┐
│ Subtotal (Products)     │
│ - Discount              │
│ + Additional Fees       │
│ + Tax                   │
│ + Shipping              │
├─────────────────────────┤
│ Total Amount            │
└─────────────────────────┘
```

#### Invoice Actions

| Action | Description | When Available |
|--------|-------------|----------------|
| Edit | Modify invoice details | Status: Open |
| Add Item | Add more products | Status: Open |
| Remove Item | Remove products | Status: Open |
| Apply Discount | Add discount | Status: Open |
| Add Fee | Add additional charges | Status: Open |
| Confirm | Finalize invoice | Status: Open |
| Send | Email invoice to customer | Status: Confirmed |
| Export PDF | Download as PDF | Status: Confirmed/Paid |
| View | View invoice details | Always |

### Managing Invoices

#### Viewing Invoices

1. Go to **Sales → Invoices**
2. Use filters to find specific invoices:
   - Customer name
   - Invoice number
   - Status
   - Date range
   - Amount range

#### Editing Invoices

- Only **Open** invoices can be edited
- After confirming, invoices become read-only
- To modify a confirmed invoice, contact your administrator

#### Invoice Comments

- Add comments to track invoice-related communications
- View comment history in the invoice timeline
- Comments are visible to all users with invoice access

---

## Product Management

Manage your product catalog for use in invoices.

### Product Features

- **Product Catalog**: Centralized product database
- **Pricing**: Set default prices for products
- **Categories**: Organize products by category
- **Bulk Import**: Import products from Excel/CSV
- **Search & Filter**: Quickly find products

### Creating a Product

1. Navigate to **Sales → Products**
2. Click **Create Product**
3. Fill in product details:
   - **Name**: Product name
   - **Description**: Product description
   - **Price**: Default unit price
   - **Category**: Product category (optional)
   - **SKU**: Stock keeping unit (optional)
4. Click **Save**

### Product Import

Import multiple products at once using Excel/CSV:

1. Go to **Sales → Products**
2. Click **Import**
3. Download the template (if available)
4. Fill in product data:
   - Name (required)
   - Price (required)
   - Description (optional)
   - Category (optional)
   - SKU (optional)
5. Upload the file
6. Review imported products
7. Confirm import

### Using Products in Invoices

When creating an invoice:

1. Click **Add Product**
2. Select from your product catalog
3. The default price is automatically filled
4. Adjust quantity and price as needed

---

## Personal Settings

Manage your personal account settings and preferences.

### Accessing Personal Settings

1. Click on your **user menu** (top right)
2. Select **Profile**

### Available Settings

#### Profile Information

- **Name**: Your display name
- **Email**: Your email address (used for login)
- **Phone**: Contact phone number
- **Avatar**: Profile picture (if supported)

#### Password Management

- **Change Password**: Update your login password
- **Password Requirements**: 
  - Minimum length (typically 8 characters)
  - Mix of letters and numbers recommended

### Activity Log

View your activity history:

- Actions you've performed
- Leads you've claimed
- Customers you've created
- Invoices you've generated
- System changes you've made

---

## Best Practices

### Lead Management

1. **Regular Review**: Check the Lead Pool regularly for new opportunities
2. **Quick Response**: Claim promising leads quickly
3. **Status Management**: Keep lead status updated (valid/invalid)
4. **Follow-up**: Record all interactions with leads

### Customer Management

1. **Customer Levels**: Use customer levels to prioritize your efforts
2. **Complete Profiles**: Fill in all available customer information
3. **Regular Updates**: Keep customer information current
4. **Activity Tracking**: Log all customer interactions

### Invoice Management

1. **Accurate Products**: Use the product catalog for consistency
2. **Clear Descriptions**: Add notes for special terms or conditions
3. **Timely Confirmation**: Confirm invoices promptly after creation
4. **Professional Presentation**: Use PDF export for customer delivery

### Product Management

1. **Standardized Names**: Use consistent naming conventions
2. **Accurate Pricing**: Keep product prices up to date
3. **Categories**: Organize products with categories for easy finding
4. **Regular Updates**: Update product information as needed

---

## Keyboard Shortcuts

| Action | Shortcut | Description |
|--------|----------|-------------|
| Search | `Ctrl/Cmd + F` | Quick search in current page |
| New Lead | - | Create new lead (context menu) |
| New Invoice | - | Create new invoice (context menu) |

---

## Troubleshooting

### Common Issues

**Q: I can't see the Lead Pool**
- **A**: Ensure you have proper permissions. Contact your administrator.

**Q: I can't convert a lead to customer**
- **A**: Make sure the lead is assigned to you (in "My Leads") and has a valid status.

**Q: I can't create an invoice for a lead**
- **A**: Only customers can have invoices. Convert the lead to a customer first.

**Q: I can't edit an invoice**
- **A**: Only "Open" invoices can be edited. Confirmed invoices are read-only.

**Q: Products don't appear in invoice creation**
- **A**: Ensure products are created and active in the Products section.

---

## Additional Resources

- [Quick Start Guide](quick-start.md) - Get started in 5 minutes
- [Administrator Guide](admin-guide.md) - Advanced administration
- [FAQ](faq.md) - Frequently asked questions
- [Subscription Guide](subscription.md) - Subscription and billing

## Support

For additional help or questions not covered in this guide:

**Website**: [https://www.tinycrmgo.com](https://www.tinycrmgo.com)

**Email**: contact@tinycrmgo.com

You can also contact your system administrator for assistance.

---

*Last Updated: January 2025*
