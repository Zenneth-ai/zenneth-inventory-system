# Seed Data

## Default Roles
- Admin
- Manager
- Storekeeper
- Salesperson
- Accountant
- HR Officer

## Product Categories
- LPG Cylinders
- LPG Accessories
- Cookers
- Burners
- Regulators
- Hoses
- Valves

## LPG Brands
- Pro Gas
- Total
- Wajiko Gas
- Hashi Gas

## Default Status
- Active
- Inactive

## Notes
This file contains the default data that will be inserted into the database during system setup.
# Table: products

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| product_name | VARCHAR(150) | Product Name |
| sku | VARCHAR(50) | Stock Keeping Unit |
| barcode | VARCHAR(100) | Barcode |
| category_id | BIGINT | Category Reference |
| brand_id | BIGINT | Brand Reference |
| unit | VARCHAR(20) | Piece, Kg, Litre, etc. |
| buying_price | DECIMAL(10,2) | Buying Price |
| selling_price | DECIMAL(10,2) | Selling Price |
| reorder_level | INT | Minimum Stock Level |
| description | TEXT | Product Description |
| status | ENUM | Active / Inactive |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: categories

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| category_name | VARCHAR(100) | Category Name |
| description | TEXT | Category Description |
| status | ENUM | Active / Inactive |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |

### Default Categories
- LPG Cylinders
- Regulators
- Hoses
- Burners
- Gas Cookers
- Valves
- Accessories
---

## Table: sale_items

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| sale_id | BIGINT | Linked Sale |
| product_id | BIGINT | Linked Product |
| quantity | INT | Quantity Sold |
| unit_price | DECIMAL(10,2) | Selling Price |
| discount | DECIMAL(10,2) | Discount |
| total | DECIMAL(10,2) | Total Amount |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: purchase_items

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| purchase_id | BIGINT | Linked Purchase |
| product_id | BIGINT | Linked Product |
| quantity | INT | Quantity Purchased |
| unit_cost | DECIMAL(10,2) | Buying Price |
| total | DECIMAL(10,2) | Total Cost |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: cylinder_exchanges

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| customer_id | BIGINT | Customer |
| product_id | BIGINT | LPG Product |
| empty_quantity | INT | Empty Cylinders Returned |
| full_quantity | INT | Full Cylinders Issued |
| exchange_fee | DECIMAL(10,2) | Exchange Charge |
| user_id | BIGINT | Staff Member |
| created_at | TIMESTAMP | Exchange Date |
---

## Table: payments

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| sale_id | BIGINT | Linked Sale |
| payment_method | VARCHAR(20) | Cash / M-PESA / Bank |
| amount | DECIMAL(10,2) | Amount Paid |
| reference_number | VARCHAR(100) | Transaction Reference |
| payment_status | VARCHAR(20) | Paid / Pending |
| created_at | TIMESTAMP | Payment Date |
---

## Table: notifications

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| title | VARCHAR(150) | Notification Title |
| message | TEXT | Notification Message |
| type | VARCHAR(50) | Info, Warning, Success, Error |
| user_id | BIGINT | Recipient User |
| is_read | BOOLEAN | Read Status |
| created_at | TIMESTAMP | Date Created |
| updated_at | TIMESTAMP | Date Updated |

### Examples
- Low Stock Alert
- New Sale Completed
- Cylinder Exchange Completed
- Purchase Received
- Payment Confirmed
---

## Table: audit_logs

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| user_id | BIGINT | User who performed the action |
| action | VARCHAR(100) | Action Performed |
| module | VARCHAR(100) | Module Affected |
| description | TEXT | Action Details |
| ip_address | VARCHAR(50) | User IP Address |
| created_at | TIMESTAMP | Date Created |
---

## Table: expenses

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| expense_category | VARCHAR(100) | Expense Category |
| amount | DECIMAL(10,2) | Amount |
| payment_method | VARCHAR(50) | Cash / Bank / M-PESA |
| description | TEXT | Expense Details |
| expense_date | DATE | Expense Date |
| user_id | BIGINT | Recorded By |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: payroll

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| employee_id | BIGINT | Linked Employee |
| basic_salary | DECIMAL(10,2) | Basic Salary |
| allowances | DECIMAL(10,2) | Allowances |
| deductions | DECIMAL(10,2) | Deductions |
| net_salary | DECIMAL(10,2) | Net Salary |
| payment_date | DATE | Salary Payment Date |
| status | ENUM | Paid / Pending |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: branches

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| branch_name | VARCHAR(100) | Branch Name |
| branch_code | VARCHAR(20) | Unique Branch Code |
| address | TEXT | Branch Address |
| phone | VARCHAR(20) | Contact Number |
| email | VARCHAR(100) | Branch Email |
| manager_id | BIGINT | Branch Manager |
| status | ENUM | Active / Inactive |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
---

## Table: system_settings

| Field | Type | Description |
|-------|------|-------------|
| id | BIGINT | Primary Key |
| company_name | VARCHAR(150) | Company Name |
| company_email | VARCHAR(100) | Company Email |
| company_phone | VARCHAR(20) | Company Phone |
| company_address | TEXT | Company Address |
| currency | VARCHAR(10) | Currency (KES) |
| tax_rate | DECIMAL(5,2) | Default Tax Rate |
| logo | VARCHAR(255) | Company Logo |
| created_at | TIMESTAMP | Created Date |
| updated_at | TIMESTAMP | Updated Date |
