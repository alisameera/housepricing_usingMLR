# House Price Prediction — Multiple Linear Regression

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Regression-orange?style=flat&logo=scikitlearn&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-OLS-blue?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

---

## Overview

End-to-end regression project to predict house prices using Multiple Linear Regression. Emphasis on building a **statistically sound, interpretable model** — including feature importance analysis, categorical encoding, and performance evaluation on a held-out test set.

---

## Model Results

| Metric | Value |
|--------|-------|
| R² (test set) | **0.67** |
| RMSE | **~1.32 million** |
| Train/Test Split | 70/30 |
| Dataset size | 545 rows, 13 columns |

The model explains **67% of the variance** in house prices — a solid baseline for a linear model on this feature set.

---

## Feature Importance (OLS Coefficients)

| Feature | Coefficient | Direction |
|---------|------------|-----------|
| **Area (sqft)** | ~2.5 million | ↑ Strongest positive predictor |
| **Bathrooms** | ~2.2 million | ↑ Strong positive |
| **Air conditioning** | ~1.5 million | ↑ Moderate positive |
| **Hot water heating** | ~1.4 million | ↑ Moderate positive |
| **Stories** | ~1.2 million | ↑ Moderate positive |
| Guestroom / Basement | ~0.5–0.8 million | ↑ Weak positive |
| **Unfurnished status** | ~-0.5 million | ↓ Negative vs furnished baseline |

---

## Dataset

| Attribute | Detail |
|-----------|--------|
| File | Housing.csv |
| Rows | 545 |
| Columns | 13 |
| Missing values | None |
| Duplicates | None |
| Median price | ~4.34 million |
| Median area | ~4,600 sqft |

**Features:** area, bedrooms, bathrooms, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, prefarea, furnishingstatus

---

## Key Findings

- **Area and bathrooms** are the two strongest price drivers — together they account for the majority of the model's predictive power
- **Air conditioning and preferred area** add significant premium — buyers pay for comfort and location
- **Furnishing status matters** — unfurnished homes priced ~0.5M lower than furnished baseline
- **Bedrooms alone are a weak predictor** — size (area) matters more than bedroom count
- Pairplot confirmed area and bathrooms have strongest positive correlations with price

---

## Pipeline

```
Housing.csv (545 rows, 13 columns)
        │
        ▼
EDA
  ├── Pairplot — correlation with price
  ├── Boxplots — categorical feature impact
  └── Distribution analysis — skewness check
        │
        ▼
Preprocessing
  ├── Binary encoding (yes/no → 1/0)
  ├── One-hot encoding (furnishingstatus)
  └── Feature scaling (StandardScaler)
        │
        ▼
Train/Test Split (70/30)
        │
        ▼
MLR Model (OLS via Statsmodels + Scikit-learn)
        │
        ▼
Evaluation
  ├── R² = 0.67
  ├── RMSE = ~1.32M
  └── Feature coefficient analysis
```

---

## Future Improvements

- VIF (Variance Inflation Factor) check to address potential multicollinearity
- Regularisation: Ridge / Lasso regression
- Non-linear models: Random Forest, XGBoost for comparison
- Log transformation of price to handle right skew

---

## Tech Stack

`Python` · `Pandas` · `NumPy` · `Scikit-learn` · `Statsmodels` · `Matplotlib` · `Seaborn` · `Jupyter`

---

## Files

```
├── housepricing_MLR.ipynb    ← main notebook
├── Housing.csv               ← dataset
└── README.md
```

---

## Author

**Sameera Ali** | [LinkedIn](https://www.linkedin.com/in/sameera-ali-0055252a2/) | [GitHub](https://github.com/alisameera)
