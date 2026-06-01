# 💻 Laptop Price Prediction

Laptop price prediction with regression models, preprocessing, feature engineering, cross-validation, regularization, and learning-curve analysis. Compares linear, polynomial, ridge, lasso, and decision tree models using cross-validated evaluation. (Task 1 ML)

<p align="center">
	<a href="Laptop_Prediction.ipynb"><img src="https://img.shields.io/badge/Open%20Notebook-Laptop_Prediction.ipynb-0f766e?style=for-the-badge&logo=jupyter" alt="Open Notebook" /></a>
	<a href="https://www.kaggle.com/competitions/laptop-price-prediction"><img src="https://img.shields.io/badge/Kaggle-Competition-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white" alt="Kaggle" /></a>
	<a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.13-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" /></a>
	<a href="https://scikit-learn.org/"><img src="https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="scikit-learn" /></a>
	<a href="https://jupyter.org/"><img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter Notebook" /></a>
	<a href="https://www.kaggle.com/"><img src="https://img.shields.io/badge/Machine%20Learning-Regression-2E7D32?style=for-the-badge" alt="Machine Learning" /></a>
	<a href="https://scikit-learn.org/"><img src="https://img.shields.io/badge/Regression-Models-1565C0?style=for-the-badge" alt="Regression" /></a>
</p>

## Table of Contents
- [Overview](#overview)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Key Insights](#key-insights)
- [ML Pipeline](#ml-pipeline)
- [Models Used](#models-used)
- [Evaluation Metrics](#evaluation-metrics)
- [Results](#results)
- [Learning Curve Analysis](#learning-curve-analysis)
- [Technologies Used](#technologies-used)
- [Repository Structure](#repository-structure)
- [How to Run](#how-to-run)
- [Future Improvements](#future-improvements)
- [License](#license)

## Overview
This project builds a laptop price prediction pipeline using supervised regression. It combines preprocessing, feature selection, polynomial feature expansion, regularization, and model comparison in a single notebook workflow. The final model explains approximately **81% of price variation** (R² ≈ 0.81) and achieves low mean absolute error.

## Objectives
- Predict laptop prices from structured product features (CPU, RAM, storage, GPU, screen, brand, etc.)
- Compare baseline and regularized regression models.
- Reduce overfitting with feature scaling and cross-validation.
- Select the best model using validation metrics instead of training fit alone.
- Identify which features most influence laptop pricing.

## Dataset
- **881 training samples** + **422 test samples** (unlabeled)
- Features include: brand, CPU model, RAM (GB), storage (type + capacity), GPU, screen size, resolution, weight, OS, etc.
- Target: laptop price (continuous)

## Key Insights
- **RAM** and **CPU speed** have the strongest positive impact on price.
- **Gaming laptops & ultrabooks** are typically more expensive than standard notebooks.
- **Screen size** has minimal influence on price.
- Pricing is driven more by **performance specs** than physical attributes.

## ML Pipeline
1. **EDA** – Statistical summaries, missing value analysis, correlation heatmap, distributions.
2. **Data Cleaning** – Handle missing values, format inconsistent entries.
3. **Feature Engineering**:
   - One‑hot encoding for categorical features (brand, OS, GPU, CPU).
   - Transform screen resolution into width & height.
   - Convert storage to unified GB format.
4. **Feature Selection** – Selected top 24 most relevant features.
5. **Train/Validation Split** – Standard scaling applied after split.
6. **Model Training** – Multiple regression models with K‑Fold CV (k=5).
7. **Hyperparameter Tuning** – GridSearchCV for ridge, lasso, polynomial degree, decision tree.
8. **Final Evaluation** – Compare R², MAE, RMSE on validation set.

## Models Used
- Linear Regression  
- Polynomial Regression (Degree 2)  
- Ridge Regression (L2 regularization)  
- Lasso Regression (L1 regularization)  
- Decision Tree Regressor  

## Evaluation Metrics
- **R²** – Coefficient of determination
- **MAE** – Mean Absolute Error
- **RMSE** – Root Mean Squared Error

## Results
The best performing model was **Tuned Polynomial Ridge Regression**.

| Model | Validation R² | Validation RMSE | Validation MAE |
|-------|--------------|----------------|----------------|
| Linear Regression | ~0.72 | ~320 | ~210 |
| Ridge (tuned) | ~0.76 | ~290 | ~185 |
| Polynomial Ridge (tuned) | **~0.81** | **~240** | **~155** |
| Decision Tree | ~0.70 | ~350 | ~230 |

**Final R² ≈ 0.81** – The model explains ~81% of the variance in laptop prices.

Key observations:
- Polynomial features improved validation performance over plain linear regression.
- Ridge regularization reduced overfitting seen in unregularized polynomial models.
- RAM and CPU speed were confirmed as dominant price drivers.

## Learning Curve Analysis
Learning curves show the classic bias‑variance tradeoff:
- High training performance with a large validation gap → overfitting.
- Regularization narrows the gap and stabilises validation error.
- The tuned polynomial ridge model achieves the most balanced fit.

## Technologies Used
- Python 3.13
- Jupyter Notebook
- pandas, NumPy
- Matplotlib, seaborn
- scikit-learn (LinearRegression, Ridge, Lasso, PolynomialFeatures, DecisionTreeRegressor, GridSearchCV, StandardScaler)

## Repository Structure
```text
Laptop_Price-Prediction_MIU/
├── Laptop_Prediction.ipynb
├── README.md
├── train_data.csv
├── test_data.csv
```

## How to Run
1. Open `Laptop_Prediction.ipynb` in Jupyter Notebook or VS Code.
2. Make sure the CSV files are available in the `data/` folder.
3. Run the notebook from top to bottom.
4. Review the comparison table and the generated `submission.csv`.

## Future Improvements
- Try tree-based ensembles such as Random Forest and Gradient Boosting.
- Add more systematic feature selection and interaction analysis.
- Expand hyperparameter tuning for the best-performing model family.
- Validate the pipeline with a stricter train/validation split strategy.

## License
For academic use within the Machine Learning course context at Misr International University.
