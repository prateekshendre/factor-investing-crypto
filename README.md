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
│  └── factor_construction.ipynb


