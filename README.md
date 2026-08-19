# Varona Expense OS

Implementation repository for the Varona GmbH expense, invoice and accounting-preparation workflow.

This repository does **not** build a custom expense app from scratch.

The goal is to use an existing open-source solution, preferably **TaxHacker**, as the base system for:

- Uploading receipts, invoices and expense documents.
- Extracting structured fields with AI.
- Reviewing and correcting extracted data.
- Categorising expenses professionally.
- Exporting data for accountant review.
- Preparing monthly and annual accounting packages.

## Current Decision

Use TaxHacker as the first implementation path.

## Target Workflow

```txt
Receipt / Invoice / PDF
        ↓
TaxHacker upload
        ↓
AI extraction
        ↓
Paula review
        ↓
Expense register
        ↓
Export CSV / Excel
        ↓
Accountant package
```

## Repository Purpose

This repo stores:

- Implementation notes.
- Required expense fields.
- Expense categories.
- Export requirements.
- Accountant package structure.
- Custom extraction prompts.
- Testing checklist.
- Future automation notes.

## What This Is Not

This repository is not:

- A custom accounting app.
- A tax filing system.
- A regulated financial system.
- A replacement for an accountant.
- A final tax/accounting judgment engine.

## First Milestone

Process 10 real Varona GmbH documents:

- GoDaddy invoice.
- Wise statement.
- LEI invoice/confirmation.
- Software subscriptions.
- Receipts.
- IBKR-related documents if relevant.
- Bank transfer confirmations.
- Any company expense invoice.

Then check:

- Are fields extracted correctly?
- Are categories useful?
- Can data be exported?
- Is accountant review easy?
- What needs to be customized?
