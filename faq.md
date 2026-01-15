---
layout: default
title: FAQ
nav_order: 6
description: "Frequently asked questions and answers about using TinyCRM"
permalink: /faq/
---

# Frequently Asked Questions (FAQ)

Common questions and answers about using TinyCRM.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Lead Management](#lead-management)
3. [Customer Management](#customer-management)
4. [Invoice Management](#invoice-management)
5. [User & Permissions](#user--permissions)
6. [Subscription & Billing](#subscription--billing)
7. [Technical Issues](#technical-issues)

---

## Getting Started

### Q: How do I log in to TinyCRM?

**A**: Navigate to the login page and enter your email address and password. If you don't have an account, contact your administrator to create one or accept an invitation.

### Q: I forgot my password. How do I reset it?

**A**: 
1. Click "Forgot Password" on the login page
2. Enter your email address
3. Check your email for a password reset link
4. Click the link and set a new password

### Q: What browser should I use?

**A**: TinyCRM works best with modern browsers:
- Chrome (recommended)
- Firefox
- Safari
- Edge

Ensure your browser is up to date for the best experience.

### Q: Is there a mobile app?

**A**: TinyCRM is a web-based application that works on mobile browsers. While there's no dedicated mobile app, the interface is responsive and works well on tablets and smartphones.

---

## Lead Management

### Q: What's the difference between Lead Pool, My Leads, and Customers?

**A**: 

```
Lead Management Flow:
┌──────────────┐      Claim      ┌──────────────┐
│  Lead Pool   │ ──────────────► │  My Leads    │
│ (Public,     │                  │ (Assigned    │
│ Unassigned)  │                  │  to You)     │
└──────────────┘                  └──────┬───────┘
                                         │ Convert
                                         ▼
                                    ┌──────────────┐
                                    │  Customers   │
                                    │ (Business    │
                                    │ Relationship) │
                                    └──────────────┘
```

- **Lead Pool**: Public leads available to all users. Anyone can claim them.
- **My Leads**: Leads assigned to you. You can manage and convert them.
- **Customers**: Converted leads with an established business relationship. Only customers can have invoices.

### Q: How do I claim a lead from the Lead Pool?

**A**:
1. Go to **CRM → Lead Pool**
2. Find the lead you want
3. Click **Claim**
4. The lead moves to **My Leads**

### Q: Can I return a lead to the Lead Pool?

**A**: Yes, if a lead is in "My Leads" and hasn't been converted to a customer, you can release it. However, once converted to a customer, you can only return it to "My Leads" status, not back to the Lead Pool.

### Q: What happens if I mark a lead as invalid?

**A**: Invalid leads are marked but remain in your "My Leads" list. You can still convert them to customers later if needed. Invalid status helps you filter and prioritize your leads.

### Q: How do I convert a lead to a customer?

**A**:
1. Go to **CRM → My Leads**
2. Open the lead
3. Click **Convert to Customer**
4. Select a customer level (1-5)
5. Click **Save**

> 💡 **Note**: Only leads assigned to you (in "My Leads") can be converted to customers.

---

## Customer Management

### Q: What are customer levels?

**A**: Customer levels (1-5) help you categorize customers by importance:

| Level | Typical Use |
|-------|-------------|
| 1 | New customers |
| 2 | Regular customers |
| 3 | Important accounts |
| 4 | VIP customers |
| 5 | Strategic partners |

### Q: Can I change a customer's level?

**A**: Yes, open the customer and click **Set Customer Level** to change it.

### Q: Can I convert a customer back to a lead?

**A**: Yes, use the **Return to Lead** button on the customer page. This moves the customer back to "My Leads" status.

### Q: Why can't I create an invoice for a lead?

**A**: Only customers can have invoices. Convert the lead to a customer first, then create the invoice.

---

## Invoice Management

### Q: What invoice statuses are there?

**A**: 

| Status | Description |
|--------|-------------|
| **Open** | Draft invoice, can be edited |
| **Confirmed** | Finalized, ready to send |
| **Paid** | Payment received |

### Q: Can I edit an invoice after confirming it?

**A**: No, confirmed invoices are read-only. Only "Open" invoices can be edited. If you need to modify a confirmed invoice, contact your administrator.

### Q: How do I add multiple products to an invoice?

**A**:
1. Create or edit an invoice
2. Click **Add Product** for each product
3. Select product, quantity, and price
4. Repeat for additional products

### Q: How are discounts and fees calculated?

**A**: 

```
Total = Subtotal - Discount + Additional Fees + Tax + Shipping
```

Discounts are subtracted from the subtotal, while fees (tax, shipping, etc.) are added.

### Q: Can I export invoices as PDF?

**A**: Yes, open a confirmed or paid invoice and click **Export PDF** to download it.

### Q: How do I send an invoice to a customer?

**A**: 
1. Open a confirmed invoice
2. Click **Send**
3. Enter recipient email (if different from customer email)
4. Add message (optional)
5. Click **Send**

> 💡 **Note**: Email sending requires proper email configuration.

---

## User & Permissions

### Q: What's the difference between Admin and User roles?

**A**:

| Role | Permissions |
|------|-------------|
| **Admin** | Full access, user management, subscription management |
| **User** | Access to assigned leads, customers, invoices |

### Q: Can I change my own role?

**A**: No, only administrators can change user roles. Contact your administrator if you need role changes.

### Q: Why can't I see certain features?

**A**: Your role may not have permission. Contact your administrator to review your permissions.

### Q: How do I invite new users?

**A**: Administrators can invite users:
1. Go to **System → Users**
2. Click **Invite User**
3. Enter email and select role
4. Send invitation

---

## Subscription & Billing

### Q: What subscription plans are available?

**A**: Three plans are available:

| Plan | Features |
|------|----------|
| **Starter** | Basic CRM features |
| **Pro** | Advanced features, higher limits |
| **Business** | Full features, maximum limits |

### Q: Can I upgrade my subscription?

**A**: Yes, administrators can upgrade at any time:
1. Go to **System → Subscription**
2. Click **Upgrade**
3. Select new plan
4. Confirm upgrade

Upgrades take effect immediately with prorated billing.

### Q: Can I downgrade my subscription?

**A**: No, downgrades are not supported. Contact support if you need to discuss your subscription.

### Q: What happens when my subscription expires?

**A**: Some features may be limited until you renew. You'll receive warnings before expiration. Renew as soon as possible to avoid service interruption.

### Q: How do I check my subscription usage?

**A**: Go to **System → Subscription** to view:
- Current usage vs. limits
- Customers count
- Users count
- Storage usage

### Q: Can I cancel my subscription?

**A**: Users cannot cancel subscriptions directly. Contact support or your administrator for cancellation requests.

---

## Technical Issues

### Q: The page is loading slowly. What should I do?

**A**: 
1. Check your internet connection
2. Clear browser cache
3. Try a different browser
4. Contact support if issues persist

### Q: I'm getting an error message. What should I do?

**A**: 
1. Note the exact error message
2. Try refreshing the page
3. Check if you have proper permissions
4. Contact support with error details

### Q: My data seems incorrect. How do I fix it?

**A**: 
1. Check if you're viewing the correct filters
2. Verify you have access to the data
3. Review audit logs (if admin) to see changes
4. Contact support if data appears corrupted

### Q: Can I export my data?

**A**: 
- **Invoices**: Export individual invoices as PDF
- **Products**: Export product list (if feature available)
- **Full Data Export**: Contact your administrator for full data export

### Q: How do I report a bug?

**A**: Contact your administrator or support team with:
- Description of the issue
- Steps to reproduce
- Screenshots (if possible)
- Browser and system information

---

## General Questions

### Q: Is my data secure?

**A**: Yes, TinyCRM uses industry-standard security practices:
- Data encryption
- Tenant isolation
- Access controls
- Regular backups

### Q: How often is data backed up?

**A**: Backups are performed regularly (typically daily). Contact your administrator for specific backup schedules.

### Q: Can I customize the system?

**A**: Some customization options are available to administrators. Contact support for advanced customization needs.

### Q: Where can I get more help?

**A**: 
- Check the [User Guide](user-guide.md) for detailed instructions
- Review the [Administrator Guide](admin-guide.md) for admin features
- Contact your system administrator
- Reach out to support team

---

## Still Have Questions?

If your question isn't answered here:

1. **Visit Website**: [https://www.tinycrmgo.com](https://www.tinycrmgo.com)
2. **Check Documentation**: Review the [User Guide](user-guide.md) or [Administrator Guide](admin-guide.md)
3. **Contact Administrator**: Reach out to your organization's administrator
4. **Support**: Contact us at **contact@tinycrmgo.com**

---

*Last Updated: January 2025*
