# Batch & Price

A costing, pricing, order and stock app for home food businesses: brownies, cookies, cakes, Indian sweets, snacks, pickles and home meals. All amounts are in rupees.

Open `index.html` in any browser on a phone, tablet or computer. There is nothing to install or build. Data is saved in that browser; use **Setup → Your data** to download a backup or move it to another device.

## Pages

| Page | What it does |
|---|---|
| **Dashboard** | This month's sales and profit, whether you have broken even (and on what date), open orders, start-up money paid back, and everything that needs attention: expired or expiring stock, low stock, shortages for open orders, overdue orders. |
| **Orders** | Add orders with due dates, quantities and agreed prices (filled in from your price and bulk discount). Mark them *made* (stock is deducted, oldest first, ready stock used first) and *delivered & paid* (sale is recorded). The production plan totals all open orders into batches, exact measurements, stock left after, a shopping list, cash needed, cost and expected profit. |
| **Quote** | Price an enquiry for an individual or bulk customer, copy a WhatsApp message, then turn it into an order. |
| **Pricing** | Break-even, lowest safe, recommended and premium prices; market check; per-kg, delivery-app and GST prices; bulk tiers with a margin warning on each. |
| **Recipes & cost** | Cost per batch and per piece (ingredients with wastage, oven, gas, your time, packaging, overheads). Change an ingredient's price from the recipe. *Measure for any quantity* gives weighed amounts for any number of pieces. |
| **Stock** | Ingredients with pack price (editable inline), cost per kg, stock on hand, purchase lots with expiry dates, low-stock alerts and price history. Change several prices at once by a percentage. Packaging stock. *Ready to sell* products made ahead, with best-before dates. |
| **Barcode scan** | Scan with the camera, from a photo, or type the number. A known barcode opens *Add stock* for that ingredient with its price ready to update. A new one becomes an ingredient or packaging item; name and pack size are looked up on Open Food Facts when the network allows. Barcodes do not carry prices, so you type the price from the pack or bill once. |
| **Money** | Month-by-month break-even (sales against expenses plus fixed costs and, optionally, your own pay), the date each month broke even, start-up money payback with a projection, sales and expense log, spending by category, CSV export. |
| **Shelf life, Packaging, Guide** | Best-before estimator with label text and a home-trial method; packaging suggestions with typical prices; pricing rules, FSSAI/GST basics, label requirements, stock habits. |
| **Setup** | Business questions with suggestions; appearance (five colour schemes or your own brand colour, light/dark/auto, compact spacing, text size); backup and restore. |

## How the numbers are worked out

- **Electricity** = oven watts ÷ 1000 × (bake + preheat minutes) ÷ 60 × 0.7 × ₹ per unit.
- **Gas** = stove minutes ÷ 60 × burner kg per hour × (cylinder price ÷ 14.2 kg).
- **Cost per piece** = (ingredients × (1 + wastage) + electricity + gas + labour) ÷ pieces + packaging per piece + monthly fixed costs ÷ pieces sold per month.
- **Price at a margin** = cost ÷ (1 − margin).
- **Measurements for orders** = recipe quantity × pieces ÷ batch size × (1 + wastage), rounded up for items counted in pieces.
- **Month break-even** = sales ≥ logged expenses + fixed costs (+ your pay if set). The date is when running sales first covered running costs.
- **Shelf-life label** = about 70% of the estimated life.

Sample prices, shelf-life figures and the tax and licence notes are starting points. Replace prices with your own bills, confirm shelf life with a home trial or a lab test, and check FSSAI and GST rules with the official portals or a CA.

The live camera needs the page to be opened over `https://` or from a local file in Chrome, Edge or Safari. Where the camera is not allowed, take a photo of the barcode instead.
