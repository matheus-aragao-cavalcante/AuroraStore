# Payment Gateway Routing: Financial BI Case Study

**Fictional e-commerce (Aurora Store) · Power BI + HTML report · 25,728 orders · Jan 2025 to Sep 2026**

## The problem
Most Brazilian online stores send every payment through a single gateway. But each gateway prices Pix, credit and debit differently: some charge a percentage, some a fixed fee, some a mix with minimums and caps. One gateway is never the cheapest for every sale.

## The approach
I compared four Brazilian gateways with no monthly fees (Asaas, Mercado Pago, Inter PJ, InfinitePay) using their standard public fees, and simulated a **routing rule**: each order goes to the cheapest gateway for its payment method and ticket size.

- Pix → InfinitePay (0%)
- Credit card → InfinitePay up to R$ 40.50, Asaas above
- Debit card → Mercado Pago up to R$ 16.67, Asaas above

## Results (fictional data, Jan 1, 2025 to Sep 30, 2026)
| Scenario | Payment fees | Net profit |
|---|---|---|
| Mercado Pago only (current setup) | R$ 114,013 (3.09%) | R$ 386,733 |
| Asaas only (best single gateway) | R$ 87,071 (2.36%) | R$ 413,675 |
| **Multi-gateway routing** | **R$ 62,471 (1.69%)** | **R$ 423,975** |

- **+R$ 37,242 net profit (+9.6%)** vs the current setup, after deducting R$ 14,300 in routing setup and maintenance
- **+R$ 10,300** even vs the best single gateway
- **+R$ 251,389 projected over 5 years** (15% yearly growth)

## What's inside
- **Interactive HTML report:** Revenue, Costs and Results pages with KPI cards, weekly/monthly/YoY comparisons, top products, expense breakdown, side-by-side income statement and 5-year projection
- **Power BI version:** DAX measures that render the same report through the HTML Content visual (pure HTML/CSS charts, slicer-aware)
- **Dataset (.xlsx):** Sales, Products, Expenses, Targets, Employees, Payment_Fees

## Tech
Power BI · DAX (dynamic HTML generation, table constructors, CONCATENATEX) · JavaScript · HTML/CSS · Excel · financial modeling

## Caveats
All company data is fictional. Gateway fees are standard public rates checked on Sep 30, 2026, without volume discounts. Settlement times differ (e.g., Asaas card funds are not instant). Taxes estimated at 8% of revenue. Not financial advice.
