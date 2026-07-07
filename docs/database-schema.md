# ZIMS Database Schema (Version 1.0)

## Core Tables

### Users
- id
- name
- email
- password
- role_id
- branch_id

### Roles
- id
- name
- description

### Branches
- id
- name
- address

### Products
- id
- name
- sku
- barcode
- category_id
- brand_id
- unit_price
- quantity

### Categories
- id
- name

### Brands
- id
- name

### Customers
- id
- name
- phone
- email

### Suppliers
- id
- name
- phone
- email

### Sales
- id
- customer_id
- total
- payment_method
- created_by

### Purchases
- id
- supplier_id
- total
- created_by

### Stock Movements
- id
- product_id
- type
- quantity
- reference

### Expenses
- id
- title
- amount
- category

### Settings
- id
- company_name
- business_type
- currency
