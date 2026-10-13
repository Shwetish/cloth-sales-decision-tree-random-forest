# Cloth Manufacturing Sales Prediction & Analysis
Predicting and analyzing key attributes contributing to high sales in a cloth manufacturing company using Decision Tree and Random Forest models.



## 1. Business Problem
### 1.1. What is the business objective?
The primary business objective is to identify and analyze the key attributes and factors that contribute to high product sales for a cloth manufacturing company. By converting sales into a categorical target variable (e.g., High vs. Low/Medium), the company aims to understand purchasing patterns and optimize inventory, marketing, and distribution strategies.
### 1.2. Are there any constraints?
* Data quality constraints regarding categorical encoding and potential class imbalance in sales tiers.
* Interpretability constraints: The model needs to clearly highlight feature importance so business stakeholders can act upon the insights.

---

## 2. Data Dictionary
| Feature Name | Data Type | Relevance to Model Building | Description & Reason for Inclusion/Exclusion |
| :--- | :--- | :--- | :--- |
| `Sales` | Continuous / Float | **Target (Transformed)** | Target variable representing sales turnover; converted into categorical classes (e.g., High vs. Low) for classification. |
| `CompPrice` | Numerical (Float) | Relevant | Price charged by competitor at each location; critical for pricing strategy analysis. |
| `Income` | Numerical (Integer) | Relevant | Community median income level, indicating customer purchasing power. |
| `Advertising` | Numerical (Integer) | Relevant | Local advertising budget for the company at each location. |
| `Population` | Numerical (Integer) | Relevant | Population size in the region/location area. |
| `Price` | Numerical (Float) | Relevant | Price company charges for the cloth items at each site. |
| `ShelveLoc` | Categorical | Relevant | Shelf location (Bad, Medium, Good) of the product at stores. |
| `Age` | Numerical (Integer) | Relevant | Average age of the local population. |
| `Education` | Numerical (Integer) | Relevant | Educational level at each location. |
| `Urban` | Categorical (Binary) | Relevant | Whether the store is in an urban or rural location. |
| `US` | Categorical (Binary) | Relevant | Whether the store is in the US or not. |

---

## 3. Exploratory Data Analysis (EDA)
* **3.1 Summary:** Statistical overview of numerical and categorical attributes, identifying central tendencies, dispersions, and missing values.
* **3.2 Univariate Analysis:** Distribution plots (histograms and box plots) for numerical features (`Price`, `Income`, `Advertising`) and count plots for categorical variables (`ShelveLoc`, `Urban`, `US`).
* **3.3 Bivariate Analysis:** Correlation heatmaps and scatter/box plots comparing features against the categorical sales target to uncover key drivers.

---

## 4. Data Pre-processing
* **4.1 Data Cleaning & Feature Engineering:** Handled missing values, encoded categorical features using Label Encoding / One-Hot Encoding, and discretized the continuous `Sales` column into categorical bins (e.g., `<= 8` as 'Low', `> 8` as 'High'). Feature scaling applied where necessary.

---

## 5. Model Building
* **5.1 Scaled Data Preparation:** Features standardized using `StandardScaler` to optimize distance-based operations and convergence.
* **5.2 Algorithm Implementation:** Built both **Decision Tree Classifier** (with tuned max depth and criterion) and **Random Forest Classifier** (ensemble of trees with bootstrapping).
* **5.3 Training, Testing & Cross-Validation:** Split data into train and test sets (e.g., 80-20 split). Performed K-Fold cross-validation. Compared models using **Accuracy**, **Precision**, **Recall**, and F1-Score to evaluate false positives and false negatives.
* **5.4 Model Output Explanation:** Visualized decision tree structures and feature importance rankings from Random Forest to show which factors drive high sales.

---

## 6. Business Benefits & Impact
* Enables management to pinpoint critical sales drivers (e.g., shelf location, advertising budget, pricing).
* Optimizes marketing spend and retail placement strategies to boost revenue and profitability.
