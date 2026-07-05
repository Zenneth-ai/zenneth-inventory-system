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
