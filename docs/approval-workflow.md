# ZIMS Approval Workflow

## Overview

Sensitive business actions require approval before they are completed.

Every request is recorded with complete audit information.

---

## Approval Levels

### Level 1 - Manager

Can approve:

- Price Changes
- Stock Adjustments
- Product Returns
- Purchase Orders
- Large Discounts

---

### Level 2 - Super Admin

Can approve:

- Product Deletion
- Employee Role Changes
- Company Settings
- Branch Creation
- Database Restore

---

## Approval Requests

Every request contains:

- Request ID
- Employee Name
- Employee Role
- Branch
- Action Requested
- Reason
- Date
- Time
- Status

Status:

- Pending
- Approved
- Rejected
- Cancelled

---

## Actions Requiring Approval

### Inventory

- Delete Product
- Stock Adjustment
- Stock Transfer
- Mark Product Damaged

### Sales

- Void Sale
- Cancel Receipt
- Refund Customer
- High Discount

### Products

- Change Selling Price
- Change Cost Price
- Disable Product

### Employees

- Promote Employee
- Change Role
- Reset Password

---

## LPG Module

Approval required for:

- Cylinder Write-Off
- Cylinder Loss
- Cylinder Transfer
- Bulk Stock Adjustment

---

## Audit Trail

Every approval stores:

- Requested By
- Approved By
- Rejected By
- Reason
- Date
- Time
- Branch

Approval history cannot be deleted.

---

## Notifications

Notify:

- Manager
- Super Admin
- Business Owner

For:

- Pending Approvals
- Approved Requests
- Rejected Requests

---

## Dual Approval

Required for:

- Large Stock Adjustments
- High Value Refunds
- Company Settings
- Database Restore

Workflow:

Employee
↓

Manager Approval
↓

Super Admin Approval
↓

Completed
