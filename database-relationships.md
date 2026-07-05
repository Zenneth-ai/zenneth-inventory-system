# Database Relationships (ERD)

## Branches
- One Branch has many Users
- One Branch has many Employees
- One Branch has many Inventory Records
- One Branch has many Sales
- One Branch has many Purchases
- One Branch has many Expenses

## Roles
- One Role has many Users

## Brands
- One Brand has many Products

## Products
- One Product has many Inventory Records
- One Product has many Stock Transactions
- One Product can appear in many Sales
- One Product can appear in many Purchases

## Customers
- One Customer has many Sales

## Suppliers
- One Supplier has many Purchases

## Employees
- One Employee has many Payroll Records

## Users
- One User has many Stock Transactions
- One User has many Activity Logs
