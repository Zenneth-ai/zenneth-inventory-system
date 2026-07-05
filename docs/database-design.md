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
