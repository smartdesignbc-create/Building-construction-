# Smart Design Construction — Operations Platform

A premium, single-page business operations platform for a construction contractor, built to replace paper records, notebooks, and manual tracking with one integrated system.

**Status:** Phase 1 — Interactive Browser Demo. Data lives in memory for the session (no backend, auth, or persistent storage yet). Phase 2 will add cloud storage, authentication, and backups.

---

## What's inside

A single self-contained `index.html` file — no build step, no dependencies to install. It loads React, ReactDOM, and Babel from a CDN at runtime and renders the whole app client-side.

**Modules:**
- Dashboard — revenue, expenses, cash flow, outstanding payments, projects, materials alerts, staff overview, today's priorities, recent activity, quick actions
- Customers — full profiles with linked projects, quotations, invoices, payments, documents
- Projects — tasks, milestones, material planning, financial summary, progress tracking
- Quotations — line items, VAT, discounts, PDF preview, one-click conversion to invoice
- Invoices — payment history, outstanding balances, status tracking
- Finance — income, expenses, cash flow, profit summary
- Materials — master catalogue, per-project material planner, procurement tracking
- Staff — trades, skills, current project assignment, availability
- Calendar — site visits, meetings, deliveries, deadlines
- Documents — contracts, plans, photos, receipts, certificates

**Synchronisation:** creating a customer makes them available everywhere; converting a quotation carries its line items into a new invoice; recording a payment updates the invoice, customer history, project financials, and dashboard automatically; project material tracking (required → ordered → delivered → used → remaining) updates as figures change.

---

## Running locally

No install required. Either:

1. Double-click `index.html` to open it directly in your browser, **or**
2. Serve it locally (recommended, avoids any browser file:// restrictions):
   ```bash
   npx serve .
   # or
   python3 -m http.server 8000
   ```
   Then open `http://localhost:8000` (or the port shown).

---

## Deploying to Vercel

**Option A — GitHub integration (recommended)**

1. Push this repo to GitHub (see below).
2. Go to [vercel.com/new](https://vercel.com/new) and import the GitHub repository.
3. Vercel will detect it as a static site automatically — no build command or output directory needed (leave both blank, or set Output Directory to `.`).
4. Click **Deploy**. Vercel will give you a live URL immediately, and will redeploy automatically on every push to your main branch.

**Option B — Vercel CLI**

```bash
npm i -g vercel
vercel login
vercel --prod
```

Run this from inside the project folder. Vercel will pick up `index.html` and `vercel.json` automatically.

---

## Pushing to GitHub

```bash
git init
git add .
git commit -m "Initial commit: Smart Design Construction operations platform"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

---

## Notes for reviewers

- This is a **demo build**: all data resets on page reload. There's no server, no database, and no login — that's intentional for Phase 1.
- The "PDF Preview" buttons on quotations/invoices open a print-formatted view; use your browser's print dialog (Ctrl/Cmd+P → Save as PDF) to export.
- Seeded with sample customers, projects, quotations, and invoices so the app is fully explorable on first load — feel free to edit or delete the sample data.
