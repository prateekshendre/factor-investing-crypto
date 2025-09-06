# 📈 Factor Investing with a Crypto Twist

Apply **Fama–French style factor investing** to both equities and crypto.  
Build Value, Size, and Momentum factors, backtest them, and analyze diversification effects when adding Bitcoin and Ethereum to traditional equity portfolios.

---

## 🚀 What This Project Does

* **Constructs** Value, Size, and Momentum factors from equity and crypto data  
* **Aligns & cleans** datasets for consistent backtesting  
* **Backtests** long-only and long-short factor portfolios with performance attribution  
* **Generates** cumulative returns, rolling exposures, and factor correlation plots  
* **Exports** publication-ready plots and CSV files for reporting and dashboards  

---

## 📂 Data

* **Sources:**  
  * Equities – Yahoo Finance (`yfinance`)  
  * Crypto – Bitcoin (**BTC-USD**) and Ethereum (**ETH-USD**)  

* **Frequency:** Daily closes  
* **Storage:** Clean CSVs are kept in `/data` for reproducibility  

---

## 🛠 Methods & Tools

* **pandas & numpy** – factor construction and data wrangling  
* **scikit-learn** – ranking, scaling, preprocessing  
* **matplotlib & seaborn** – visualizations  
* **backtrader** (or custom engine) – backtesting  
* **streamlit** – optional interactive dashboard  
* **Jupyter Notebook** – exploration and analysis  

---

## 📁 Repository Layout

factor-investing-crypto/
│
├── data/ # Cleaned CSVs
│ ├── prices_equities.csv
│ └── prices_crypto.csv
│
├── notebooks/ # Jupyter notebooks
│ └── factor_construction.ipynb
│
├── src/ # Core source code
│ ├── ingestion.py
│ ├── factors.py
│ ├── backtest.py
│ ├── portfolio.py
│ ├── metrics.py
│ └── dashboard_app.py
│
├── scripts/ # Utility scripts
│ ├── run_backtest.py
│ └── export_plots.py
│
├── outputs/
│ ├── plots/ # Saved visuals
│ └── results/ # Backtest results
│
├── tests/ # Unit tests
│ ├── test_factors.py
│ └── test_backtest.py
│
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore

yaml
Copy code

---

## 🖼 Key Visuals

1. **Cumulative Factor Returns** – Value, Size, Momentum vs benchmarks  
   *(outputs/plots/factor_cumulative_returns.png)*  

2. **Factor Correlation Heatmap** – co-movement between factors and crypto assets  
   *(outputs/plots/factor_correlation_heatmap.png)*  

3. **Rolling Alpha Attribution** – contribution of each factor over time  
   *(outputs/plots/rolling_alpha.png)*  

4. **Transaction Cost Sensitivity** – turnover and slippage effects  
   *(outputs/plots/turnover_sensitivity.png)*  

*All plots saved in `/outputs/plots` as high-resolution PNGs and SVGs for reports and LinkedIn.*

---

## ⚡ How to Run Locally

1. Clone repo  

   ```bash
   git clone https://github.com/your-username/factor-investing-crypto.git
   cd factor-investing-crypto
Create virtual environment

bash
Copy code
python -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows
Install dependencies

bash
Copy code
pip install -r requirements.txt
Run backtest

bash
Copy code
python scripts/run_backtest.py --config configs/backtest.yaml
Export plots

bash
Copy code
python scripts/export_plots.py --input outputs/results.pkl --out outputs/plots
(Optional) Launch dashboard

bash
Copy code
streamlit run src/dashboard_app.py
📌 Example Command
Generate normalized factor performance:

bash
Copy code
python src/backtest.py --start 2016-01-01 --end 2025-06-30 \
  --factors value,size,momentum \
  --out outputs/results.pkl
🔮 Next Steps
Add risk parity weighting across factor exposures

Extend to additional crypto assets beyond BTC and ETH

Add rolling volatility & Sharpe ratio analysis

Integrate with live data feed for daily signals

📜 License
MIT License
