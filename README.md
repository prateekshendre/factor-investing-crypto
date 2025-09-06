# Factor Investing with a Crypto Twist

Track factor returns and test factor tilts on both equities and crypto.  
This project builds Fama French style factors in Python and backtests factor exposures on Bitcoin and large cap equities for practical portfolio construction and risk analysis.

---

## What this project does

* Builds factor signals for Value Size Momentum and any custom factors you add
* Aligns and cleans equity and crypto data for consistent backtesting
* Runs long only and long short backtests with transaction cost assumptions
* Produces performance tables and publication ready plots
* Exposes a simple API and light web dashboard for live signal inspection and trade signals

---

## Why this matters

Factor strategies are proven in equities. Crypto markets are different.  
What this project tests is how classic factors translate to crypto and whether crypto can improve factor diversification for a factor driven portfolio.

---

## Data

* Price sources
  * equities from `yfinance` or your market data vendor
  * crypto from `yfinance` or public exchange APIs
* Frequency
  * daily close only
* Stored cleaned csv files live in `data/` for reproducibility

---

## Methods and tools

* pandas for data handling
* numpy for numeric operations
* ta or custom functions for factor calculations
* scikit learn for cross sectional ranking and preprocessing
* backtrader or custom backtest engine for returns simulation
* matplotlib and seaborn for plots
* streamlit or a lightweight Flask app for a live signal viewer
* pytest for tests
* Docker for reproducible environment
* GitHub Actions for CI

---

## Architecture overview

1. data ingestion
2. cleaning and alignment
3. factor construction and cross sectional ranking
4. portfolio construction and backtest
5. reporting, plots, and dashboard

The code is intentionally modular so you can swap the data source or backtest engine.

---

## Repo layout

factor-investing-crypto/
│
├── data/ # Cleaned CSV files
│ ├── prices_equities.csv
│ └── prices_crypto.csv
│
├── notebooks/ # Exploratory analysis
│ └── factor_construction.ipynb
│
├── src/
│ ├── ingestion.py # load raw data and output cleaned csv
│ ├── factors.py # factor calculation and ranking
│ ├── backtest.py # backtest engine wrapper
│ ├── portfolio.py # portfolio construction and rebalancing
│ ├── metrics.py # performance metrics
│ └── dashboard_app.py # streamlit or flask app for live signals
│
├── scripts/
│ ├── run_backtest.py
│ └── export_plots.py
│
├── tests/
│ ├── test_factors.py
│ └── test_backtest.py
│
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── .github/workflows/ci.yml
├── README.md
└── LICENSE

yaml
Copy code

---

## Key outputs and visuals

1. Normalized factor returns plot with cumulative returns
2. Turnover and transaction cost sensitivity table
3. Factor correlation matrix plot
4. Rolling factor exposures and alpha attribution
5. Live signal table for current ranks and signals

Save every figure under `outputs/plots` as both PNG and SVG for reports.

---

## How to run locally

1. Clone and enter repo

```bash
git clone https://github.com/your-username/factor-investing-crypto.git
cd factor-investing-crypto
Create virtual environment and install

bash
Copy code
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
Fetch cleaned data locally

bash
Copy code
python src/ingestion.py --symbols-file configs/symbols.csv --out data/
Run full backtest

bash
Copy code
python scripts/run_backtest.py --config configs/backtest.yaml
Export plots

bash
Copy code
python scripts/export_plots.py --input data/clean_prices.csv --out outputs/plots
Start live dashboard

bash
Copy code
streamlit run src/dashboard_app.py
Example commands
Generate normalized factor performance

bash
Copy code
python src/backtest.py --start 2016-01-01 --end 2025-06-30 --factors value,size,momentum --out outputs/results.pkl
Plot results

bash
Copy code
python scripts/export_plots.py --input outputs/results.pkl --out outputs/plots
Tests and quality
Run tests

bash
Copy code
pytest -q
CI pipeline on push runs lint tests flake8 and pytest

Deployment and live demo
Option 1 streamlit cloud

Build container with Dockerfile and push to registry

Configure streamlit cloud to pull the container

Option 2 Docker and cloud provider

Build Docker image

Deploy to AWS ECS, DigitalOcean App Platform, or a small VM

Use GitHub Actions to build push and deploy on tag

Expose a read only endpoint that returns current ranks and signals in JSON for any external execution system.

Config and reproducibility
Keep seeds fixed in config

Log versions of pandas numpy scikit learn with pip freeze > environment.txt

Store cleaned data csvs in data/ so backtests are repeatable

Next steps
Add risk parity weighting across factor exposures

Add live market neutral mode for intraday signals

Add transaction cost model and slippage sampling for robustness

License
MIT
