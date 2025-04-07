# 📊 Project – Analysis of Linthurst Data


## 📌 Project Overview

This comprehensive project investigates the Linthurst dataset to identify key physicochemical properties of soil that influence biomass production (BIO) in the Cape Fear Estuary, North Carolina. Through the application of advanced regression techniques and collinearity diagnostics, the project demonstrates a robust statistical modeling approach and showcases proficiency in practical regression analysis.

---

## 📁 Dataset Description

### LINTHALL.txt
- 14 predictor variables, 43 observations
- Includes variables such as H2S, SAL, pH, Ca, Mg, Zn, etc.

### LINTH-5.txt
- Subset with 5 predictors
- Used to further validate methods with reduced multicollinearity

---

## 🧠 Methodology

### ✅ Part I – OLS & Collinearity Diagnostics
- Used `lm()` function in R to fit an OLS model with all predictors.
- Diagnosed multicollinearity using:
  - **Variance Inflation Factor (VIF)** – Threshold: VIF > 10
  - **Correlation Matrix & Plot** – Threshold: Correlation > 0.7
- **Findings:** Variables such as pH, Ca, BUF, Zn showed high collinearity.

### 🧪 Part II – Principal Component Regression (PCR)
- Applied PCR to transform correlated predictors into orthogonal principal components.
- Retained 11 PCs (99.41% explained variance).
- Transformed coefficients back to original space.
- **Outcome:** Significant reduction in standard errors of coefficients; slight trade-off in SSE.

### 🔁 Part III – Model Selection & Regularization

#### 📌 Stepwise Regression
- Implemented both forward selection and backward elimination using α = 0.10.
- Final Model: `BIO ~ pH + Na`
- **Confirmed** that collinearity had disappeared via eigenvalue diagnostics.

#### 📉 Ridge Regression
- Applied regularization via ridge regression.
- Used ridge trace to visualize coefficient shrinkage and guide variable selection.
- Final Model obtained with optimized penalty (λ = 0.074).
- Multicollinearity effectively reduced.

#### 📚 Subset Selection (via BIC)
- Evaluated all 2-variable combinations based on BIC.
- In case of ties, applied VIF as a secondary criterion.
- Final Model: `BIO ~ pH + Na`

---

## 📈 Key Results

- **OLS Model SSE:** 3,276,740  
- **PCR Model SSE:** 3,402,208  
- **OLS ∑ Std. Errors:** 4069.579  
- **PCR ∑ Std. Errors:** 575.085  
- **Best 2-variable model:** pH and Na

These results demonstrate improved stability and interpretability of the model with minimal loss in predictive power using appropriate variable selection and regularization techniques.

---

## 🛠 Technologies Used

- **Programming Language:** R
- **Key Packages:** `car`, `MASS`, `leaps`, `ggplot2`, base R

---

## 🧑‍💻 Skills Demonstrated

- Multicollinearity detection and resolution
- Principal Component Analysis (PCA)
- Ridge Regression and trace interpretation
- Stepwise and subset variable selection
- Advanced model diagnostics and evaluation
- Proficient R programming and visualization

---

> *This repository showcases practical expertise in modern regression techniques and a strong foundation in statistical modeling.*
