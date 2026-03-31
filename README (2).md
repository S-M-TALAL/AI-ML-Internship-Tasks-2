# 🤖 AI/ML Engineering Internship Tasks

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0+-orange?logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Task Objective

The goal of this task is to **predict short-term stock prices** using historical market data.  
Specifically, the model predicts the **next day's closing price** of a stock (TSLA — Tesla Inc.) based on the current day's Open, High, Low, and Volume values.

This is a **supervised regression problem** designed to explore and compare the performance of multiple machine learning models on real-world financial time-series data.

---

## 📊 Dataset Used

| Property       | Details                            |
|----------------|------------------------------------|
| **Source**     | Yahoo Finance (`yfinance` library) |
| **Stock**      | TSLA (Tesla Inc.)                  |
| **Date Range** | January 1, 2022 — December 31, 2024 |
| **Features**   | Open, High, Low, Volume            |
| **Target**     | Next Day's Closing Price           |
| **Split**      | 60% Train / 40% Test (time-based) |

---

## 🧠 Models Applied

### 1. 📈 Linear Regression
- Baseline model
- Solves mathematically in one step (no epochs)
- Fast and interpretable

### 2. 🌲 Random Forest Regressor
- Ensemble of **200 decision trees**
- Trained incrementally with progress checkpoints (10 → 200 trees)
- Captures non-linear relationships in the data

### 3. 🧬 Neural Network (MLPRegressor)
- Architecture: `128 → 64 → 32` hidden layers
- Activation: `ReLU`
- Trained for **200 epochs** with warm start
- Learning Rate: `0.001`
- StandardScaler applied before training

---

## 📈 Key Results and Findings

### Model Evaluation Metrics (on Test Set)

| Model              | MAE (↓ better) | RMSE (↓ better) | R² Score (↑ better) |
|--------------------|---------------|-----------------|----------------------|
| Linear Regression  | —             | —               | Baseline             |
| Random Forest      | —             | —               | Best overall         |
| Neural Network     | —             | —               | Improved with epochs |

> 📝 *Run the notebook to see exact metric values — they depend on live data fetched from Yahoo Finance.*

### Key Findings

- ✅ **Random Forest** outperformed Linear Regression by capturing non-linear price patterns
- ✅ **Neural Network** showed consistent loss reduction across 200 epochs with accuracy improvement
- ✅ **Feature Engineering** — using `shift(-1)` on Close price as the target was effective for next-day prediction
- ⚠️ Stock prediction is inherently noisy; all models perform better on short-term trends than sudden volatility
- 📉 Linear Regression struggled with large price swings due to its assumption of linear relationships

---

## 🗂️ Project Structure

```
📦 AI-ML-Internship-Tasks/
├── 📓 AI_ML_Engineering_Internship_Tasks_2.ipynb   ← Main notebook
├── 📊 stock_prediction.png                          ← Actual vs Predicted plot
├── 📉 epoch_training.png                            ← Neural network training curves
└── 📄 README.md                                     ← This file
```

---

## ⚙️ How to Run

### Prerequisites
```bash
pip install yfinance scikit-learn matplotlib pandas numpy
```

### Steps
1. Clone this repository
2. Open the Jupyter Notebook:
   ```bash
   jupyter notebook AI_ML_Engineering_Internship_Tasks_2.ipynb
   ```
3. Run all cells from top to bottom
4. Results and plots will be generated automatically

---

## 🛠️ Technologies Used

- **Python 3.8+**
- **Jupyter Notebook**
- `yfinance` — Stock data download
- `scikit-learn` — ML models (LinearRegression, RandomForest, MLPRegressor)
- `pandas` / `numpy` — Data manipulation
- `matplotlib` — Visualization



*This project was completed as part of an AI/ML Engineering Internship program.*
