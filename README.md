# 📈 Factor Investing with a Crypto Twist
Apply **Fama–French style factor investing** to equities and crypto.  
Build Value, Size, and Momentum factors in Python, run backtests, and generate performance reports and plots for portfolio analysis.  

---
## 🚀 What This Project Does
* **Constructs** Value, Size, Momentum, and custom factors from equity and crypto data  
* **Cleans & aligns** daily price series for consistent backtests  
* **Backtests** long-only and long-short factor portfolios  
* **Produces** cumulative return plots, factor correlation heatmaps, and attribution tables  
* **Exports** publication-ready plots and CSV files  

---
## 📂 Data
* **Sources:**  
  * Equities – Yahoo Finance (`yfinance`)  
  * Crypto – Bitcoin (**BTC-USD**) and Ethereum (**ETH-USD**)  
* **Frequency:** Daily closes  
* **Storage:** Cleaned CSVs are saved in `data/`  

---
## 🛠 Methods & Tools
* **pandas, numpy** – factor construction and wrangling  
* **scikit-learn** – preprocessing and ranking  
* **matplotlib, seaborn** – plots  
* **backtrader** (or custom engine) – backtesting  
* **streamlit** – optional dashboard  
* **pytest** – testing  

---
## 📁 Repository Layout

```
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
│   ├── plots/                  # Saved visuals  
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

```

---
## 🖼 Key Visuals
1. **Cumulative Factor Returns** – Value, Size, Momentum vs benchmark *(outputs/plots/factor_cumulative_returns.png)*  
2. **Factor Correlation Heatmap** – co-movement between factors and crypto assets *(outputs/plots/factor_correlation_heatmap.png)*  
3. **Rolling Alpha Attribution** – factor contributions over time *(outputs/plots/rolling_alpha.png)*  
4. **Turnover Sensitivity** – impact of transaction costs *(outputs/plots/turnover_sensitivity.png)*  
*All plots saved in `/outputs/plots` as high-resolution PNGs for LinkedIn and reports.*  

---
## ⚡ How to Run Locally
1. Clone repo
   ```bash
   git clone https://github.com/your-username/factor-investing-crypto.git  
   cd factor-investing-crypto
 

3. Create virtual environment
   ```bash
   python -m venv venv  
   source venv/bin/activate   # on Windows: venv\Scripts\activate
  

4. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```

6. Prepare data
   ```bash
   python src/ingestion.py --symbols configs/symbols.csv --out data/prices_equities.csv  
   python src/ingestion.py --symbols configs/crypto_symbols.csv --out data/prices_crypto.csv
   ```

8. Run backtest
   ```bash
   python scripts/run_backtest.py --config configs/backtest.yaml
   ```

10. Export plots

   ```bash
   python scripts/export_plots.py --input outputs/results.pkl --out outputs/plots 
   ```

12. Launch dashboard (optional)
   ```bash
   streamlit run src/dashboard_app.py
   ```

---
## 📌 Example Command

```bash
Backtest Value + Size + Momentum from 2016 onward:  
   python src/backtest.py --start 2016-01-01 --end 2025-06-30 \  
     --factors value,size,momentum \  
     --out outputs/results.pkl
```

---
## 🔮 Next Steps
* Add **risk parity weighting** across factors  
* Extend to **additional crypto assets** beyond BTC & ETH  
* Add **rolling Sharpe ratios and volatility overlays**  
* Integrate with **live data feeds** for daily signals  

---
## 📜 License
MIT License
