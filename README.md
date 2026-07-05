# Pacific Biomedical — Quote Builder

A single, self-contained HTML file for producing branded quotations for **Pacific Biomedical & Consulting Services Pty Ltd**. No install, no server, no internet required. Open `pbcs-quote-builder.html` in any modern browser and it runs.

Branded to match the Pacific Biomedical style: navy `#1F3864`, light-blue tables, Calibri, and the PBCS globe logo baked in.

---

## Quick start

1. Open `pbcs-quote-builder.html` in Chrome, Edge, Safari or Firefox.
2. **Settings** → enter your ABN, phone, confirm the address, and save.
3. **Rate Library** → set your real prices (they start as editable placeholders).
4. **Currencies** → update the FX rates to current figures.
5. **Settings → Export backup** → keep a safe `.json` copy.

Then build quotes from the **New Quote** tab.

---

## Where your data lives

Everything you enter — quotes, clients, rates, currencies and settings — is stored in **`localStorage` in the browser on the computer you're using**. It is not sent anywhere.

- To move data between computers, or keep a safe copy: **Settings → Export backup** produces a portable `.json`, and **Import backup** restores it.
- Persistence works once the file is opened **from your own computer** or **hosted** (e.g. a GitHub Pages subfolder like `/quotes/index.html`). In an in-chat preview it runs fine but won't remember data between reloads — use Export backup either way.

---

## Tabs

| Tab | What it does |
|-----|--------------|
| **New Quote** | Build a quote; subtotal → discount → tax → grand total update live. Quote numbers auto-run as `PBC-Q-2026-001`. |
| **Saved Quotes** | Every saved quote with a status badge (Draft / Sent / Accepted / Declined). Open, copy or delete. |
| **Rate Library** | Reusable rates + equipment catalogue (seeded from live pacificbiomed.com.au prices). Click **Use** to drop any item into the current quote. Edit prices in place. |
| **Currencies** | Pacific nations with editable FX rates and optional per-nation labour rates. |
| **Settings** | Company details, ABN, number prefix, default GST / validity / terms, plus backup / import / reset. |
| **Help** | The same guidance, in-app. |

---

## Key features

### Equipment catalogue (live prices)
Seeded from the current pacificbiomed.com.au refurbished-equipment prices:

- Fresenius Kabi Injectomat MC Agilia syringe pump — **$749**
- Fresenius Kabi Injectomat TIVA Agilia syringe pump — **$989**
- Fresenius Kabi Volumat MC Agilia infusion pump — **$549**
- GE B30 patient monitor — **$789**
- GE Carescape R860 ventilator (new / unused) — **price on application**

All editable in the Rate Library.

### Tender mode
A toggle on each quote that reveals NSW Health / government fields — tender/RFQ reference, contract or panel number, delivery lead time, warranty period, and a conformance statement. It defaults validity to **90 days** and prints a tender header block on the PDF.

### Per-quote tax treatment
- **GST 10% (domestic)**
- **GST-free (export / overseas)** — Australian goods and services exported to Pacific facilities are generally GST-free
- **Custom rate**

Selecting a non-AUD currency automatically switches to GST-free (override any time).

### Multi-currency with per-nation labour
Line-item prices are always entered in **AUD**. Pick a quote currency and the grand total is also shown converted at the FX rate, stamped **"rate as at [date]"** on the PDF. Preloaded nations: Fiji (FJD), Papua New Guinea (PGK), Solomon Islands (SBD), Vanuatu (VUV), Samoa (WST), Tonga (TOP), plus Australia (AUD).

FX rates are **manual** — this is an offline file with no live feed, so update them occasionally under the Currencies tab. Each nation can carry an optional local labour rate.

### Payment schedule (deposit / progress payments)
Turn on **Use schedule** for equipment + install jobs. Default split is **30% deposit / 40% on delivery / 30% on commissioning**, fully editable; percentages should total 100%. The schedule prints on the quote as a milestone table.

### John Hunter sample
The **Load John Hunter sample** button fills a worked example: an NSW Health tender (`HNELHD-RFQ-2026-0483`) for a patient-monitoring upgrade at John Hunter Hospital — 12 GE B30 bedside monitors plus modules, central stations, installation, commissioning, safety testing, training and asset documentation. It demonstrates tender mode, an equipment + install line-item mix, a discount, and the payment schedule together. (Subtotal $43,898 − $1,500 discount + 10% GST = **$46,637.80**.)

### Print / Export PDF
Produces a clean client-facing document — logo lockup, navy rule, `QUOTATION` masthead, category-tagged line items, discount / tax / grand-total stack, optional tender header and payment schedule, terms, and dual signature blocks. Use your browser's **Save as PDF** option.

---

## Hosting alongside the other study tools

Drop the file into a GitHub Pages subfolder, e.g.:

```
/quotes/index.html
```

and share the link. Because it's a single file with no dependencies, nothing else needs to be uploaded.

---

## Reset

**Settings → Reset all data** restores factory defaults (catalogue, nations, terms) and clears all quotes and clients. This cannot be undone — export a backup first.
