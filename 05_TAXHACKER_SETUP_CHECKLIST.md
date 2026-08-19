# TaxHacker Setup Checklist

## Goal

Set up TaxHacker as the first expense/invoice processing system for Varona GmbH.

## Setup Checklist

- [ ] Create or clone the TaxHacker setup.
- [ ] Review installation requirements.
- [ ] Decide hosting approach: local first or cheap VPS.
- [ ] Configure AI provider.
- [ ] Configure document upload.
- [ ] Configure categories.
- [ ] Add Varona expense fields.
- [ ] Add custom extraction prompt.
- [ ] Upload 10 test documents.
- [ ] Review extracted fields.
- [ ] Correct wrong fields.
- [ ] Export CSV/Excel.
- [ ] Check whether export is accountant-ready.
- [ ] Document limitations.
- [ ] Decide whether TaxHacker is enough or needs extension.

## Hosting Decision

Start with the cheapest/simplest option.

Preferred first:

```txt
Local Docker install
```

Only move to VPS if Paula needs access from anywhere.

## AI Provider

Possible options:

```txt
OpenAI
Gemini
Mistral
Ollama
```

Initial recommended path:

```txt
OpenAI or Gemini for best extraction quality
```

## First Test Batch

Upload:

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

## Pass/Fail Criteria

TaxHacker passes the MVP if:

- [ ] At least 8/10 documents are classified correctly.
- [ ] Amount and currency are correct in at least 9/10 documents.
- [ ] Supplier is correct in at least 9/10 documents.
- [ ] Export works without manual reformatting.
- [ ] Accountant can understand the register.
- [ ] Paula can review/correct fields visually.
