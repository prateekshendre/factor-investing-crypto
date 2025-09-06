# 📈 Factor Investing with a Crypto Twist

Apply **Fama–French style factor investing** to equities and crypto.  
Build Value, Size, and Momentum factors in Python, run backtests, and generate clear performance reports and plots for portfolio analysis.

---

## 🚀 What This Project Does

* **Constructs** Value, Size, Momentum, and custom factors from equity and crypto data  
* **Cleans & aligns** daily price series to ensure consistent timestamps and returns  
* **Backtests** long-only and long-short factor portfolios with optional transaction cost assumptions  
* **Produces** cumulative return plots, factor correlation matrices, turnover and attribution tables  
* **Exports** publication-ready PNGs and CSVs for reports and dashboards  

---

## 📂 Data

* **Sources:**  
  * Equities – Yahoo Finance via `yfinance`  
  * Crypto – Bitcoin (**BTC-USD**) and Ethereum (**ETH-USD**) via `yfinance` or exchange APIs  
* **Frequency:** Daily closes  
* **Storage:** Cleaned CSVs saved under `data/` for reproducibility  

---

## 🛠 Methods & Tools

* **pandas** & **numpy** – data wrangling and factor construction  
* **scikit-learn** – ranking, scaling, preprocessing  
* **matplotlib** & **seaborn** – visualizations  
* **backtrader** (or custom engine) – backtesting  
* **streamlit** – optional dashboard for live signal viewing  
* **pytest** – testing  

---

## 📁 Repository Layout

factor-investing-crypto/
│
├── data/                       # Cleaned CSVs
│   ├── prices_equities.csv
│   └── prices_crypto.csv
│
├── notebooks/                  # Jupyter notebooks
│   └── factor_construction.ipynb
│
├── src/                        # Core source code
│   ├── ingestion.py            # data loading & cleaning
│   ├── factors.py              # factor construction logic
│   ├── backtest.py             # backtesting engine
│   ├── portfolio.py            # portfolio weighting & rebalancing
│   ├── metrics.py              # performance metrics & attribution
│   └── dashboard_app.py        # optional Streamlit dashboard
│
├── scripts/                    # Utility scripts
│   ├── run_backtest.py
│   └── export_plots.py
│
├── outputs/                    # Model outputs
│   ├── plots/                  # Saved PNG/SVG visuals
│   │   ├── factor_cumulative_returns.png
│   │   ├── factor_correlation_heatmap.png
│   │   ├── rolling_alpha.png
│   │   └── turnover_sensitivity.png
│   └── results/                # Backtest results
│
├── tests/                      # Unit tests
│   ├── test_factors.py
│   └── test_backtest.py
│
├── configs/                    # Config files
│   └── backtest.yaml
│
├── README.md                   # Project overview
├── requirements.txt            # Dependencies
├── LICENSE                     # License info
└── .gitignore                  # Ignore rules

