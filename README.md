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
