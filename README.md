**Asset Allocation**

Use macroeconomic indicators (e.g., inflation, yield curve, PMI) to predict market regimes (risk-on/off) and dynamically allocate to equity vs bonds vs cash.

What I Learnt:
	•	Regime classification (K-Means or HMM)
	•	Factor-based portfolio allocation
	•	Rolling backtest of regime-switching strategy
	•	Feature importance (SHAP, model coefficients)

Tools:
	•	scikit-learn, pandas, stats-models, matplotlib
	•	Macroeconomic data: FRED, OECD, World Bank
	•	Strategy logic in Python or Excel

Key Output:
	•	Regime-labeled time series (bull, bear, neutral)
	•	Backtest vs 60/40 static portfolio
	•	Monthly regime shift heat-map

Sample Insight:
“During inflationary bear regimes, switching 60% of equity allocation to cash improved annualized return by 1.3% and reduced drawdown by 25%.”

⸻

📌 Objective:

**Classify market regimes using macroeconomic indicators and allocate between asset classes (e.g., stocks vs bonds) accordingly.**


🧩 Components:

1. Data -  Download key macro indicators (FRED: Inflation, Fed Funds Rate, GDP growth, PMI, etc.)
2. Preprocessing -  Normalize data, handle missing values, align by date
3. Modeling -  Use KMeans or **Hidden Markov Model** (HMM) to identify regimes
4. Allocation Logic -  Create rules for asset allocation per regime
5. Backtest -  Compare regime-based strategy vs static 60/40

🛠️ Tools:
	• pandas, sklearn, **statsmodels**, matplotlib
	• yfinance for ETFs: SPY (stocks), TLT (bonds), SHY (cash)
	• fredapi or manual download for macro data

⸻

# 🧠 Macro Regime-Based Asset Allocation Strategy

A machine learning-driven investment strategy that dynamically adjusts asset allocation (SPY, TLT, SHY) based on prevailing macroeconomic regimes. The model uses both KMeans clustering and Hidden Markov Models (HMMs) to detect regime shifts from macro data and adapt portfolio weights accordingly.

---

## 📌 Objective
To replicate how macro hedge funds and asset managers adjust asset exposure across economic cycles. The strategy simulates adaptive portfolio allocation using interpretable, rule-based logic layered on unsupervised and probabilistic regime detection.

---

## 📈 Strategy Flow

1. **Data Collection**
   - Macroeconomic indicators from FRED (CPI, Fed Funds, Employment, Yield Curve Spread, PPI)
   - ETF prices from Yahoo Finance (SPY, TLT, SHY)

2. **Feature Engineering**
   - Year-over-year % changes in employment and PPI
   - Monthly resampling and forward-filling for alignment

3. **Regime Detection**
   - **KMeans Clustering**: Groups macro conditions into 4 unsupervised clusters
   - **Hidden Markov Model**: Captures sequential structure in economic regimes

4. **Asset Allocation Rules**
   - Assigns weight presets to SPY, TLT, SHY based on detected regime
   - Compares performance of static SPY benchmark vs dynamic allocation

5. **Backtesting + Evaluation**
   - Metrics: CAGR, Sharpe Ratio, Max Drawdown
   - Visualizations: Regime transitions, cumulative returns, heatmaps

---

## 📊 Results (Highlights)

| Strategy | CAGR | Max Drawdown | Sharpe Ratio |
|----------|------|--------------|---------------|
| HMM Regime Allocation | 1.19% | -24.61% | 0.18 |
| KMeans Strategy | ~ | ~ | ~ |
| SPY Benchmark | ~ | ~ | ~ |

✅ HMM showed smoother transitions and improved drawdown control versus SPY.  
✅ KMeans captured broad regime clusters but lacked sequential modeling.

---

## 🧰 Tech Stack
- Python, **pandas**, matplotlib, seaborn
- scikit-learn, **hmmlearn**, yfinance
- **FRED macroeconomic data
**
---

## 📂 Structure

- `notebooks/` — Jupyter notebook for full strategy walkthrough
- `data/` — Cleaned FRED macroeconomic inputs
- `plots/` — Strategy visualizations
- `report/` — PDF write-up of methodology and results

---

## 💡 Next Steps

- Integrate regime forecasts into forward-looking models
- Combine macro signals with factor momentum (Project 2)
- Build production-ready pipeline for real-time regime tracking

---

## 🙋 About Me

I'm Partha Sarathi Chakraborty — an aspiring Quantitative Researcher with a CS background and deep interest in macro strategy, signals research, and data-driven investing.  
This project was designed to simulate real-world investment modeling and signal deployment as done in hedge funds and institutional desks.
