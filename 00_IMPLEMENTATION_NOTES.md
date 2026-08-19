# Implementation Notes

## Decision

The chosen minimum implementation path is to use an existing open-source expense/accounting tool instead of building a custom application.

Preferred first tool:

```txt
TaxHacker
```

## Objective

Create the simplest professional expense system for Varona GmbH.

The system should allow Paula to:

1. Upload receipts, invoices and PDFs.
2. Extract key fields using AI.
3. Review and correct extracted fields.
4. Categorise expenses.
5. Export structured data.
6. Prepare documents for accountant review.

## Current Varona Context

Varona GmbH is a Swiss company.

Current operational context:

- Company banking: Wise business account.
- Company email: varona-capital.ch.
- Company documentation storage: Google Drive.
- GitHub is used for policies, prompts, operating documentation and system design.
- External accountant/fiduciary is not yet fully integrated.
- The system must be accountant-ready.

## MVP Definition

The MVP is successful when:

```txt
10 real documents are uploaded
        ↓
AI extracts key fields
        ↓
Paula reviews/corrects
        ↓
Expenses are categorized
        ↓
CSV/Excel export works
        ↓
Accountant can understand the package
```

## Minimum Human Review Rule

Every extracted document must be reviewed by Paula before being considered final.

The AI can suggest. The human approves.

## Do Not Automate Yet

Do not automate:

- Tax filings.
- VAT returns.
- Payments.
- Final accounting classifications.
- Regulatory decisions.
- Deletion of original documents.
- Sending documents to third parties.

## First Real Test

Upload these examples:

```txt
1. GoDaddy invoice
2. Wise statement
3. Wise transfer confirmation
4. LEI invoice
5. LEI confirmation
6. Software subscription invoice
7. Receipt paid with company card
8. IBKR-related document
9. Professional service invoice
10. Other company expense
```

## Success Criteria

For each document, check:

- Correct document date.
- Correct supplier.
- Correct amount.
- Correct currency.
- Correct tax/VAT if present.
- Correct category.
- Correct business purpose.
- Correct review status.
- Exportable row.
- Link to original file.
