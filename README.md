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

finance-ml-risk/
│
├── data/
│ ├── examples/ # sample CSVs
│ └── feature_store/ # engineered features
│
├── notebooks/
│ └── eda_feature_engineering.ipynb
│
├── src/
│ ├── ingestion.py # raw to cleaned data
│ ├── features.py # feature engineering
│ ├── pipeline.py # preprocessing pipeline
│ ├── train.py # training and persistence
│ ├── evaluate.py # model validation
│ ├── explainability.py # SHAP reports
│ └── predict.py # inference
│
├── experiments/ # MLflow logs
├── reports/
│ ├── model_card_template.md
│ └── validation_report_template.md
│
├── scripts/
│ ├── run_training.sh
│ └── generate_report.py
│
├── tests/
│ ├── test_pipeline.py
│ └── test_features.py
│
├── requirements.txt
├── Dockerfile
├── README.md
├── LICENSE
└── .gitignore

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
