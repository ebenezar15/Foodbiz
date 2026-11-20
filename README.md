# Batch & Price

A costing, pricing and tracking app for home food businesses: brownies, cookies, cakes, Indian sweets, snacks, pickles and home meals. All amounts are in rupees.

Open `index.html` in any browser. There is nothing to install or build. Data is saved in that browser; use **Start here → Your data → Copy backup** to move it to another device.

## What it does

| Tab | What you do there |
|---|---|
| **Start here** | Answer setup questions: what you make, where you sell, monthly volume, oven and gas, your hourly rate, fixed costs, target margin, FSSAI and GST. You get suggestions based on your answers and a snapshot of every product's cost, price and margin. |
| **Recipe cost** | Cost of one batch and one piece: ingredients with wastage, oven electricity, gas, hands-on time, packaging per piece and a share of fixed costs. |
| **Pricing** | A four-step price ladder (break-even, lowest safe, recommended, premium), a check against what others charge, per-kg price, delivery-app price, GST, bulk discount tiers with a margin warning on each, break-even volume, and what a 10% ingredient price rise would do. |
| **Quote** | A quote for an individual or bulk customer with tier discounts, custom packaging, rush charge, delivery, GST and advance. Produces a WhatsApp-ready message and can record the order as a sale. |
| **Tracker** | Sales and expenses by month, a six-month chart, spending by category and warnings when ingredients or packaging take too much of sales. |
| **Ingredients & packaging** | Pack prices for ingredients and packaging items, the cost per kg, litre or piece, and the date each price was last updated. |
| **Shelf life** | A cautious best-before estimate from product type, climate, moisture, packing and risky ingredients, plus label text and a home-trial method. |
| **Packaging** | Suggested packaging and typical prices by product, purpose (everyday, gift, bulk) and distance (local, city, courier). |
| **Guide** | Questions to ask before pricing, pricing rules, individual vs bulk vs café customers, FSSAI and GST basics, label requirements, shelf life and packaging. |

## How the numbers are worked out

- **Electricity** = oven watts ÷ 1000 × (bake + preheat minutes) ÷ 60 × 0.7 × ₹ per unit. The 0.7 allows for the thermostat cycling off.
- **Gas** = stove minutes ÷ 60 × burner kg per hour × (cylinder price ÷ 14.2 kg).
- **Cost per piece** = (ingredients × (1 + wastage) + electricity + gas + labour) ÷ pieces + packaging per piece + monthly fixed costs ÷ pieces sold per month.
- **Price at a margin** = cost ÷ (1 − margin). Delivery-app prices also divide out the commission.
- **Shelf-life label** = about 70% of the estimated life, so there is always a safety margin.

Sample prices, shelf-life figures and the tax and licence notes are starting points. Replace the prices with your own bills, confirm shelf life with a home trial or a lab test, and check FSSAI and GST rules with the official portals or a CA.
