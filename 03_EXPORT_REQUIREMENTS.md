# Export Requirements

## Purpose

This file defines the minimum export format needed for accountant review.

## Required Export Formats

The system should be able to export:

```txt
CSV
Excel
JSON backup
PDF document archive
```

## Minimum CSV Columns

```txt
document_id
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
review_status
file_link
notes
```

## Accountant Export

The accountant-ready export should include:

```txt
1. Expense register CSV/Excel
2. Original documents
3. Missing documents list
4. Review notes
5. Summary by category
6. Summary by month
7. Summary by currency
8. Potential tax/VAT review items
```

## Monthly Export Folder

Suggested structure:

```txt
accountant_package/
└── 2026-08/
    ├── 01_expense_register.csv
    ├── 02_expense_register.xlsx
    ├── 03_original_documents/
    ├── 04_missing_documents.md
    ├── 05_review_notes.md
    └── 06_summary_by_category.csv
```

## Review Status Before Export

Only export final accountant package when each row is one of:

```txt
Approved
Corrected
Sent to Accountant
```

Rows still marked as `To Review` should appear in `04_missing_documents.md` or `05_review_notes.md`.

## Quality Checks

Before exporting:

- All documents have a document date.
- All documents have supplier name.
- All documents have gross amount.
- All documents have currency.
- All documents have category.
- All documents have review status.
- Uncertain rows are flagged.
- Original file link exists.
