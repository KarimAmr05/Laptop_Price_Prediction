# 💻 Laptop Price Prediction

A machine learning project that predicts laptop prices based on hardware specifications and features. This project demonstrates the full ML pipeline—from data preprocessing and feature engineering to model training, evaluation, and optimization.

---

## 📌 Project Overview

The goal of this project is to build a regression model capable of accurately estimating the market price of a laptop using its technical specifications.

The dataset includes:
- **881 training samples**
- **422 testing samples**

Each laptop entry contains:
- Hardware specs (CPU, RAM, storage, GPU)
- Physical features (screen size, resolution, weight)
- Brand and category information

---

## 🚀 Key Results

- 📊 **R² Score:** ~0.81  
- 📉 **Low Mean Absolute Error (MAE)**  
- ✅ Model explains ~81% of price variation  

---

## 🧠 Key Insights

- **RAM** and **CPU speed** have the strongest impact on price  
- **Gaming laptops & ultrabooks** are typically more expensive  
- **Screen size** has minimal influence on price  
- Pricing is driven more by **performance specs** than physical attributes  

---

## 🔍 Project Workflow

### 1. Data Exploration (EDA)
- Statistical summaries
- Missing value analysis
- Correlation heatmap
- Distribution analysis (histograms, boxplots)

### 2. Data Preprocessing
- Handling missing values  
- Feature formatting and consistency  

### 3. Feature Engineering
- **One-Hot Encoding** for categorical features:
  - Brand, OS, GPU, CPU, etc.
- **Feature transformations:**
  - Resolution → Width & Height
  - Storage → unified GB format  

### 4. Feature Selection
- Selected top **24 most relevant features**
- Removed redundant and weak predictors  

### 5. Model Training

Models used:
- Linear Regression  
- Polynomial Regression (Degree 2)  
- Ridge Regression  
- Lasso Regression  
- Decision Tree Regressor  

### 6. Model Validation

- **K-Fold Cross-Validation (k=5)**
- Metrics used:
  - R² Score  
  - MAE  
  - RMSE  

### 7. Model Optimization

- **Feature Scaling** using StandardScaler  
- **Regularization:**
  - Ridge (L2)
  - Lasso (L1)
- **Hyperparameter tuning** using GridSearchCV:
  - Ridge: alpha  
  - Polynomial: degree  
  - Decision Tree: depth & splits  

### 8. Final Model Selection

The final model was chosen based on:
- Highest R²  
- Lowest MAE & RMSE  
- Stable cross-validation performance  

---

## 🛠️ Technologies Used

- Python 🐍  
- Pandas & NumPy  
- Matplotlib & Seaborn  
- Scikit-learn  

---

## 📈 Future Improvements

- Use advanced models (XGBoost, Random Forest)
- Deploy as a web app (Streamlit / Flask)
- Add real-time price prediction API
- Expand dataset for better generalization
