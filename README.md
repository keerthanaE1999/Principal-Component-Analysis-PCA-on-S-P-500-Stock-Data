# 📊 PCA-Based Analysis of S&P 500 Stock Prices

This project applies *Principal Component Analysis (PCA)* to historical stock price data of S&P 500 companies. The goal is to reduce dimensionality, understand market trends, and visualize hidden structures in stock behavior using unsupervised learning techniques.

---

## 📁 Dataset

- *Source:* [Kaggle - S&P 500 Stock Data](https://www.kaggle.com/datasets/camnugent/sandp500)
- *File Used:* all_stocks_5yr.csv
- *Features:*
  - date: Trading date
  - open, high, low, close, volume
  - Name: Stock ticker symbol

---

## 📌 Objectives

- Load and clean historical stock price data.
- Compute daily returns for each stock.
- Apply PCA to reduce feature space.
- Visualize the principal components to detect market patterns.

---

## 🧪 Technologies Used

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn

---

## 🧷 Key Steps

### 1. Load and Pivot the Data

```python
import pandas as pd

df = pd.read_csv('all_stocks_5yr.csv')
df['date'] = pd.to_datetime(df['date'])
pivot_df = df.pivot(index='date', columns='Name', values='close').dropna(axis=1)
