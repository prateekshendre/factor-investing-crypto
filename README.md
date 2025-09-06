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
├── data/                       # Cleaned CSVs
│   ├── prices_equities.csv
│   └── prices_crypto.csv
├── notebooks/                  # Jupyter notebooks
│   └── factor_construction.ipynb
├── src/                        # Core source code
│   ├── ingestion.py            # data loading & cleaning
│   ├── factors.py              # factor construction logic
│   ├── backtest.py             # backtesting engine
│   ├── portfolio.py            # portfolio weighting & rebalancing
│   ├── metrics.py              # performance metrics & attribution
│   └── dashboard_app.py        # optional Streamlit dashboard
├── scripts/                    # Utility scripts
│   ├── run_backtest.py
│   └── export_plots.py
├── outputs/                    # Model outputs
│   ├── plots/                  # Saved PNG/SVG visuals
│   │   ├── factor_cumulative_returns.png
│   │   ├── factor_correlation_heatmap.png
│   │   ├── rolling_alpha.png
│   │   └── turnover_sensitivity.png
│   └── results/                # Backtest results
├── tests/                      # Unit tests
│   ├── test_factors.py
│   └── test_backtest.py
├── configs/                    # Config files
│   └── backtest.yaml
├── README.md                   # Project overview
├── requirements.txt            # Dependencies
├── LICENSE                     # License info
└── .gitignore                  # Ignore rules


---

## 🖼 Key Visuals

1. **Cumulative Factor Returns** – Value, Size, Momentum vs benchmarks  
   *(outputs/plots/factor_cumulative_returns.png)*  

2. **Factor Correlation Heatmap** – co-movement between factors and assets  
   *(outputs/plots/factor_correlation_heatmap.png)*  

3. **Rolling Alpha Attribution** – contribution of each factor over time  
   *(outputs/plots/rolling_alpha.png)*  

4. **Turnover Sensitivity** – transaction costs and slippage effects  
   *(outputs/plots/turnover_sensitivity.png)*  

*All saved in `/outputs/plots` as high-res PNGs and SVGs for LinkedIn and reports.*  

---
## ⚡ How to Run Locally
1. Clone repo  
   git clone https://github.com/your-username/factor-investing-crypto.git  
   cd factor-investing-crypto  

2. Create virtual environment  
   python -m venv venv  
   source venv/bin/activate   # on Windows: venv\Scripts\activate  

3. Install dependencies  
   pip install -r requirements.txt  

4. Prepare data  
   python src/ingestion.py --symbols configs/symbols.csv --out data/prices_equities.csv  
   python src/ingestion.py --symbols configs/crypto_symbols.csv --out data/prices_crypto.csv  

5. Run backtest  
   python scripts/run_backtest.py --config configs/backtest.yaml  

6. Export plots  
   python scripts/export_plots.py --input outputs/results.pkl --out outputs/plots  

7. Launch dashboard (optional)  
   streamlit run src/dashboard_app.py  

---
## 📌 Example Command
Backtest Value + Size + Momentum from 2016 onward:  
   python src/backtest.py --start 2016-01-01 --end 2025-06-30 \  
     --factors value,size,momentum \  
     --out outputs/results.pkl  

---
## 🔮 Next Steps
* Add **risk parity weighting** across factors  
* Extend to **additional crypto assets** beyond BTC & ETH  
* Add **rolling Sharpe ratios and volatility overlays**  
* Integrate with **live data feeds** for daily signals  

---
## 📜 License
MIT License

