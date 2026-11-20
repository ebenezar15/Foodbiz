# Batch & Price

A costing, pricing, order, stock and billing app for home food businesses: brownies, cookies, cakes, Indian sweets, snacks, pickles and home meals. All amounts are in rupees.

**Live app: https://foodbiz-ashy.vercel.app/**

It is a static web app (no server, no build step). Host it on Vercel, open the link on your phone and install it to the home screen. It then opens like an app and works offline.

## Put it online with Vercel

1. Go to [vercel.com/new](https://vercel.com/new) and sign in with GitHub.
2. Import the **ebenezar15/foodbiz** repository. Leave the framework preset as **Other**, with no build command and no output directory.
3. Click **Deploy**. Every push to the repository's default branch now deploys automatically.
4. Open the `….vercel.app` address on your phone and install it:
   - **Android (Chrome):** ⋮ menu → **Install app** (or **Add to Home screen**).
   - **iPhone (Safari):** Share button → **Add to Home Screen**.

## Back up to your Gmail / Google account

Data lives on the device. Two ways to keep a copy in your Google account:

- **Email the backup** (works straight away): Setup → Your data → **Email the backup**. On a phone, choose Gmail and send it to yourself. To restore, open the email on the new device, save the attachment, then Setup → Your data → Restore → choose the file.
- **Google Drive backup** (one-time setup): saves the backup file to your Google Drive and restores it with one tap. It needs a Google OAuth client ID:
  1. In [Google Cloud Console](https://console.cloud.google.com/), create a project and enable the **Google Drive API**.
  2. **APIs & Services → OAuth consent screen**: choose *External*, fill in the app name, and add your Gmail address as a test user.
  3. **Credentials → Create credentials → OAuth client ID**, type **Web application**. Under *Authorised JavaScript origins* add `https://foodbiz-ashy.vercel.app`.
  4. Put the client ID in `config.js` (`googleClientId: '…apps.googleusercontent.com'`) and push, or paste it in the app under Setup → Your data → *Switch on Google Drive backup*.

  The app asks only for the `drive.file` permission, so it can see only the backup files it created. The last 10 backups are kept.

## Pages

| Page | What it does |
|---|---|
| **Dashboard** | Get-started checklist, this month's sales and profit, break-even status and date, open orders, start-up money paid back, alerts for expired, expiring or low stock and shortages, backup reminder. |
| **Orders** | Orders with due dates, agreed prices, extras, discount and advance. *Mark as made* deducts stock (oldest first, ready stock first); *Delivered & paid* records the sale. The production plan gives batches, measurements, stock left, a shopping list, cash needed, cost and profit. **Bill** makes a PDF invoice to download or share on WhatsApp or Gmail. |
| **Quote** | Price an enquiry, copy a WhatsApp message, download a quotation PDF, turn it into an order. |
| **Pricing** | Break-even, lowest safe, recommended and premium prices; market check; per-kg, delivery-app and GST prices; bulk tiers with margin warnings. |
| **Recipes & cost** | Cost per batch and per piece; change ingredient prices from the recipe; measurements for any quantity. |
| **Stock** | Ingredients (pack price editable inline, price history, bulk % change, purchase lots with expiry, low-stock alerts), packaging stock, ready-to-sell products with best-before dates. Starter lists to begin quickly. |
| **Barcode scan** | Camera, photo or typed number. A known barcode opens *Add stock*; a new one becomes an item, with the name looked up on Open Food Facts when possible. |
| **Money** | Month-by-month break-even and the date it happened, start-up money payback, sales and expense log. |
| **Reports** | Any period (this month, last month, 3 months, financial year, all time, custom): profit, monthly break-even, best sellers, sales by customer type, expenses by category, stock value, expiring items, price changes. Download or share as PDF; export entries and stock as CSV for Excel or Google Sheets. |
| **Shelf life, Packaging, Guide** | Best-before estimator and label text, packaging suggestions with typical prices, pricing rules, FSSAI/GST basics, label checklist. |
| **Setup** | Business questions with suggestions; details printed on bills (address, phone, UPI ID, FSSAI no., GSTIN, bill numbering); dessert colour schemes (Chocolate fudge, Strawberry shortcake, Pistachio kulfi, Blueberry cheesecake, Kesar mango, Red velvet) or your own brand colour; light/dark/auto; spacing and text size; backup, restore and install. |

## How the numbers are worked out

- **Electricity** = oven watts ÷ 1000 × (bake + preheat minutes) ÷ 60 × 0.7 × ₹ per unit.
- **Gas** = stove minutes ÷ 60 × burner kg per hour × (cylinder price ÷ 14.2 kg).
- **Cost per piece** = (ingredients × (1 + wastage) + electricity + gas + labour) ÷ pieces + packaging per piece + monthly fixed costs ÷ pieces sold per month.
- **Price at a margin** = cost ÷ (1 − margin).
- **Measurements for orders** = recipe quantity × pieces ÷ batch size × (1 + wastage), rounded up for items counted in pieces.
- **Month break-even** = sales ≥ logged expenses + fixed costs (+ your pay if set); the date is when running sales first covered running costs.
- **Shelf-life label** = about 70% of the estimated life.

Shelf-life figures and the tax and licence notes are starting points. Confirm shelf life with a home trial or a lab test, and check FSSAI and GST rules with the official portals or a CA.

## Files

| Path | Purpose |
|---|---|
| `index.html` | The whole app (markup, styles and code). |
| `config.js` | Hosting settings (Google client ID for Drive backup). |
| `manifest.webmanifest`, `sw.js`, `icons/` | Install to home screen and offline use. |
| `vendor/` | PDF, barcode and font files, kept locally so the app works offline. See `vendor/LICENSES.md`. |
| `vercel.json` | Caching headers for Vercel. |
