# Photo Studio Business Analysis

A financial and operational analysis of a SME photo studio business based in Indonesia. This project examines 13 months of bank transaction data (January 2025 – January 2026) alongside customer booking records to assess the studio's financial health, operational patterns, and growth trajectory.

> **Note:** The Jupyter Notebook contains only the code used to perform the analysis. The complete report — including written interpretations, findings, and strategic recommendations — is documented in a separate PDF file.

---

## Overview

The analysis is split into two main parts:

### Part 1 — Bank Statement Analysis
Explores the studio's financial performance using categorized bank transaction data pulled from a Supabase database.

- **Descriptive statistics**: Data types, category/subcategory breakdowns, and summary metrics
- **Cash balance (Saldo) trend**: Linear regression on cumulative balance over time, showing a daily growth of ~Rp. 20,659
- **Revenue analysis**: Monthly income broken down by subcategory (photo sessions, events, etc.)
- **Expense breakdown**: Costs categorized across Personnel, Operations, Marketing, Direct, Equipment, Financial, and Tax
- **Net cashflow**: Monthly net cashflow with identification of positive vs. negative months; total annual net cashflow of Rp. 4.03 Jt (~Rp. 310K/month average)
- **Growth projections**: Linear forecast vs. an exponential target of Rp. 200 Jt by end of 2026

### Part 2 — Booking Spreadsheet Analysis
Examines customer booking behavior using a cleaned and restructured CSV export from the studio's booking system.

- **Data cleaning**: 13-step cleaning and restructuring pipeline applied to raw booking data
- **Booking statistics**: Overall booking rate of 98.3%; breakdown of booking vs. non-booking entries
- **Monthly trends**: Monthly booking volumes and trend lines
- **Discount impact**: Effect of discounts (0%, 20%, 25%, 30%, 50%) on booking volume; non-discounted stable baseline of ~29 bookings/month
- **Weekday patterns**: Saturday and Sunday are peak days
- **Hourly patterns**: Saturday peaks at 14:00–15:00; Sunday peaks at 11:00
- **Repeat customer analysis**: Repeat customers identified via email and WhatsApp; majority of customers are first-time visitors, with less than 30% returning

---

## Key Findings

- Business growth is stagnant with a low average monthly net cashflow
- Revenue fluctuates cyclically; a linear model may underestimate future variance
- Marketing spend appears to correlate with revenue increases in subsequent months
- Fixed costs (personnel + operations) remain relatively stable month-to-month
- High customer acquisition but low retention — growing repeat customers is a key opportunity
- Reaching the Rp. 200 Jt EOY 2026 target would require significant strategic changes

---

## Data Sources

| Source | Description |
|--------|-------------|
| Supabase (`transactions` table) | Categorized bank transaction records (Jan 2025 – Feb 2026) |
| Booking CSV | Customer booking records exported from the studio's booking system |

---

## Libraries Used

| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation and analysis |
| `numpy` | Numerical operations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical data visualization |
| `statsmodels` | Linear regression and statistical modeling |
| `supabase` | Database connection to fetch transaction data |
| `python-dotenv` | Managing environment variables (database credentials) |
| `re` | Regular expressions for data cleaning |

---

## Repository Structure

```
photo_studio_analysis/
├── photo_studio_analysis_notebook.ipynb   # Analysis code
└── README.md
```

---

## Notes

- Database credentials are managed via a `.env` file (not included in this repository)
- The full written report, including charts, interpretations, and recommendations, is available as a separate PDF document
- Analysis was conducted as of February 22, 2026
