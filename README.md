# Swt-er

A costing, pricing, order, stock and billing app for home food businesses: brownies, cookies, cakes, Indian sweets, snacks, pickles and home meals. All amounts are in rupees.

**Live app: https://swt-er.vercel.app/**

Share this link with anyone who should install Swt-er. They open it on their phone and follow the steps below (or More → Install app inside Swt-er).

It is a static web app (no server, no build step). Host it on Vercel, open the link on your phone and install it to the home screen. It then opens like an app and works offline.

## Put it online with Vercel

The project deploys from GitHub automatically on every push.

**Use the address swt-er.vercel.app** (one-time, in your Vercel account):
1. Open [vercel.com](https://vercel.com), sign in, and click the **foodbiz** project.
2. Go to **Settings → Domains**.
3. Type `swt-er.vercel.app` and click **Add**. Vercel connects it within a minute.
4. Optional: **Settings → General → Project Name**, rename it to `swt-er`.

The live address is **swt-er.vercel.app**. Older addresses (`foodbiz-ashy.vercel.app`, `swe-tr.vercel.app`) are no longer in use.

## Install on your phone (step by step)

The app also has this guide built in: **More → Install app**.

### Android (Chrome)
1. Open **Chrome** and go to **swt-er.vercel.app**.
2. Link your Gmail and set your fingerprint or PIN when Swt-er asks.
3. Tap **Install** on the banner at the top of the Dashboard. No banner? Tap the **⋮** menu (top right), then **Install app** or **Add to Home screen**.
4. Tap **Install** again to confirm.
5. Open **Swt-er** from your home screen or app drawer. It opens full screen and works offline.

*Samsung Internet:* tap **☰** (bottom right) → **Add page to** → **Home screen**.

### iPhone or iPad (Safari)
1. Open **Safari** and go to **swt-er.vercel.app**.
2. Tap the **Share** button (square with an up arrow) at the bottom of the screen (top on iPad).
3. Scroll down and tap **Add to Home Screen**.
4. Keep the name **Swt-er** and tap **Add**.
5. Open **Swt-er** from your home screen, then link your Gmail and turn on Face ID or Touch ID lock.

On iPhone the home-screen app keeps its own data, separate from Safari. If you already used Swt-er in Safari, email yourself a backup first (Setup → Your data → Email the backup) and restore it inside the installed app.

**To remove the app:** press and hold the Swt-er icon, then **Uninstall** (Android) or **Remove App** (iPhone). Back up first.

## Signing in

- **First time:** link your Gmail (type it, or tap *Continue with Google* once the Google client ID is set up). Backups go to this address.
- **Then choose a lock:** fingerprint, face or the phone's own screen lock (PIN/pattern), using the phone's passkey support; or a 4–6 digit app PIN. You can set both.
- **Every time you open Swt-er** it asks for the fingerprint or PIN. It locks again after you leave the app for a set time (Setup → Account & lock: right away, 1, 5 or 15 minutes).
- **Can't unlock?** Sign in again with the same Google account (when the client ID is set up), or erase this phone's copy and restore your latest backup.
- The lock keeps other people out of the app on your phone. Data is stored in the phone's browser, so keep the phone's own screen lock on and back up regularly.

## Back up to your Gmail / Google account

Data lives on the device. Two ways to keep a copy in your Google account:

- **Email the backup** (works straight away): Setup → Your data → **Email the backup**. On a phone, choose Gmail and send it to yourself. To restore, open the email on the new device, save the attachment, then Setup → Your data → Restore → choose the file.
- **Google Drive backup** (one-time setup): saves the backup file to your Google Drive and restores it with one tap. It needs a Google OAuth client ID:
  1. In [Google Cloud Console](https://console.cloud.google.com/), create a project and enable the **Google Drive API**.
  2. **APIs & Services → OAuth consent screen**: choose *External*, fill in the app name, and add your Gmail address as a test user.
  3. **Credentials → Create credentials → OAuth client ID**, type **Web application**. Under *Authorised JavaScript origins* add `https://swt-er.vercel.app`.
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
| `brand/` | Swt-er logo files used in the app, on the home-screen icon and on PDF bills (`icons/` is made from the round S icon). |
| `vendor/` | PDF, barcode and font files, kept locally so the app works offline. See `vendor/LICENSES.md`. |
| `vercel.json` | Caching headers for Vercel. |
