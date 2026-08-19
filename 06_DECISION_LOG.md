# Decision Log

## Decision 001 — Expense System

### Date

2026-08-19

### Decision

Use an existing open-source solution instead of building a custom expense app from scratch.

### Preferred Tool

TaxHacker.

### Reason

Varona GmbH needs a simple, cheap and already-built system for:

- Uploading receipts and invoices.
- AI extraction.
- Expense categorization.
- Review.
- Export.

### Alternatives Considered

```txt
Receipt Wrangler
local-invoice-ocr
OpenInvoice
n8n expense workflow
Custom app
```

### Why Not Custom App Now

A custom app would create unnecessary complexity before the basic workflow is validated.

### Success Criteria

The tool must allow Paula to process real Varona GmbH expenses and export a clean accountant-ready register.

### Review Date

After processing the first 10 real documents.
