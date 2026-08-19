# Accountant Package

## Purpose

This file defines how Varona GmbH should prepare monthly or annual documents for an accountant/fiduciary.

## Monthly Package

For each month:

```txt
YYYY-MM/
├── 01_expense_register.csv
├── 02_expense_register.xlsx
├── 03_original_documents/
├── 04_missing_documents.md
├── 05_review_notes.md
├── 06_summary_by_category.csv
├── 07_summary_by_currency.csv
└── 08_questions_for_accountant.md
```

## Annual Package

For the year:

```txt
YYYY/
├── 01_full_expense_register.xlsx
├── 02_monthly_summaries/
├── 03_original_documents/
├── 04_missing_documents.md
├── 05_review_notes.md
├── 06_tax_review_items.md
├── 07_shareholder_loan_documents/
├── 08_bank_statements/
├── 09_broker_statements/
└── 10_questions_for_accountant.md
```

## Questions for Accountant

Track questions like:

```txt
Is this expense deductible?
Should this be capitalized?
Is VAT recoverable?
Is this personal or business?
How should this shareholder loan movement be treated?
How should foreign currency be handled?
```

## Accountant Review Principle

The AI prepares.

The accountant validates.

No AI-generated accounting treatment should be considered final without review.
