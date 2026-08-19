# Expense Fields

## Purpose

This file defines the minimum professional fields that Varona GmbH should capture from receipts, invoices and expense documents.

## Required Fields

```txt
document_id
upload_date
document_date
supplier_name
supplier_country
document_type
invoice_number
currency
net_amount
tax_amount
gross_amount
vat_rate
payment_method
expense_category
business_purpose
deductible_status
confidence_score
needs_review
review_status
file_link
original_filename
suggested_filename
notes
```

## Field Definitions

### document_id

Unique internal ID for the document.

Example:

```txt
EXP-2026-0001
```

### document_date

Date shown on the invoice, receipt or document.

### supplier_name

Name of the supplier/vendor.

Examples:

```txt
GoDaddy
Wise
Interactive Brokers
Google
OpenAI
Microsoft
```

### document_type

Allowed values:

```txt
Invoice
Receipt
Bank Statement
Broker Statement
Transfer Confirmation
Subscription
Contract
Tax Document
Other
```

### currency

Examples:

```txt
CHF
EUR
USD
GBP
```

### amounts

Capture:

```txt
net_amount
tax_amount
gross_amount
vat_rate
```

If tax is not shown, leave tax fields blank/null and set `needs_review` if uncertain.

### payment_method

Allowed values:

```txt
Wise Card
Wise Transfer
Bank Transfer
Credit Card
Debit Card
IBKR
Cash
Personal Paid
Unknown
```

### expense_category

Use the category list in:

```txt
02_EXPENSE_CATEGORIES.md
```

### business_purpose

Short explanation of why the expense is business-related.

Examples:

```txt
Company email service
Broker account setup
LEI registration
AI software subscription
Professional services
```

### deductible_status

Suggested values:

```txt
Likely deductible
Partially deductible
Non-deductible
Needs accountant review
Unknown
```

Final deductibility should be reviewed by an accountant.

### confidence_score

Suggested scale:

```txt
high
medium
low
```

### needs_review

Boolean:

```txt
true
false
```

Set to true when key fields are missing, unclear, personal, sensitive, or require accounting/tax judgment.

### review_status

Allowed values:

```txt
To Review
Approved
Corrected
Rejected
Sent to Accountant
Archived
```

### suggested_filename

Professional filename suggested by AI.

Format:

```txt
YYYY-MM-DD__Supplier__Document_Type__Description__Amount_Currency.ext
```

Example:

```txt
2026-08-19__GoDaddy__Invoice__Company_Email__25_CHF.pdf
```
