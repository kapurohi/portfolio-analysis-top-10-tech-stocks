# Portfolio Optimization Project

This project is an implementation of Modern Portfolio Theory, which constructs and visualizes the Efficient Frontier using Monte Carlo simulation and constrained optimization.

This project contains two implementations:

- **Static Version** – Matplotlib-based visualization  
- **Interactive Version** – Panel dashboard with dynamic exploration  

The goal is to simulate portfolios, compute optimal allocations, and identify the maximum Sharpe ratio (Tangency) portfolio.

---

## Project Overview

This project applies core quantitative finance concepts:

- Log return computation  
- Annualized expected return  
- Annualized volatility  
- Sharpe ratio maximization  
- Monte Carlo portfolio simulation  
- Efficient Frontier construction  
- Tangency portfolio identification  

It recreates an HPOL-style efficient frontier workflow using clean, modular Python code.

---

## Project Structure

Portfolio-Optimization/
│
├── portfolio_optimization_analysis         # Static efficient frontier visualization  
├── portfolio_optimization_interactive     # Panel-based interactive dashboard  
└── README.md  

---

## What This Project Does

### 1. Efficient Frontier (Static)

The `portfolio_optimization_analysis.ipynb` script:
- Loads historical price data
- Computes daily log returns
- Simulates thousands of random portfolios
- Plots:
  - Simulated portfolios colored by Sharpe ratio
  - Markers for Efficient Frontier
  - Tangency portfolio (maximum Sharpe ratio)

Run using:

```bash
python portfolio_optimization_analysis.ipynb
```

### 2. Panel App (Interactive)

The `portfolio_optimization_interactive.ipynb` script creates a Panel app that:
- Shows an interactive visualization of the Efficient Frontier
- Displays portfolio statistics with filters
- Presents log returns in a paginated table
- Allows dynamic interaction with graphs

Run the app:
```bash
panel serve portfolio_optimization_interactive.ipynb --autoreload
```

Then open:
```code
http://localhost:5006
```

Log Returns
Daily log returns are computed as:
```code
log_return = np.log(prices / prices.shift(1))
```

Portfolio Metrics
* Annualized Expected Return
* Annualized Volatility
* Sharpe Ratio

Run using:
```bash
python portfolio_optimization_interactive.ipynb
```


## Notes:
- The interactive version has additional UI components.
- Both versions use the same underlying computations and return metrics.
- Interactive dashboards are useful for exploration and teaching.

### Possible future enhancements:
- Add a risk-free rate slider
- Add more optimization objectives
- Enable export of optimal portfolios
- Add additional interactive controls (e.g., target return)