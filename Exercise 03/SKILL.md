---
name: ap-invoice-entry
description: Checks and logs a vendor invoice in the AP invoice register, and sends invoices of $10,000 or more for approval. Use when the user wants to log, enter, record or add a vendor invoice or bill, or asks whether an invoice is already in the register.
---

# AP invoice entry

Follow these steps every time a user wants to log a vendor invoice.

## 1. Collect the details
You need all of these. Ask for anything missing, one short question at a time:
- Vendor
- Vendor invoice number
- Invoice date (YYYY-MM-DD)
- Amount in USD
- Description of the goods or services
- Department

## 2. Check for a duplicate
Use the **Look up AP invoices** tool to search the register for the same vendor and vendor invoice number.
- If you find a match, do **not** add the invoice. Show the existing row (InvoiceID, amount, status) and ask the user to check it.

## 3. Code the invoice
Pick the GL account from this list. If none fits, ask the user.

| GL account | Use for |
| --- | --- |
| 5100 Packaging | Boxes, mailers, packing materials |
| 6100 Freight-in | Inbound freight and delivery |
| 6200 Repairs and maintenance | Janitorial, repairs, facility services |
| 6250 Security | Security guards and alarm services |
| 6300 Utilities | Electricity, gas, water |
| 6350 Telecom | Phone and internet |
| 6400 IT services | IT support, software services |
| 6500 Office supplies | Stationery, toner, small supplies |
| 6600 Marketing | Printing, signage, advertising |
| 6700 Professional fees | Audit, tax, legal, consulting |

## 4. Fill in the rest
- **InvoiceID:** the next number after the highest AP- number in the register (for example AP-1021).
- **DueDate:** invoice date plus 30 days (Net 30), unless the user gives other terms.
- **Status:** "Pending Approval" if the amount is $10,000 or more; otherwise "Open".
- **EnteredBy:** "Agent - " followed by the user's name, if known.

## 5. Confirm, then write
Show the full row as a table and ask "Shall I add this invoice?" Only after the user says yes, use the **Log new AP invoice** tool.

## 6. Approval
If the status is Pending Approval, use the **Request invoice approval** workflow with the InvoiceID, vendor, amount and description. Tell the user the approval request was sent.

## 7. Accounting reminder
If the goods or services were received in an earlier month than the invoice date, remind the user that under US GAAP accrual accounting the expense belongs in the month it was incurred, so an accrual may be needed for that period.

## Rules
- Never change or delete existing rows.
- Never add an invoice without the user's confirmation.
- If the user shares bank account numbers, SSNs or other sensitive details, don't store them. Ask them to leave them out.
