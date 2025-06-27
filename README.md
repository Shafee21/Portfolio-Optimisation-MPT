# Portfolio Optimisation and Risk Modelling

This project explores portfolio construction and risk analysis using real financial data. It applies mean-variance optimisation, VaR calculations, stochastic simulation, and GARCH modelling — all implemented in Python.

---

## 📌 Key Sections

### 📚 1. Portfolio Optimisation Theory

Using historical returns and covariances, the notebook solves for the portfolio that maximises the Sharpe ratio under full investment and no short-selling constraints.

**What I Got**:
- ✅ **Optimal Portfolio Weights**:
  - GOOGL: 22.58%
  - AMZN: 64.76%
  - TSLA: 12.66%
  - GS, BNDX, DAX_USD: 0%
- 📈 **Expected Annual Return**: **22.38%**
- 📉 **Expected Volatility**: **28.82%**
- 📊 **Sharpe Ratio**: **0.66**

> Interpretation: The optimiser favoured a concentrated allocation in tech stocks, particularly AMZN, due to their superior return-to-risk profile. Defensive assets were excluded because they didn’t enhance overall risk-adjusted performance.

---

### 💾 2. Data Acquisition

Price data was loaded from a CSV (originally sourced via Bloomberg) and cleaned using `pandas`. Columns were renamed, missing values were handled, and dates formatted. Assets included:  
`GOOGL`, `AMZN`, `TSLA`, `GS`, `BNDX`, `DAX_USD`.

---

### ⚙️ 3. Optimisation Code

The optimisation used `scipy.optimize.minimize` to determine asset weights by:
- Maximising the Sharpe ratio
- Enforcing constraints (weights sum to 1, no short selling)
- Calculating portfolio-level return, volatility, and the efficient frontier

---

### 📉 4. Value at Risk (VaR)

Both **parametric** and **historical** methods were used to estimate the risk of large losses in the optimised portfolio.

**What I Got**:
- 📉 **95% Daily VaR**: ~**-2.45%**
- 📉 **99% Daily VaR**: ~**-3.91%**

> Interpretation: Under normal market conditions, there's a 5% chance of losing more than 2.45% of the portfolio value in a single day.

---

### 📈 5. Geometric Brownian Motion (GBM)

Simulated multiple future price paths using GBM to understand how the portfolio might behave over time under stochastic returns. Drift and volatility were estimated from historical log returns.

---

### 🌀 6. GARCH Modelling

Applied a GARCH(1,1) model to capture volatility clustering in asset returns — reflecting more realistic and time-varying risk behaviour compared to constant volatility assumptions.

---

## 🛠️ Technologies Used

- Python (Pandas, NumPy, SciPy, Statsmodels, ARCH)
- Jupyter Notebook
- Matplotlib for plotting and data visualisation

---

## 📁 File

- [Access the full Jupyter notebook here](https://github.com/Shafee21/Portfolio-Optimisation-MPT/blob/main/ShafeeFMFinal%20(1)%20(1)%20(1)%20(1).ipynb) — full notebook with data prep, modelling, results, and charts

---


## ✅ Final Conclusion


This project demonstrates how data-driven techniques can inform portfolio decisions beyond intuition or static allocations. By combining optimisation, simulation, and volatility modelling, we gain a fuller understanding of how assets interact and how portfolios may perform under uncertainty. While the optimal allocation leaned heavily on high-growth equities, tools like VaR and GARCH helped quantify and contextualise the associated risks — highlighting the value of integrated risk management in investment strategy.
---

> Developed to demonstrate applied quantitative finance concepts, with a focus on portfolio construction, simulation, and risk assessment.
