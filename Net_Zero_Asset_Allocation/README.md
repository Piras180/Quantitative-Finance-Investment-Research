# Carbon-Constrained Portfolio Optimization in Emerging Markets

**Sustainability-Aware Asset Management | Python Research Project | 2026**

## Project Overview

Can an equity portfolio reduce its financed carbon emissions without materially sacrificing investment performance?

This project investigates the trade-off between **portfolio efficiency and decarbonization** in emerging-market equities. Using monthly financial data and firm-level **Scope 1 and Scope 2 emissions**, we construct conventional and carbon-constrained portfolios and evaluate their out-of-sample performance from **January 2014 to December 2025**.

The analysis compares five long-only strategies: a value-weighted benchmark, a minimum-variance portfolio, two portfolios targeting a **50% reduction in carbon footprint**, and a tracking-error-minimizing portfolio following a **10% annual decarbonization trajectory**.

## Methodology

- **Data preparation:** Clean Datastream financial and emissions data, align securities by ISIN, address missing observations and delistings, and filter low or stale prices.
- **Dynamic investment universe:** Rebuild the eligible emerging-market universe annually using a **120-month rolling estimation window** and historical information available at portfolio formation.
- **Portfolio optimization:** Use constrained numerical optimization (SLSQP) to minimize portfolio variance or tracking-error variance under full-investment and long-only constraints.
- **Carbon accounting:** Calculate **Weighted Average Carbon Intensity (WACI)** and portfolio **Carbon Footprint (CF)** using Scope 1 + 2 emissions.
- **Out-of-sample evaluation:** Compare annualized returns, volatility, Sharpe ratios, cumulative performance, and the carbon impact of each strategy.

## Key Results

| Portfolio | Annualized average return | Annualized volatility | Sharpe ratio | Carbon objective |
|---|---:|---:|---:|---|
| Value-weighted benchmark | 8.22% | 15.57% | 0.42 | None |
| Minimum variance | 6.72% | 10.48% | 0.47 | None |
| Minimum variance, carbon-constrained | 6.52% | 10.03% | 0.48 | 50% CF reduction vs. minimum variance |
| Tracking-error minimization, carbon-constrained | 9.01% | 16.10% | 0.45 | 50% CF reduction vs. value-weighted |
| Net-zero trajectory | 9.16% | 16.14% | 0.46 | 10% compounded annual CF reduction from 2013 baseline |

*Reported figures are historical out-of-sample results for 2014–2025. Returns are annualized arithmetic averages, not CAGR.*

The main finding is that **substantial carbon-footprint reductions were achieved without a material loss in risk-adjusted performance** over the sample. The constrained minimum-variance strategy preserved a similar Sharpe ratio while reducing volatility; both benchmark-tracking decarbonization strategies delivered higher realized returns than the value-weighted benchmark. These results are sample-dependent and should not be interpreted as evidence of persistent low-carbon outperformance.

## Technical Implementation

**Language:** Python  
**Libraries:** pandas, NumPy, SciPy, Matplotlib, Jupyter, openpyxl

The notebook covers data cleaning, dynamic universe construction, portfolio optimization, performance evaluation, carbon metrics, and exports of tables and figures.

## Repository Contents

```text
.
├── README.md
├── FINALCODE.ipynb                 # Complete analysis and portfolio optimization
├── sustainable_asset_management.pdf  # Research report, methodology and findings
└── Data_2026/                    # Required Datastream Excel inputs (if licensed for sharing)
```

To run the notebook, install the Python dependencies and place the required source Excel files in `Data_2026/` using the filenames referenced in the code. Outputs are written to an `outputs/` directory. **The notebook is not fully reproducible without the source data**, which may be subject to Datastream licensing restrictions.

## Authors

Academic group project by **Matteo Piras, Marco D'Amico, Roberto Berardi, and Tomas Papuga**.

**Full report:** [sustainable_asset_management.pdf](sustainable_asset_management.pdf)  
**Python notebook:** [FINALCODE.ipynb](FINALCODE.ipynb)
