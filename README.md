# 📈 Factor Investing with a Crypto Twist

Apply Fama French style factor investing to equities and crypto.  
Build Value Size Momentum factors in Python run backtests and produce clear performance reports and plots for portfolio analysis.

---

## 🚀 What This Project Does

* **Constructs** Value Size Momentum and custom factors from equity and crypto data  
* **Cleans and aligns** daily price series so backtests use consistent timestamps and returns  
* **Backtests** long only and long short factor portfolios with simple transaction cost assumptions  
* **Produces** cumulative performance plots factor correlation matrices turnover tables and attribution summaries  
* **Exports** publication ready PNG and CSV files for reports and dashboards

---

## 📂 Data

* **Sources**  
  * Equities from `yfinance` or your vendor of choice  
  * Crypto from `yfinance` or exchange APIs for BTC and ETH  
* **Frequency** daily close prices only  
* **Storage** cleaned CSVs live in `data` for reproducibility

---

## 🛠 Methods and Tools

* **pandas** and **numpy** for data wrangling and factor maths  
* **scikit learn** for ranking scaling and preprocessing utilities  
* **matplotlib** and **seaborn** for visualizations  
* **backtrader** or a small custom engine for backtests  
* **streamlit** as an optional lightweight signal viewer  
* **pytest** for unit tests

---

## 📁 Repository Layout

factor-investing-crypto/  
  data/  
    prices_equities.csv  
    prices_crypto.csv  
  notebooks/  
    factor_construction.ipynb  
  src/  
    ingestion.py       # load raw data write cleaned csv  
    factors.py         # factor construction and ranking routines  
    backtest.py        # backtest wrapper or engine adapter  
    portfolio.py       # portfolio construction and rebalancing logic  
    metrics.py         # performance metrics and tables  
    dashboard_app.py   # optional streamlit app for live signals  
  scripts/  
    run_backtest.py  
    export_plots.py  
  outputs/  
    plots/  
    results/  
  tests/  
    test_factors.py  
    test_backtest.py  
  requirements.txt  
  configs/  
    backtest.yaml  
  README.md  
  LICENSE

---

## 🖼 Key Visuals

1. **Cumulative Factor Returns** Value Size Momentum vs benchmark  
   *(outputs/plots/factor_cumulative_returns.png)*

2. **Factor Correlation Heatmap** shows co movement between factors and crypto  
   *(outputs/plots/factor_correlation_heatmap.png)*

3. **Rolling Exposure and Attribution** contribution of each factor over time  
   *(outputs/plots/rolling_attribution.png)*

4. **Turnover and Transaction Cost Sensitivity** table and plot  
   *(outputs/plots/turnover_sensitivity.png)*

All visuals are saved to `outputs/plots` as high resolution PNGs and SVGs for reports and social posts.

---

## ⚡ How to Run Locally

1. Clone the repo

```bash
git clone https://github.com/your-username/factor-investing-crypto.git
cd factor-investing-crypto
Create and activate a virtual environment

bash
Copy code
python -m venv venv
source venv/bin/activate   # on Windows use venv\Scripts\activate
Install dependencies

bash
Copy code
pip install -r requirements.txt
Fetch or place raw price files under data/raw then run ingestion

bash
Copy code
python src/ingestion.py --symbols configs/symbols.csv --out data/prices_equities.csv
python src/ingestion.py --symbols configs/crypto_symbols.csv --out data/prices_crypto.csv
Run a backtest with the example config

bash
Copy code
python scripts/run_backtest.py --config configs/backtest.yaml
Export plots

bash
Copy code
python scripts/export_plots.py --input outputs/results.pkl --out outputs/plots
Optional run live signal viewer

bash
Copy code
streamlit run src/dashboard_app.py
📌 Example backtest command
Generate factor performance from 2016 to 2025

bash
Copy code
python src/backtest.py --start 2016-01-01 --end 2025-06-30 \
  --factors value,size,momentum \
  --out outputs/results.pkl
🔮 Next Steps
Add risk parity or volatility parity weighting across factors

Extend factor set to include quality and low volatility for equities and momentum variants for crypto

Add rolling metrics like volatility Sharpe and information ratio

Wire a light CI check that runs a very small sample backtest on push

📜 License
MIT License
