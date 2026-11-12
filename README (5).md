# Asian Paints Valuation: DCF and Comparable Companies

An Excel valuation of **Asian Paints Ltd** (NSE: ASIANPAINT) using a 10-year discounted cash flow (DCF) model and a comparable-company (trading multiples) analysis against listed Indian paint peers. Every output is formula-driven from a single Assumptions sheet, so you can change an input and the whole model updates.

> Educational project. Not investment advice.

## Headline results

| Method | Low | Base / Median | High |
|---|---|---|---|
| DCF (Low: WACC 12.5%, g 5.5% / High: WACC 11.0%, g 6.5%) | ₹915 | **₹1,097** | ₹1,351 |
| EV/EBITDA, peer multiples (low / median / high) | ₹910 | ₹1,066 | ₹1,778 |
| P/E, peer multiples (low / median / high) | ₹1,093 | ₹1,229 | ₹2,007 |
| Market price (BSE close, 6 Nov 2026) | | ₹2,542 | |

- Base-case DCF value is about **57% below** the market price.
- Asian Paints trades at **45.3x P/E** and **27.9x EV/EBITDA**, a premium of about **66%** and **79%** to the peer median.
- Terminal value is **65% of enterprise value**, so the result is very sensitive to WACC and terminal growth (see the Sensitivity sheet).
- Interpretation: the market is pricing in faster growth, higher margins or a lower discount rate than the base case assumes.

## Repository contents

```
asian-paints-valuation/
├── README.md
└── model/
    └── Asian_Paints_Valuation_DCF_Comps.xlsx
```

### Workbook sheets

| Sheet | What it contains |
|---|---|
| Summary | Valuation comparison table, key results, takeaways, chart |
| Assumptions | All inputs (blue = input, yellow = key assumption), WACC build, forecast drivers |
| Historical | FY2022-FY2026 consolidated financials and ratios |
| DCF | 10-year unlevered free cash flow forecast, terminal value, equity bridge |
| Sensitivity | Value per share and upside/downside across WACC (10-13%) and terminal growth (5-7%) |
| Comps | Peer multiples, implied Asian Paints value from peer EV/EBITDA and P/E |
| Notes | Sources, method and limitations |

## Methodology

**DCF (FCFF)**
- Forecast FY2027E-FY2036E: revenue growth, EBITDA margin, D&A, capex and working-capital investment.
- Unlevered free cash flow = EBIT x (1 - tax) + D&A - capex - increase in net working capital.
- Discounted at WACC with end-of-year discounting, anchored to the 31-Mar-2026 balance sheet.
- Terminal value by Gordon growth: FCF(FY36) x (1 + g) / (WACC - g).
- Equity value = enterprise value + cash and investments - debt (including leases) - minority interest, divided by 95.92 Cr shares.

**Comparable companies**
- Peers: Berger Paints, Kansai Nerolac, Indigo Paints.
- Low / median / high peer P/E and EV/EBITDA applied to Asian Paints FY2026 net income and EBITDA.
- JSW Dulux (formerly Akzo Nobel India) is excluded because its reported multiples are distorted by one-off items.

## Key assumptions (base case)

| Assumption | Value | Basis |
|---|---|---|
| Risk-free rate | 7.39% | India 10Y G-Sec yield, 29 Oct 2026 |
| Equity risk premium | 5.5% | Analyst assumption |
| Beta | 0.80 | Analyst assumption (verify with a data provider) |
| Cost of equity | 11.79% | CAPM |
| WACC | 11.70% | Market-value weights (debt is about 1.6% of capital) |
| Terminal growth | 6.0% | Analyst assumption |
| Revenue growth | 12.0% in FY27E, fading to 8.0% by FY36E | Recent quarterly growth, fade to maturity |
| EBITDA margin | 18.8% rising to 21.0% | FY26 17.7%, Q4 FY26 19.3% |
| Capex / revenue | 4.0% fading to 3.5% | FY26 4.1% |
| Tax rate | 26% | FY22-FY26 effective rate average |

## How to use

1. Open `model/Asian_Paints_Valuation_DCF_Comps.xlsx` in Excel (or LibreOffice).
2. Go to **Assumptions** and edit the blue input cells. Update the share price (`C5`) to the latest close before using.
3. Review **Summary**, **DCF** and **Sensitivity**; they recalculate automatically.

## Data sources

- Consolidated financials FY2022-FY2026: S&P Global Market Intelligence via StockAnalysis.com (INR million converted to INR crore). Cross-check against the Asian Paints annual report.
- Share price: BSE close, 6 Nov 2026 (StockAnalysis.com).
- Peer and Asian Paints market multiples: Upstox, 2-4 Nov 2026 (third-party aggregator; EBITDA definitions may differ from company filings).
- Risk-free rate: India 10-year G-Sec yield, 29 Oct 2026.

## Limitations

- Beta, equity risk premium, margin path, capex and working-capital ratios are judgement-based assumptions.
- Only three listed peers; multiples come from an aggregator and are not adjusted for accounting differences.
- End-of-year discounting with no stub-period adjustment; long-term investments (about ₹1,929 Cr) are not added to equity value, which is conservative.
- Market data is as of early November 2026 and will go stale.

## Skills demonstrated

Financial modelling, DCF valuation, WACC / CAPM, terminal value, comparable-company analysis, sensitivity analysis, Excel (formula-driven model design).

## Disclaimer

This project is for educational purposes only and is not investment advice.
