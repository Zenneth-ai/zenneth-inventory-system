# Database Design

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
