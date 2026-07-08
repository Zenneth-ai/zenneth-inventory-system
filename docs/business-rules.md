# ZIMS Business Rules Engine

## Purpose

The Business Rules Engine automatically enforces company policies without relying on manual checks.

---

## Inventory Rules

- Prevent negative stock.
- Prevent duplicate barcodes.
- Prevent duplicate SKUs.
- Require approval for stock adjustments.
- Block sales when stock is zero.

---

## Sales Rules

- Do not allow discounts above the approved limit.
- Block sales when a cashier's shift is closed.
- Require manager approval for refunds.
- Prevent duplicate receipt numbers.

---

## Pricing Rules

- Selling price cannot be lower than cost price unless approved.
- Record every price change in the audit log.
- Keep complete price history.

---

## Employee Rules

- Employees only access assigned branches.
- Employees only perform actions allowed by their role.
- Every login and logout is recorded.
- Every barcode scan is recorded.

---

## Security Rules

- Passwords are encrypted.
- Automatic session timeout after inactivity.
- Lock account after repeated failed login attempts.
- Record every important action in the audit log.

---

## LPG Rules

- Every cylinder has a unique serial number.
- Every cylinder movement is recorded.
- Lost cylinders require manager approval.
- Damaged cylinders require inspection before write-off.

---

## Notifications

Notify managers when:

- Stock falls below reorder level.
- A large discount is requested.
- A refund is requested.
- Stock is adjusted.
- A shift closes with a cash difference.

---

## Future Rules

- AI fraud detection.
- Automatic reorder suggestions.
- Demand forecasting.
- Smart approval recommendations.
