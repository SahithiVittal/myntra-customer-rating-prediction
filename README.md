# 🛍️ Myntra Customer Rating Prediction using Machine Learning

## 📌 Project Overview

Customer ratings significantly influence purchasing decisions on e-commerce platforms. Predicting customer ratings enables businesses to identify products that may receive poor reviews, optimize pricing strategies, improve seller performance, and enhance customer satisfaction.

This project develops and compares **Classification** and **Regression** machine learning models to predict customer ratings using product, pricing, seller, and category-related features.

---

## 🎯 Business Problem

The objective of this project is to build predictive models that can:

- Predict customer rating categories (Low, Medium, High)
- Predict the exact customer rating
- Identify the factors influencing customer ratings
- Compare multiple machine learning algorithms
- Generate actionable business recommendations

---

## 📂 Dataset

- **Records:** 270,419 products
- **Features:** 13 original features

### Original Features

- Product Name
- Product Image URL
- Price
- MRP
- Rating
- Total Ratings
- Seller
- Product URL
- Sub-category
- Gender
- Category
- Discount Percentage
- Deep Discount Indicator

---

## ⚙️ Feature Engineering

### Feature Extraction

The following features were extracted from existing data:

| Feature | Source | Purpose |
|---------|--------|---------|
| Category | Sub-category | Derived the main product category |
| Gender | Product Name | Identified the target customer gender |
| Sub-category | Product URL | Extracted product sub-category information |

### Engineered Features

| Feature | Description |
|---------|-------------|
| Discount Percentage | Percentage discount calculated from Price and MRP |
| Deep Discount Indicator | Identifies heavily discounted products |
| Category-Gender | Combines category and gender to capture customer targeting intent |
| Seller Frequency | Number of products listed by each seller |
| Sub-category Frequency | Number of products within each sub-category |
| Rating Category | Converted ratings into Low, Medium, and High classes for classification |

---

## 🔍 Exploratory Data Analysis

The exploratory analysis included:

- Missing Value Analysis
- Distribution of Numerical Features
- Outlier Detection
- Seller-wise Product Analysis
- Rating vs Total Ratings Analysis
- Correlation Analysis

### Key Insights

- Most products received ratings between **4.0 and 4.5**.
- Product prices and MRP exhibited right-skewed distributions.
- Product popularity (Total Ratings) varied significantly across products.
- Price and MRP showed a strong positive correlation.
- Customer ratings had relatively weak linear correlations with individual numerical variables.

---

## 📊 Statistical Testing

Statistical tests were performed to validate assumptions and identify significant relationships between variables before model development.

### Tests Performed

| Statistical Test | Purpose |
|------------------|---------|
| **Shapiro-Wilk Test** | Evaluated whether numerical variables followed a normal distribution. |
| **Spearman Rank Correlation** | Measured the monotonic relationship between numerical variables since the data was not normally distributed. |
| **Chi-Square Test** | Assessed the association between categorical variables and the customer rating category. |

### Key Findings

- The **Shapiro-Wilk Test** indicated that the numerical variables were **not normally distributed**.
- Therefore, the **Spearman Rank Correlation**, a non-parametric statistical test, was used instead of Pearson Correlation.
- The **Chi-Square Test** was used to evaluate the relationship between categorical features and the target variable, helping identify statistically significant predictors.


---

## 🤖 Machine Learning Models

### Classification Models

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- XGBoost Classifier

### Regression Models

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor

---

# 📈 Model Performance

## Classification Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|--------|---------:|----------:|--------:|---------:|--------:|
| Logistic Regression | 75.10% | 56.42% | 75.10% | 64.43% | 0.579 |
| Decision Tree | 75.47% | 76.17% | 75.47% | 75.79% | 0.699 |
| **Random Forest** ⭐ | **80.55%** | **78.97%** | **80.55%** | **79.21%** | **0.843** |
| XGBoost | 76.29% | 72.22% | 76.29% | 69.32% | 0.787 |

---

## Regression Results

| Model | MAE | RMSE | R² Score |
|--------|-----:|------:|---------:|
| Linear Regression | 0.361 | 0.500 | 0.025 |
| Decision Tree | 0.310 | 0.534 | -0.113 |
| **Random Forest** ⭐ | **0.272** | **0.415** | **0.328** |
| XGBoost | 0.325 | 0.456 | 0.191 |

---

## 🌟 Feature Importance

Feature importance analysis was performed using the best-performing Random Forest models.

### Key Findings

The most influential features were:

- Total Number of Ratings (`ratingTotal`)
- Seller Frequency
- Discount Percentage
- Price
- MRP

These results indicate that customer engagement and pricing-related factors have a stronger influence on customer ratings than product category alone.

---

## 📌 Classification vs Regression

### Classification

- Predicts rating categories (Low, Medium, High)
- Best Model: **Random Forest Classifier**
- Accuracy: **80.55%**

### Regression

- Predicts exact customer ratings
- Best Model: **Random Forest Regressor**
- R² Score: **0.328**

Both approaches consistently identified similar key predictors, demonstrating the importance of customer engagement and pricing features.

---

## 💼 Business Recommendations

Based on the analysis:

- Improve quality for products predicted to receive low ratings.
- Monitor seller performance using historical customer ratings.
- Optimize pricing strategies for heavily discounted products.
- Prioritize inventory from consistently high-performing sellers.
- Use predictive models to identify products requiring proactive quality improvements.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- SciPy
- Jupyter Notebook

---

## 📁 Project Structure

```
Myntra-Customer-Rating-Prediction/
│
├── Myntra_Customer_Rating_Prediction.ipynb
├── README.md
├── requirements.txt
├── data/
│   └── myntra_dataset.csv
└── images/
```


## 📌 Future Improvements

- Hyperparameter tuning using GridSearchCV and RandomizedSearchCV
- Model deployment using Streamlit or Flask
- Real-time customer rating prediction
- Integration with recommendation systems
- Explainable AI using SHAP or LIME

---

## 👩‍💻 Author

**Sahithi Vittal**

- 📧 Email: sahithi.vittal@gmail.com
- 💼 LinkedIn: (https://www.linkedin.com/in/vittal-sahithi/)

---

## ⭐ If you found this project useful, consider giving it a star!
