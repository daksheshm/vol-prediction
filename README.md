# Realized Volatility Prediction for High-Frequency Markets

A machine learning pipeline for forecasting **10-minute ahead realized volatility** from high-frequency limit order book (LOB) data. The project explores statistical and ensemble learning methods for short-horizon volatility prediction through feature engineering, dimensionality reduction, and rigorous model evaluation.

## Overview

Realized volatility is a fundamental quantity in quantitative finance, influencing market making, risk management, option pricing, and execution strategies. This project builds predictive models using historical order book data to estimate future realized variance over fixed time horizons.

The workflow consists of:

- Computing realized volatility from log returns
- Engineering temporal and market microstructure features
- Training multiple regression models
- Comparing forecasting performance using RMSE
- Building an end-to-end prediction pipeline

---

## Features

- High-frequency limit order book preprocessing
- Realized variance computation from log returns
- Rolling-window feature engineering
- HAR-RV style volatility modeling
- Ridge Regression and ExtraTrees regressors
- PCA-based dimensionality reduction
- Cross-validation and hyperparameter tuning
- RMSE-based model evaluation

---

## Dataset

The project uses high-frequency order book snapshots containing:

- Bid and ask prices
- Bid and ask sizes
- Weighted Average Price (WAP)
- Log returns
- Time bucket identifiers
- Stock identifiers

The prediction target is the **10-minute ahead realized variance** computed from intra-bucket log returns.

---

## Feature Engineering

The following classes of features were constructed:

- Rolling realized volatility
- Historical volatility averages
- Weighted log-return statistics
- Temporal aggregation features
- Stock-level historical statistics
- PCA-transformed feature representations

---

## Models

The following models were implemented and compared:

- HAR-RV (Heterogeneous AutoRegressive Volatility)
- Ridge Regression
- ExtraTrees Regressor

Each model was evaluated using out-of-sample RMSE and compared against a persistence baseline.

---

## Project Structure

```
.
├── data/
│   └── vol_lab.parquet
├── notebooks/
│   └── variance_prediction.ipynb
├── models/
├── outputs/
├── README.md
└── requirements.txt
```

---

## Workflow

1. Load and preprocess high-frequency market data
2. Compute realized volatility targets
3. Generate rolling-window features
4. Apply dimensionality reduction (PCA)
5. Train regression models
6. Evaluate using validation RMSE
7. Generate final predictions

---

## Tech Stack

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Jupyter Notebook

---

## Future Improvements

- Gradient Boosting (LightGBM/XGBoost)
- LSTM/Transformer-based sequence models
- Graph Neural Networks over order book states
- Multi-stock joint learning
- Online learning for streaming market data

---

## Applications

This project is relevant to:

- Quantitative Trading
- Market Making
- Risk Management
- Volatility Forecasting
- Algorithmic Execution
- Financial Machine Learning
