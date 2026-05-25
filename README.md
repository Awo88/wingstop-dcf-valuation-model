# Wingstop (WING) — DCF Valuation Model

A from-scratch discounted cash flow model built in Excel to estimate the intrinsic value of Wingstop Inc. (NASDAQ: WING), a pure-play franchise restaurant company.

-----

## Why Wingstop

Wingstop operates an asset-light franchise model with ~2,200 locations globally. Nearly all revenue comes from royalties, franchise fees, and technology fees rather than company-owned restaurants — making cash flows relatively predictable and well-suited to a DCF framework. The company has grown system-wide sales at a ~20% CAGR over the past four years and is expanding aggressively in international markets.

-----

## Model Structure

|Sheet               |Contents                                                                    |
|--------------------|----------------------------------------------------------------------------|
|**Assumptions**     |All hardcoded inputs — growth rates, margins, WACC components, share data   |
|**Income Statement**|Historical P&L (FY2021–FY2024) from 10-K filings + 5-year projections       |
|**FCF Build**       |Unlevered free cash flow bridge (NOPAT → UFCF)                              |
|**WACC**            |CAPM-based cost of equity, after-tax cost of debt, blended WACC             |
|**DCF Valuation**   |PV of FCFs, Gordon Growth terminal value, equity bridge, implied share price|
|**Sensitivity**     |Two-way tables: WACC × terminal growth rate and WACC × EBITDA margin        |

-----

## Key Assumptions

|Input                   |Value |Source                              |
|------------------------|------|------------------------------------|
|Revenue growth (FY2025E)|15.5% |Based on unit growth + SSSG trends  |
|EBITDA margin (FY2025E) |29.5% |In line with FY2024 reported margins|
|Terminal growth rate    |3.0%  |Conservative long-run nominal GDP   |
|WACC                    |~8.5% |CAPM + blended capital structure    |
|Risk-free rate          |4.3%  |10-yr UST, May 2026                 |
|Equity risk premium     |4.6%  |Damodaran US ERP, January 2026      |
|Levered beta            |1.18  |5-year monthly regression vs S&P 500|
|Net debt                |$316mm|From FY2024 10-K balance sheet      |
|Diluted shares          |28.5mm|FY2024 10-K                         |

-----

## Output

|Metric                 |Value                    |
|-----------------------|-------------------------|
|Sum of PV (FCFs)       |Calculated in model      |
|PV of Terminal Value   |Calculated in model      |
|**Implied Share Price**|**See DCF Valuation tab**|
|Sensitivity range      |See Sensitivity tab      |

The sensitivity analysis stress-tests the implied price across WACC assumptions from 7.5% to 10.0% and terminal growth rates from 2.0% to 4.0%.

-----

## Data Sources

- Wingstop 10-K FY2024 — [SEC EDGAR](https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=WING&type=10-K)
- Wingstop 10-K FY2023 — [SEC EDGAR](https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=WING&type=10-K)
- Damodaran Online — US Market Risk Premium & Beta (January 2026)
- FRED — 10-Year US Treasury Constant Maturity Rate (May 2026)

-----

## Color Coding (industry standard)

- **Blue text** — hardcoded inputs (assumptions you can change)
- **Black text** — formula outputs
- **Green text** — links pulling from another sheet

-----

## How to Use

1. Open `Wingstop_DCF_Model.xlsx` in Excel
1. Start on the **Assumptions** tab — all inputs are in blue
1. Adjust growth rates, margins, WACC, or terminal growth rate to run scenarios
1. The **DCF Valuation** tab automatically updates the implied share price
1. Use the **Sensitivity** tab to see how the price changes across a range of inputs

-----

*Built by Adebola Awokoya — Applied Mathematics, Towson University (May 2026)*
