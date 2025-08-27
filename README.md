# Volatility-Informed Machine Learning and Technical Indicators for Multi-Asset Trading Signal Evaluation
**Author:** Yiwen Chan 
**Programme – MSc Banking and Digital Finance**  


---

## Project Overview

This repository contains the  **Jupyter Notebooks** code used for the master's dissertation:

 “Volatility-Informed Trading Signal Prediction Using Technical Analysis and Machine Learning: A Multi-Asset Investigation.” 

The project investigates the predictive power of technical indicators (Bollinger Bands, MACD, RSI) and machine learning classifiers (Random Forest, XGBoost, MLP) for trading signals. It integrates GARCH-based volatility forecasting both as a risk filter and as input features, and evaluates strategies across multiple assets using a consistent trading mechanism.

All analysis for each asset is contained in a **single, self-contained Jupyter Notebook**, making the workflow easy to run.

---

## Table of Contents
- [Notebooks](#notebooks)
- [Features](#features)
- [Usage](#usage)
- [Dataset Information](#dataset-information)
- [Environment](#environment)
- [Reproductivity Note](#reproductivity-note) 
- [License](#license)


---

## Notebooks

Each notebook focuses on a different asset:

| Asset | Notebook |
|-------|---------|
| Apple (AAPL) | `dissertation_AAPL.ipynb` |
| S&P 500 (SPY) | `dissertation_SPY.ipynb` |
| NASDAQ-100 (QQQ) | `dissertation_QQQ.ipynb` |
| Gold (GLD) | `dissertation_GLD.ipynb` |
| Oil (USO) | `dissertation_USO.ipynb` |



Each notebook includes:  
- Data download and preprocessing  
- Calculation of technical indicators (Bollinger Bands, RSI, MACD)  
- GARCH volatility modeling for risk filtering  
- Machine Learning-based trading signal generation (Random Forest, XGBoost, MLP)  
- Backtesting and evaluation of signal robustness, including stop-loss, take-profit, and performance metrics  

> **Note:** Notebooks are self-contained per asset. Running all cells sequentially will reproduce all results.  

---

## Features
- Multi-asset support
- Step-by-step Jupyter Notebook implementation
- GARCH-based volatility filtering
- Technical Indicators
- ML models: Random Forest, XGBoost, MLP
- Backtesting with stop-loss, take-profit, and transaction costs
- Inline plots and performance metrics

- **Technical Indicator Strategies**: BB, MACD, RSI  
- **GARCH Volatility Filtering**: Used as a risk filter and ML feature  
- **Machine Learning Models**: Random Forest, XGBoost, MLP for 3-class trading signals (`-1` = sell, `0` = hold, `1` = buy)  
- **Backtesting Framework**: Stop-loss, take-profit, volatility-threshold 
- **Evaluation Metrics**: Total return, annualized return & volatility, Sharpe ratio, maximum drawdown, win rate, average gain/loss, profit factor, Jensen’s alpha  
- **Permutation Testing**: Robust evaluation of model performance (return permutation & Signal permutation )
- **Self-contained Workflow**: Each notebook can run independently for one asset  

---

## Usage
1. Open the notebook you want to run

2. **Run all cells sequentially**. The notebook will
- Load and preprocess the historical price data
- Compute technical indicators (BB, MACD, RSI)
- Compute GARCH volatility forecasts
- Generate trading signals (technical and ML-based)
- Run backtesting and evaluate strategy performance
- Generate plots and metrics inline


3. **Data download** All historical price data is downloaded automatically; no additional files are required

> **Switching Assets:** To analyze a different asset, open the corresponding notebook. Each notebook is self-contained for a single asset.

---

## Dataset Information
- Historical asset data and risk-free rate is downloaded via **Yahoo Finance** using `yfinance` and `pandas_datareader`
- Assets include AAPL, GLD, USO, SPY and QQQ
- Time Range: 2004-01-01 to 2024-12-31
- Frequency: Daily

---

## Environment
- All notebooks were developed and executed in **Google Colab**, , so local installation is not strictly required.


---

## Reproductivity Note

Machine learning models and GARCH volatility forecasts introduce randomness in training and optimization processes.
As a result, running the notebooks multiple times may lead to slightly different predictions and performance metrics.

To ensure transparency and verify the results presented in the dissertation:

- The `Data/` folder contains OHLC data, adjusted close price and GARCH forecast for each assets

- The `Results/` folder contains the final performance and sensitivity testing result, organized by asset.

These files reflect the exact outputs used in the dissertation, even if live runs differ slightly.

>**Note:** When running the notebooks, outputs will be displayed in the notebook and basic CSV files and visualization plot may be generated in the working directory, but they will not automatically save to the`Data/` or `Results/` folders. These files are provided for verification of the dissertation findings.



---

## License
This project is part of an MSc dissertation and intended for academic purposes only.