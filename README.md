# Cryptocurrency Price Prediction Using Machine Learning

## 📌 Project Overview

This project applies machine learning techniques to predict cryptocurrency prices using historical market data from **Bitcoin** and **Ethereum**.

The project explores historical price patterns and uses different regression algorithms to predict the **next day's closing price**. Three machine learning models are implemented and compared:

* Random Forest Regression
* Linear Regression
* K-Nearest Neighbours (KNN) Regression

The models are evaluated using **Root Mean Squared Error (RMSE)** and **R² (R-squared)** to assess their prediction performance.

---

## 🎯 Objectives

The main objectives of this project are to:

1. Analyse historical Bitcoin and Ethereum price data.
2. Prepare and clean the cryptocurrency datasets for modelling.
3. Create a target variable representing the future closing price.
4. Engineer additional features from historical price data.
5. Examine feature relevance using a Chi-Square feature selection approach.
6. Train multiple regression models for cryptocurrency price prediction.
7. Compare model performance using RMSE and R².
8. Visualise actual versus predicted prices and model performance.

---

## 📊 Datasets

The project uses two historical cryptocurrency datasets:

### Bitcoin

**File:** `bitcoin.csv`

### Ethereum

**File:** `ethereum.csv`

The datasets contain historical cryptocurrency market information, including variables such as:

* Date
* Open price
* High price
* Low price
* Closing price
* Trading volume

The exact columns available differ slightly between the Bitcoin and Ethereum datasets.

---

## 🔧 Data Preparation

The datasets are loaded using Pandas, and the date columns are converted into datetime format.

Missing values are also checked before modelling.

A new target variable called `Target` is created by shifting the closing price by one observation:

```python
eth_data["Target"] = eth_data["Close"].shift(-1)
btc_data["Target"] = btc_data["Close"].shift(-1)
```

This means that the model uses the current market information to predict the **following closing price**.

---

## ⚙️ Feature Engineering

Two additional variables are created:

### Price Spread

```text
Price_Spread = High - Low
```

This represents the daily difference between the highest and lowest recorded prices.

### Price Change

```text
Price_Change = Close.pct_change()
```

This represents the percentage change in the closing price between observations.

The engineered features provide additional information about daily cryptocurrency price movement.

---

## 🔍 Feature Selection

A Chi-Square test is used to examine the relationship between the available features and the target variable.

Because the Chi-Square test is designed for categorical/non-negative data, numerical variables are first converted into five bins using `KBinsDiscretizer`.

The feature sets include:

### Bitcoin

* Open
* High
* Low
* Close
* Volume
* Pri
