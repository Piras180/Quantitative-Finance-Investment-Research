# Oil Shocks, the Yield Curve & U.S. Equity Returns

**Empirical Methods in Finance | MSc Finance, HEC Lausanne | 2026**

Can movements in oil prices and the U.S. Treasury yield curve help predict weekly S&P 500 returns?

This research project investigates the relationship between energy-market shocks, changes in interest-rate expectations, and equity performance. Beyond identifying statistical relationships, the objective is to test whether these signals improve forecasts on data not used to estimate the models.

## Data & methodology

- **Market data:** WTI crude oil prices, S&P 500 index levels, and 2-year and 10-year U.S. Treasury yields, covering January 1990 to March 2026.
- **Data processing:** Conversion from daily to weekly observations, computation of log returns, and construction of the 10Y–2Y Treasury yield spread and its weekly changes.
- **Econometric analysis:** Descriptive statistics, Jarque–Bera and Ljung–Box tests, OLS and ARX(1) regressions, and a VAR(1) model with impulse-response analysis.
- **Forecast evaluation:** One-step-ahead predictions with a 156-week rolling estimation window, compared against AR(1) and zero-return (random-walk) benchmarks. Rolling coefficients and forecast errors are also examined across market regimes.

## Key findings

- Changes in the Treasury yield spread show a statistically significant relationship with subsequent weekly S&P 500 returns in-sample, but the models explain only a small share of return variation.
- Lagged oil returns do not provide a statistically significant, stable direct predictor of equity returns. Their estimated relationship changes across market conditions.
- In **1,731 out-of-sample weekly forecasts**, the simple zero-return benchmark achieves the lowest root mean squared error (RMSE):

| Forecasting model | Out-of-sample RMSE |
| --- | ---: |
| Zero-return / random-walk benchmark | **0.023680** |
| AR(1) | 0.023918 |
| ARX(1) | 0.024370 |
| VAR(1) | 0.024383 |

**Main takeaway:** Adding macro-financial variables and model complexity did not improve short-horizon equity-return forecasts. The project highlights the importance of out-of-sample validation and the instability of financial relationships across market regimes.

## Implementation

**Tools:** Python, pandas, NumPy, SciPy, statsmodels, Matplotlib, and Jupyter Notebook.

- [Python analysis notebook](./Markdown%20%2B%20Notes2%281%29.ipynb) — data preparation, estimations, diagnostics, visualizations, and rolling forecasts.
- [Research report](./EMIF_Project_Report.pdf) — research motivation, methodology, interpretation, and limitations.

To reproduce the notebook, install the Python dependencies and place `data_hec_projet_1.xlsx` in the same directory as the notebook. The code expects a worksheet named `Daily`.

```bash
pip install numpy pandas scipy statsmodels matplotlib openpyxl notebook
jupyter notebook
```

## Authors

Group project by **Matteo Piras, Marco D'Amico, and Roberto Berardi**.
