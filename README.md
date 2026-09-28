# RR Creation — Studio OS frontend demo

A connected, client-specific tailoring CRM based on RR Creation's measurement and invoice sheet. Built by Known State as a frontend-only demonstration.

## Open the demo

Open `dist/index.html` in a modern browser. Keep `data.js`, `app.js`, `style.css`, and `assets/` with it.

For consistent browser storage behaviour, serve the folder instead:

```sh
python3 -m http.server 4173 --directory dist
```

Then open http://localhost:4173. No installation, API keys or backend are needed.

## Presentation walkthrough

1. Start at **Studio overview**. Click deliveries, fittings, overdue work or outstanding balances to see the relevant orders.
2. Search **Priya**, **KS-0142**, **4273** or **RR-4273** using the top search bar (Cmd/Ctrl+K).
3. Open the customer **Measurements** tab. Compare fitting versions; record a new fitting in inches or centimetres.
4. Create a **Repeat / new order**. Select a saved fitting, add multiple garments, quantities and rates, choose the tailor and dates, and record an advance.
5. Open **Production board**. Open the job and move it through Confirmed, Cutting, Stitching, Fitting, Ready and Delivered.
6. Add design-reference images and record any fitting alteration. The original order's measurement snapshot remains unchanged.
7. Record later payments. Balances update across the order, customer and invoices. Overpayment is prevented.
8. Preview the invoice, use **Print / save PDF**, and print a production job sheet if needed.
9. Mark delivery. An unpaid handover requires confirmation; delivery never clears a balance automatically.
10. Try reminder previews, quotation conversion, creation photographs and the customer-facing website preview.

Use **Walk through an order** in the sidebar for an in-app guide. On mobile, scroll the navigation horizontally. Tables, fitting stages and the production board also scroll horizontally where needed.

## Exact paper fields

The photograph has **22 fields**, not 23:

- Upper garment (14): Length, Upper Chest, Pointing, Chest, Waist, Hip, Down, Shoulder, Armhole, Hand Length, Upper Hand Mouri, Hand Mouri, Front Neck, Back Neck.
- Salwar (8): Length, Waist, Hip, Thai, Knee, Cluff, Leg Mouri, Fog.

Printed terminology is retained; blank measurements are not treated as zero. Each order stores its own measurement snapshot. Changing a later fitting does not overwrite the job.

## Demo data and persistence

- Fictional customer and order records. Sample schedules are anchored to the day the demo is first opened or reset.
- Edits, payment entries and compressed reference images are stored only in the current browser under `rr-creation-demo-v2`.
- The previous Known State demo's customer records, measurement history, quotes, creations, activities and follow-up tasks are migrated on first opening the upgrade on the same origin. The old `knownstate-demo-v1` storage is left untouched. New sample orders are clearly part of the demo.
- Use **Reset sample workspace** or **Studio settings → Reset sample workspace** to restore RR Creation samples. This removes this version's local edits and uploaded images after confirmation.
- JPG, PNG and WebP uploads are compressed locally; six references per order, 8 MB input maximum. Browser quota limits still apply. A warning appears if persistence fails.
- Different browsers, the downloaded file, the local server and the hosted URL have separate storage. Demo edits do not synchronise across them.

## Scope and limitations

There is no backend, login, authentication, secure role enforcement, shared staff storage, cloud backup, message delivery, payment gateway, or tax invoicing system. Owner/Tailor switching demonstrates interface visibility only. Payments are simulated entries; enquiries and reminders are previews and never sent. The printable bill is labelled as a demo, not a tax invoice.

Business details and the two printed terms are transcribed from the supplied RR Creation sheet and editable in Studio settings. Verify them with the business before real use. Existing garment records without a photo use a category icon; the website photograph comes from the original supplied catalogue.

## Files

- `dist/index.html` — app shell
- `dist/style.css` — desktop, mobile and print styles
- `dist/data.js` — sample records, measurement fields and legacy migration
- `dist/app.js` — connected interface and interactions
- `dist/assets/atelier.jpg` — supplied catalogue image
