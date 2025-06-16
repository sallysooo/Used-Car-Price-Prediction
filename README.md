# 🚗 Used Car Price Prediction in Germany with Machine Learning
> Development of a Machine Learning-Based Prediction Model For Used Car Listing Prices in Germany

This repository contains the implementation and results of a machine learning project aimed at predicting the **fair listing price of used cars** in the German market. Our study focuses on resolving the problem of **information asymmetry** in online used car transactions by providing **data-driven price estimation tools** for both sellers and buyers.

---
## Table of Contents
1. [Project Overview](#project-overview)
2. [Motivation](#motivation)
3. [Methodology](#methodology)
4. [Results](#results)
5. [Contributions](#contributions)
6. [Paper](#paper)
7. [Technologies](#technologies)

---

## Project Overview

* **Project Type**: Machine Learning Regression
* **Target Market**: German used car listings
* **Goal**: Predict realistic listing prices of used cars using multiple ML models and categorical encoding techniques
* **Models Used**: Multiple Linear Regression (MLR), Random Forest Regression (RFR)
* **Dataset Source**: [Kaggle - German Used Cars Dataset](https://www.kaggle.com/datasets/thedevastator/uncovering-factors-that-affect-used-car-prices)

## Motivation

The used car market has been rapidly expanding as consumers seek alternatives to expensive new vehicles. However, **pricing uncertainty and market opacity** often lead to unfair deals. Our project aims to bridge this gap by:

* Accurately predicting expected listing prices
* Helping sellers avoid undervaluation
* Empowering buyers with pricing insights

## Methodology

### 1. Dataset & Preprocessing

* **Source**: German online car marketplaces (2016)
* **Initial Features**: 21 variables (brand, model, mileage, fuel type, etc.)
* **Final Feature Selection**: Focused on the top 5 most frequent car brands and frequently listed models
* **Preprocessing steps**:

  * Removed duplicate listings (based on vehicle ID and timestamp)
  * Created `Car_Age` as a derived feature
  * Removed outliers from `Horsepower` and `Listing_Price`
  * Filtered invalid or unspecified category entries

### 2. Feature Encoding

We applied two encoding techniques for categorical variables:

* **One-hot Encoding**
* **Target Encoding** (Mean encoding based on `Listing_Price`)

These were evaluated in combination with different regression models to understand how encoding influences performance.

### 3. Models

1. **Multiple Linear Regression (MLR)**
2. **Random Forest Regression (RFR)**

Both models were trained using **5-fold cross-validation**. Hyperparameters for RFR were tuned based on grid search and performance optimization.

## Results

| Model | Encoding | R² Score  | RMSE (€)     |
| ----- | -------- | --------- | ------------ |
| MLR   | One-hot  | 0.741     | 4,214.52     |
| MLR   | Target   | 0.699     | 4,546.95     |
| RFR   | Raw      | 0.867     | 3,042.17     |
| RFR   | Target   | **0.892** | **2,734.41** |

### 🔍 Key Observations

* **MLR** works better with **one-hot encoding**, as it handles linear relationships more effectively.
* **RFR** performs significantly better with **target encoding**, capturing nonlinear patterns in the data.
* RFR with target encoding emerged as the **best-performing model**, outperforming all other configurations.

## Contributions

* Investigated encoding strategies (one-hot vs. target) on categorical variables
* Conducted comparative analysis between linear and nonlinear regressors
* Validated results using standard evaluation metrics (R², RMSE)
* Highlighted implications of encoding choices on model performance

## Paper

This project was conducted as part of a university research initiative and has been summarized in the following paper:

> **Development of a Machine Learning-Based Prediction Model for Used Car Listing Prices in Germany**
> *Kim et al., Sookmyung Women’s University, 2025*

📄 [Read Full Paper](https://github.com/sallysooo/Used-Car-Price-Prediction/blob/main/Development%20of%20a%20Machine%20Learning-based%20Prediction%20Model%20for%20Used%20Car%20Listing%20Prices%20in%20Germany.pdf)

## Technologies

* Python 3.9, KNIME Analytics
* pandas, NumPy
* scikit-learn
* Matplotlib, Seaborn (for visualization)
* Jupyter Notebook

## Future Work

* Extend price prediction to include **classification of pricing tiers** (low, medium, high)
* Incorporate **external economic indicators** for more robust modeling
* Deploy an interactive **web-based prediction tool**

### Contact

For any inquiries or collaboration requests, feel free to contact:

* **Jisoo Kim** – `jisugim168[a.t.]gmail.com`

