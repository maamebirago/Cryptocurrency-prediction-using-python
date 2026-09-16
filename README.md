# Cryptocurrency Price Prediction

## 📌 Overview

This project uses machine learning to predict the future closing prices of **Bitcoin and Ethereum** using historical cryptocurrency market data.

The datasets contain **113 columns**, providing a broad range of historical market variables. For the prediction models, selected price-related features are used, including **Open, High, Low, and Close** prices. Additional features such as **Price Change** and **Price Spread** are also explored during feature analysis.

The project compares three regression algorithms:

* Random Forest Regression
* Linear Regression
* K-Nearest Neighbours (KNN) Regression

---

## 🎯 Objectives

* Analyse historical Bitcoin and Ethereum data.
* Prepare the datasets for machine learning.
* Create a target variable representing the **next closing price**.
* Perform feature analysis using the Chi-Square test.
* Train and compare different regression models.
* Evaluate predictions using **RMSE** and **R²**.
* Visualise actual and predicted cryptocurrency prices.

---

## 📊 Datasets

The project uses two datasets:

* `bitcoin.csv`
* `ethereum.csv`

Each dataset contains **113 columns** of cryptocurrency-related historical data. The modelling stage focuses on selected market-price variables rather than using all available columns.

---

## 🔧 Data Preparation

The data is loaded using Pandas and the date fields are converted into datetime format. Missing values are checked and handled before modelling.

A future closing-price target is created by shifting the `Close` column by one observation:

```python
Target = Close.shift(-1)
```

This allows the models to predict the following closing price.

Additional features are created:

* **Price Spread** = High − Low
* **Price Change** = percentage change in Close price

---

## 🔍 Feature Selection

A Chi-Square feature selection approach is applied after converting numerical variables into categorical bins.

The analysis calculates Chi-Square scores for the selected Bitcoin and Ethereum features to examine their relationship with the target variable.

---

## 🤖 Machine Learning Models

The data is divided into **80% training and 20% testing sets**.

Three regression models are trained:

### Random Forest Regression

An ensemble model using 100 decision trees.

### Linear Regression

Used as a baseline regression approach.

### KNN Regression

Uses the five nearest observations to generate predictions.

---

## 📏 Model Evaluation

Model performance is evaluated using:

* **RMSE (Root Mean Squared Error):** measures prediction error, with lower values indicating smaller errors.
* **R² (R-squared):** measures how much variation in the target is explained by the model.

The project calculates both metrics for Bitcoin and Ethereum across all three models.

---

## 📈 Results & Visualisation

The project includes:

* Actual vs. predicted Bitcoin prices
* Actual vs. predicted Ethereum prices
* RMSE comparison between the three models
* Prediction tables containing actual and predicted prices

These visualisations help compare the performance of the different approaches.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

---

## 🚀 How to Run

Clone the repository and install the required Python libraries:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

Ensure `bitcoin.csv` and `ethereum.csv` are in the appropriate project directory, then open and run the Jupyter Notebook.

---

## ⚠️ Disclaimer

This project is intended for **educational and analytical purposes**. Cryptocurrency prices are highly dynamic and influenced by many factors that are not included in the model. The predictions should therefore not be interpreted as financial advice or guaranteed future prices.

---

## 👩🏽‍💻 Author

**Maame Birago**

MSc Data Analytics

GitHub: `github.com/maamebirago`

