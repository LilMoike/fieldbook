# Fieldbook

**Quote → job → invoice → paid, in one place.** Fieldbook is a small-business app for one-to-five-person trades and service businesses: handymen, painters, cleaners, landscapers, contractors.

Most tools in this space cost $30+/month and bury the basics under features. Fieldbook does the core loop well and works on any device with a browser.

**[Try the live demo →](https://lilmoike.github.io/fieldbook/)**

![Fieldbook overview screen](docs/overview.png)

## What it does

| Stage | Features |
|---|---|
| **Quote** | Line items for labour, materials and flat fees · one-click price book · 13% HST calculated automatically · draft → sent → accepted / declined, with sent quotes locked against edits |
| **Job** | Accepted quotes become work orders · scheduled date · checklist · site notes (door codes, paint colours) · extra work found on site carries over to the invoice |
| **Invoice** | Created from a finished job in one click · Net 0 / 7 / 15 / 30 / 45 terms · partial payments · overdue tracking · "Copy as text" to paste into an email or text · print or save as PDF |
| **Deposits** | Request a deposit (30% by default) on an accepted quote or booked job · paid deposits are credited automatically on the final invoice · unpaid deposits are voided when the final invoice replaces them |
| **Getting paid** | Friendly or overdue reminder messages, written for you and logged · late fees at a set % per month, at most once every 30 days and never taxed · a full activity log on every invoice |
| **Tax** | Correct sales tax for every province and territory (HST, GST + PST, GST + QST) · switch tax off per line · every document keeps the rate it was created with, so changing settings never rewrites old invoices |
| **Discounts** | Percentage or dollar discounts, applied before tax |
| **Overview** | Money at each stage of the pipeline, and a *Needs attention* list: overdue invoices (with when you last sent a reminder), finished jobs not yet invoiced, quotes with no reply after 7 days, unsent drafts |
| **Receivables** | An aging report that groups unpaid balances into current, 1–30, 31–60, 61–90 and 90+ days overdue |

It also includes a client list with each client's full history and balance owing, light and dark themes, and a phone layout with a bottom tab bar.

## How it's built

- **One file, no build step, no framework.** It's plain HTML, CSS and JavaScript in [`index.html`](index.html).
- **Money is handled in integer cents** so totals and tax never drift from floating-point rounding.
- **Invoices are never deleted once sent.** They're voided instead, so invoice numbers have no gaps, as bookkeeping expects.
- **Status is derived, not stored.** An invoice's status (draft, sent, part paid, overdue, paid) is computed from its payments, due date and sent flag, so it can't fall out of sync.
- **Data lives in the browser** (`localStorage`). Sample data is generated relative to today's date, so the demo always looks current. *Reset sample data* restores it.
- **Responsive and accessible.** Keyboard focus states, labelled controls, `prefers-reduced-motion` and `prefers-color-scheme` support, and phone safe-area handling.

## Run it locally

Download `index.html` and open it in any browser. That's it.

## Roadmap

- Sync across devices (e.g. Supabase) so a crew can share one account
- Installable PWA with offline support
- Email quotes and invoices directly, with an "Accept quote" link for clients
- Recurring invoices for maintenance contracts
- Client statements listing every open invoice
- Card payments through Stripe or Square

## Note

All businesses, clients, phone numbers (555-01xx) and email addresses in the sample data are fictional.

## License

[MIT](LICENSE)
