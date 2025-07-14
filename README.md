# Financial Time Series Prediction with XGBoost

This repository contains the code, datasets, and final report for the Programming Assignment 1 of DS/CS 451. The goal of this assignment is to use a financial time series dataset to predict next-day returns using machine learning methods. Specifically, we apply XGBoost with time-series-aware cross-validation, using lagged features derived from historical WTI crude oil prices.

## Problem Description

The objective is to predict whether the next day’s return is positive or negative using past financial indicators derived from daily WTI prices. We engineer a variety of lag-based features (price, volume, volatility, etc.) and evaluate the predictive power of XGBoost using time-series-aware cross-validation.

## Repository Structure

```
.
├── 451_pa1_jump_start_v001.ipynb      # Main notebook with code and results
├── 451_pa1_jump_start_v001.html       # HTML export of the notebook
├── 451_pa1_report.pdf                 # Research report (PDF)
├── 451_pa1_wti_historical_data.csv    # Raw WTI data from Yahoo Finance
├── wti-with-computed-features.csv     # Feature-engineered dataset
├── README.md                          # This file
```

## Dependencies

- Python 3.9+
- `polars`
- `pandas`
- `numpy`
- `xgboost`
- `scikit-learn`
- `yfinance`
- `matplotlib`
- `seaborn`

Install all required packages via:

```bash
pip install polars pandas numpy xgboost scikit-learn yfinance matplotlib seaborn
```

## How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/YOUR_USERNAME/451_pa1_wti.git
   cd 451_pa1_wti
   ```

2. Open and run the Jupyter notebook:
   - Either locally with Jupyter:
     ```bash
     jupyter notebook 451_pa1_jump_start_v001.ipynb
     ```
   - Or upload it to [Google Colab](https://colab.research.google.com) for execution.

3. To regenerate the HTML version:
   ```bash
   jupyter nbconvert --to html 451_pa1_jump_start_v001.ipynb
   ```

## Model Summary

- **Model Used:** XGBoost Classifier
- **Evaluation:** TimeSeriesSplit with 5-fold cross-validation
- **Metric:** ROC AUC
- **Result:** Average AUC ≈ **0.5145**

> Note: The performance is close to random guessing due to the weak signal in short-term return prediction. Future improvements could include technical indicators, macroeconomic features, or alternative targets.

## Report

Please see `451_pa1_report.pdf` for the full research design, methodology, feature explanation, and evaluation results.

## Use of AI Assistants

AI assistants, such as ChatGPT, were used in the following ways:
- Code debugging (e.g., fixing `X_scaled not defined`)
- Explaining error tracebacks
- Generating summary tables and README structure

All AI-generated content was reviewed and modified for correctness and alignment with the assignment's requirements.
