# Retail Demand Forecasting & Inventory Optimization System
### Machine Learning + Time Series Analytics | Python | Google Colab

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Colab](https://img.shields.io/badge/Platform-Google%20Colab-orange)

---

## Overview

An end-to-end retail demand forecasting and inventory optimization pipeline built entirely in Python. This project combines classical time series econometrics with modern machine learning to forecast weekly product-level demand across 20 SKUs in 4 retail categories — then uses those forecasts to drive data-driven inventory decisions.

---

## Key Features

- Synthetic retail dataset: 29,220 daily records across 20 products (2021–2024)
- Five forecasting models trained and benchmarked head-to-head
- Inverse-RMSE weighted ensemble for optimal forecast accuracy
- EOQ, Safety Stock, and Reorder Point computed per SKU
- Interactive Plotly executive dashboard
- Fully reproducible — fixed random seed, zero external dependencies

---

## Models Implemented

| Model | Type |
|---|---|
| Auto-SARIMA | Classical Time Series |
| Facebook Prophet | Decomposition-based |
| XGBoost | Gradient Boosting (ML) |
| LightGBM | Gradient Boosting (ML) |
| Weighted Ensemble | Meta-learner |

---

## Inventory Optimization

| Formula | Purpose |
|---|---|
| EOQ = sqrt(2DS/H) | Minimize total ordering + holding cost |
| ROP = (Avg Daily Demand × Lead Time) + Safety Stock | When to reorder |
| Safety Stock = Z × σ × sqrt(Lead Time) | Buffer against demand variability |

Service level target: **95% (Z = 1.645)**

---

## Feature Engineering

- Lag features: 1w, 2w, 3w, 4w, 8w, 13w
- Rolling statistics: mean & std over 4w, 8w, 13w windows
- Exponential weighted mean: span 4w and 13w
- Cyclical encoding: month and week (sin/cos)
- Holiday flags: Black Friday, Christmas season, Summer
- Price × demand interaction term

---

## Tech Stack
Python 3.12 · NumPy · Pandas · Scikit-learn
XGBoost · LightGBM · Facebook Prophet · pmdarima
Statsmodels · Plotly · Matplotlib · Seaborn
Google Colab · Joblib

---

## Project Structure
retail-demand-forecasting-inventory-optimization/
│
├── Retail_Demand_Forecasting.ipynb   # Main notebook
├── model_performance.csv             # Model evaluation results
├── inventory_optimization.csv        # EOQ, ROP, Safety Stock per SKU
├── multiproduct_forecast_results.csv # MAPE per product
├── xgb_demand_forecaster.pkl         # Saved XGBoost model
└── README.md
---

## Results Summary

- Median MAPE across all 20 products: **< 15%**
- Ensemble model outperforms all individual models
- EOQ-guided ordering reduces estimated annual inventory cost by **15–25%**
- 95% service level safety stock eliminates ~85% of stockout risk

---

## Author

**Given Chinyama**
Data Scientist | Lusaka, Zambia
MSc Mathematics Education — Specialising in Time Series Analysis & Stochastic Processes

---

## License

This project is licensed under the MIT License.
