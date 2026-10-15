# Results

These are the tables and charts from the published run of `halloween_indicator.ipynb` (October 13, 2026). The main sample is Halloween years 1961–2025, with S&P 500 total return and modeled T-bills, unless a table says otherwise.

**Conventions**
- Column names ending in `%` are in percent. Other return columns are decimals.
- CIs are 95%. `lo`/`hi` are the bounds.
- Bootstrap p-values are two-sided, from a 3-year circular block bootstrap over Halloween years.
- `p_fdr` and `*_fdr` columns are Benjamini–Hochberg adjusted.
- Abbreviations: `BH` = buy-and-hold, `HW` = Halloween (Sell in May), `MIX` = 50/50 stocks/T-bills, `W`/`S` = November–April / May–October stock return, `Cs` = May–October T-bill return.

## Tables (`tables/`)

| File | Notebook section | What it shows |
|---|---|---|
| [`data_coverage.csv`](tables/data_coverage.csv) | 1 | First and last month available for each input series |
| [`summary_strategies.csv`](tables/summary_strategies.csv) | 2 | $1 grows to, CAGR, volatility, Sharpe, max drawdown for buy-and-hold, Halloween, 50/50, T-bills |
| [`tests_main.csv`](tables/tests_main.csv) | 2 | Primary endpoints H1 (`W_minus_S`) and H2 (`HW_minus_BH`) plus supporting tests: mean, median, bootstrap CI, sign test |
| [`regression_seasonality_log_price.csv`](tables/regression_seasonality_log_price.csv) | 2 | Paper-style regression of monthly log price returns on a November–April dummy (Newey–West) |
| [`regression_excess_vs_cash.csv`](tables/regression_excess_vs_cash.csv) | 2 | Monthly stock return minus T-bills on the same dummy |
| [`timing_alpha_beta_matched.csv`](tables/timing_alpha_beta_matched.csv) | 2 | Jensen's alpha and beta of Halloween vs buy-and-hold |
| [`sharpe_difference.csv`](tables/sharpe_difference.csv) | 2 | Sharpe difference, Halloween minus buy-and-hold, with bootstrap CI |
| [`variants_dividends_cash.csv`](tables/variants_dividends_cash.csv) | 3 | Price vs total return, and 0% vs T-bills while out |
| [`placebo_by_month.csv`](tables/placebo_by_month.csv) | 4 | Stocks minus T-bills for each calendar month |
| [`placebo_12_windows.csv`](tables/placebo_12_windows.csv) | 4 | All 12 consecutive six-month windows as a rule |
| [`placebo_924_calendars_top10.csv`](tables/placebo_924_calendars_top10.csv) | 4 | Top 10 of all 924 six-month month sets by winter-minus-summer premium (descriptive) |
| [`st_leger_vs_halloween.csv`](tables/st_leger_vs_halloween.csv) | 4b | Coming back at the end of August or September instead of October |
| [`pre_post_working_paper_and_journal.csv`](tables/pre_post_working_paper_and_journal.csv) | 5 | Endpoints before and after 1998 and 2002, with the smallest detectable effect (MDE80) and verdicts |
| [`by_decade.csv`](tables/by_decade.csv) | 5 | Average half-year returns and CAGRs by decade |
| [`cutoff_sensitivity.csv`](tables/cutoff_sensitivity.csv) | 5b | Results after 1998 and after 2002, side by side |
| [`cutoff_bridge_years_1999_2002.csv`](tables/cutoff_bridge_years_1999_2002.csv) | 5b | The four years that separate the two cutoffs |
| [`risk_by_period.csv`](tables/risk_by_period.csv) | 5b | Drawdown, Sharpe, beta, alpha and the same-beta comparison, by period |
| [`quant_scorecard_headline.csv`](tables/quant_scorecard_headline.csv) | 5c | Sharpe with CIs, alpha (Newey–West t), information ratio, alpha net of costs, drawdown, Sortino, Calmar |
| [`quant_scorecard_long.csv`](tables/quant_scorecard_long.csv) | 5c | Full scorecard for each strategy and period, including skewness, kurtosis, worst month |
| [`quant_scorecard_by_decade.csv`](tables/quant_scorecard_by_decade.csv) | 5c | Sharpe and alpha by decade (descriptive) |
| [`international.csv`](tables/international.csv) | 6 | Winter-minus-summer price pattern in 8 other markets (H1 only) |
| [`trading_costs.csv`](tables/trading_costs.csv) | 7 | Halloween vs buy-and-hold at 0–50 bps per switch |
| [`taxes.csv`](tables/taxes.csv) | 7 | Stylized US tax scenarios |
| [`robustness.csv`](tables/robustness.csv) | 8 | Endpoints under alternate dividend and cash constructions, and with SPY and BIL |
| [`block_length_sensitivity.csv`](tables/block_length_sensitivity.csv) | 8 | Bootstrap CIs with 1- to 8-year blocks |
| [`tail_year_sensitivity.csv`](tables/tail_year_sensitivity.csv) | 8 | Dropping each strategy's best years |
| [`outliers_monthly_regressions.csv`](tables/outliers_monthly_regressions.csv) | 8 | Monthly regressions without October 1987 and August 1998, without the 10 largest moves, and winsorized |
| [`outliers_extreme_months.csv`](tables/outliers_extreme_months.csv) | 8 | The 10 largest monthly S&P price moves and which half they fell in |
| [`outliers_annual_endpoints.csv`](tables/outliers_annual_endpoints.csv) | 8 | Annual endpoints with winsorized monthly returns |
| [`video_numbers.csv`](tables/video_numbers.csv) | 10 | Every number quoted in the video, with its notebook section |

The notebook also writes year-by-year and month-by-month series, such as growth of $1 and the per-year Halloween table, to `halloween_work/outputs_v7/` when you run it. Those series aren't included here.

## Charts (`charts/`)

| File | What it shows |
|---|---|
| [`01_growth_of_1.png`](charts/01_growth_of_1.png) | Growth of $1, 1961–2025 (log scale) |
| [`02_average_six_month_returns.png`](charts/02_average_six_month_returns.png) | Average November–April stocks, May–October stocks, May–October T-bills |
| [`03_summer_stocks_minus_tbills_by_year.png`](charts/03_summer_stocks_minus_tbills_by_year.png) | May–October stocks minus T-bills, each year |
| [`04_dividends_and_cash_variants.png`](charts/04_dividends_and_cash_variants.png) | How dividends and cash assumptions change the answer |
| [`05_by_month.png`](charts/05_by_month.png) | Stocks minus T-bills by calendar month |
| [`06_placebo_12_windows.png`](charts/06_placebo_12_windows.png) | All 12 six-month windows |
| [`06b_st_leger_vs_halloween.png`](charts/06b_st_leger_vs_halloween.png) | St Leger's Day variants |
| [`07_placebo_924_calendars.png`](charts/07_placebo_924_calendars.png) | All 924 six-month calendars |
| [`08_pre_post_journal_publication.png`](charts/08_pre_post_journal_publication.png) | Average six-month returns, 1961–2002 vs 2003–2025 |
| [`08b_growth_of_1_since_2003.png`](charts/08b_growth_of_1_since_2003.png) | Growth of $1 from the October 2002 close |
| [`08c_growth_of_1_since_1999.png`](charts/08c_growth_of_1_since_1999.png) | Growth of $1 from the October 1998 close |
| [`08d_rolling_alpha_and_sharpe.png`](charts/08d_rolling_alpha_and_sharpe.png) | Rolling 15-year alpha (with 95% CI) and Sharpe ratio |
| [`09_rolling_window.png`](charts/09_rolling_window.png) | Rolling 15-year averages of Halloween minus buy-and-hold and of the winter-minus-summer premium gap |
| [`10_international.png`](charts/10_international.png) | Winter-minus-summer gap in 8 other markets |

The charts are taken from the notebook's displayed output. Running the notebook saves 200-dpi versions to `halloween_work/outputs_v7/`.
