N# Database Design

This document contains the database schema for Zenneth Inventory Management System (ZIMS).
## Table: branches

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| branch_name | VARCHAR(100) | Branch Name |
| phone | VARCHAR(20) | Contact Number |
| email | VARCHAR(100) | Email Address |
| address | TEXT | Physical Address |
| manager | VARCHAR(100) | Branch Manager |
| status | ENUM | Active / Inactive |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |

---

## Table: roles

| Field | Type |
|-------|------|
| id | BIGINT |
| role_name | VARCHAR(50) |
| description | TEXT |

### Roles
- Admin
- Manager
- Storekeeper
- Salesperson
- Accountant
- HR Officer
## Table: branches

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| branch_name | VARCHAR(100) | Branch Name |
| phone | VARCHAR(20) | Contact Number |
| email | VARCHAR(100) | Email Address |
| address | TEXT | Physical Address |
| manager | VARCHAR(100) | Branch Manager |
| status | ENUM | Active / Inactive |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |

---

## Table: roles

| Field | Type |
|-------|------|
| id | BIGINT |
| role_name | VARCHAR(50) |
| description | TEXT |

### Roles
- Admin
- Manager
- Storekeeper
- Salesperson
- Accountant
- HR Officer
---

## Table: brands

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| brand_name | VARCHAR(100) | Brand Name |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |

### Initial Brands

- Pro Gas
- Total
- Wajiko
- K-Gas
- Hashi
---

## Table: products

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| product_name | VARCHAR(100) | Product Name |
| brand_id | BIGINT | Related Brand |
| category | VARCHAR(50) | Gas Cylinder / Accessory |
| cylinder_size | VARCHAR(20) | 6kg, 13kg, 50kg |
| buying_price | DECIMAL(10,2) | Purchase Price |
| selling_price | DECIMAL(10,2) | Selling Price |
| quantity | INT | Current Stock |
| reorder_level | INT | Minimum Stock |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: suppliers

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| supplier_name | VARCHAR(100) | Supplier Name |
| contact_person | VARCHAR(100) | Contact Person |
| phone | VARCHAR(20) | Phone Number |
| email | VARCHAR(100) | Email Address |
| address | TEXT | Physical Address |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: customers

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| customer_name | VARCHAR(100) | Customer Name |
| phone | VARCHAR(20) | Phone Number |
| email | VARCHAR(100) | Email Address |
| address | TEXT | Physical Address |
| customer_type | VARCHAR(20) | Walk-in / Registered |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: inventory

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| product_id | BIGINT | Linked Product |
| branch_id | BIGINT | Linked Branch |
| full_quantity | INT | Number of Full Cylinders |
| empty_quantity | INT | Number of Empty Cylinders |
| reorder_level | INT | Minimum Stock Level |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: stock_transactions

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| product_id | BIGINT | Linked Product |
| branch_id | BIGINT | Linked Branch |
| transaction_type | VARCHAR(20) | Stock In / Stock Out / Exchange / Adjustment |
| quantity | INT | Quantity Moved |
| reference_number | VARCHAR(50) | Transaction Reference |
| supplier_id | BIGINT | Supplier (if Stock In) |
| customer_id | BIGINT | Customer (if Stock Out) |
| user_id | BIGINT | User who performed the transaction |
| remarks | TEXT | Notes |
| created_at | TIMESTAMP | Transaction Date |
---

## Table: sales

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| invoice_number | VARCHAR(50) | Unique Invoice Number |
| customer_id | BIGINT | Linked Customer |
| branch_id | BIGINT | Linked Branch |
| payment_method | VARCHAR(20) | Cash / M-PESA / Bank |
| total_amount | DECIMAL(10,2) | Total Sale Amount |
| user_id | BIGINT | Salesperson |
| created_at | TIMESTAMP | Sale Date |
---

## Table: purchases

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| purchase_number | VARCHAR(50) | Purchase Number |
| supplier_id | BIGINT | Linked Supplier |
| branch_id | BIGINT | Linked Branch |
| total_amount | DECIMAL(10,2) | Total Purchase Cost |
| status | VARCHAR(20) | Pending / Completed |
| created_at | TIMESTAMP | Purchase Date |
---

## Table: employees

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| full_name | VARCHAR(100) | Employee Name |
| phone | VARCHAR(20) | Phone Number |
| email | VARCHAR(100) | Email Address |
| position | VARCHAR(50) | Job Position |
| salary | DECIMAL(10,2) | Monthly Salary |
| branch_id | BIGINT | Assigned Branch |
| status | VARCHAR(20) | Active / Inactive |
| created_at | TIMESTAMP | Created Date |
---

## Table: expenses

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| category | VARCHAR(100) | Expense Category |
| amount | DECIMAL(10,2) | Expense Amount |
| description | TEXT | Expense Details |
| branch_id | BIGINT | Branch |
| created_at | TIMESTAMP | Expense Date |
---

## Table: payroll

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| employee_id | BIGINT | Linked Employee |
| month | VARCHAR(20) | Payroll Month |
| basic_salary | DECIMAL(10,2) | Basic Salary |
| overtime | DECIMAL(10,2) | Overtime Pay |
| allowances | DECIMAL(10,2) | Allowances |
| deductions | DECIMAL(10,2) | Deductions |
| net_salary | DECIMAL(10,2) | Net Salary |
| payment_status | VARCHAR(20) | Paid / Unpaid |
| created_at | TIMESTAMP | Payment Date |
---

## Table: activity_logs

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| user_id | BIGINT | User |
| action | VARCHAR(100) | Action Performed |
| module | VARCHAR(50) | System Module |
| description | TEXT | Details |
| created_at | TIMESTAMP | Date & Time |
