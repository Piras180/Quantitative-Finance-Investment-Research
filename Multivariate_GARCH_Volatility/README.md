# When Bonds Stop Hedging: Post-COVID Changes in Financial Market Risk

**Empirical Methods in Finance | MSc Finance, HEC Lausanne | 2026**

Has the relationship between equities, bonds, and other asset classes changed since the COVID-19 pandemic?

This research project examines how financial market risk evolved before and after COVID-19, with a focus on **volatility persistence, tail risk, and cross-asset correlations**. It also evaluates what changing stock–bond relationships mean for portfolio diversification and risk-based asset allocation.

## Data & methodology

- **Market data:** Nine asset series spanning January 2005 to April 2026: S&P 500, Euro Stoxx 50, MSCI Emerging Markets, U.S. investment-grade and high-yield bonds, gold, oil futures, and U.S. and German 10-year government yields. The analysis compares 2005–2019 with 2021–2026, treating 2020 as a transition year.
- **Data processing:** Business-day alignment, log returns for price series, and duration-based return proxies for government bonds derived from changes in yields.
- **Volatility and tail-risk analysis:** Jarque–Bera, ARCH-LM, and Ljung–Box diagnostics; Student-*t* GARCH models, model selection using the Bayesian Information Criterion (BIC), and pre-/post-COVID volatility persistence comparisons.
- **Correlation and regime analysis:** Rolling correlations, a Dynamic Conditional Correlation (DCC) filter applied to standardized GARCH residuals, Welch tests, Newey–West HAC structural-break regressions, and a two-state Markov-switching model. EWMA correlations provide additional robustness checks for selected asset pairs.
- **Portfolio analysis:** Comparison of a traditional 60/40 stock–government-bond allocation with a nine-asset Equal Risk Contribution (ERC) portfolio, using lagged covariance estimates for monthly ERC rebalancing.

## Key findings

- **Stock–bond diversification weakened.** The average DCC correlation between the S&P 500 and the U.S. 10-year government-bond return proxy increased from **−0.325** before COVID-19 to **−0.040** afterward. The S&P 500–U.S. investment-grade bond correlation shifted from **−0.222** to **+0.083**.
- **The strongest tested break is associated with 2022.** Structural-break regressions identify significant shifts around both March 2020 and January 2022, with a larger estimated change for the 2022 inflation and rate-hiking period.
- **Volatility persistence did not systematically increase.** GARCH estimates remain highly persistent, but generally decline slightly in the post-COVID sample. Heavy-tailed returns remain a feature of the data.
- **Portfolio effects are material.** The 60/40 portfolio's annualized volatility rises from **9.98%** to **10.62%** across the two periods. The ERC portfolio's Sharpe ratio falls from **0.29** to **−0.25**, indicating weaker performance for this risk-based allocation in the later sample.

**Main takeaway:** The most notable post-COVID change is not a uniform increase in individual asset volatility, but a shift in **how asset classes move together**. A stock–bond hedge that worked in the earlier sample became less reliable, underlining the importance of monitoring correlations rather than assuming they remain stable.

## Implementation

**Tools:** Python, pandas, NumPy, SciPy, statsmodels, Matplotlib, and Jupyter Notebook.

- [Python analysis notebook](./Notebook%281%29.ipynb) — data preparation, volatility estimation, dynamic correlations, regime tests, portfolio analysis, and charts.
- [Research report](./EMIF_Report%282%29.pdf) — research motivation, empirical methodology, findings, and limitations.
- `Figures/` and `Tables/` — output directories created by the notebook for generated charts and result tables.

To reproduce the analysis, install the dependencies and place the project dataset (`Data.xlsx`) in the same directory as the notebook. The notebook uses this file rather than external data downloads.

```bash
pip install numpy pandas scipy statsmodels matplotlib openpyxl notebook
jupyter notebook
```

**Methodological note:** Government-bond returns are approximated using duration, and the DCC filter uses calibrated rather than jointly estimated parameters. The post-COVID sample is also relatively short; the findings document changes within the observed period, not a proven permanent or causal break. Portfolio results exclude transaction costs.

## Authors

Group project by **Matteo Piras, Marco D'Amico, and Roberto Berardi**.
