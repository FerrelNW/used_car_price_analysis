# Used Car Price Analysis & Prediction - A Craigslist Data Case Study

This project is a comprehensive case study covering the full data science lifecycle: **data cleaning**, **exploratory data analysis (EDA)**, and **predictive modeling** using a dataset of used car listings from Craigslist. The primary objective is to transform raw, noisy data into actionable market insights and build a robust Machine Learning model to estimate vehicle prices.

This project serves as a portfolio piece demonstrating proficiency in the end-to-end data workflow, from preprocessing raw unstructured data to deploying machine learning algorithms.

---
## Dataset

The dataset used is the **Used Car Dataset** from Kaggle, containing over 400,000 listings scraped from Craigslist.

* **Source:** [Kaggle Used Car Dataset](https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data)

This dataset was selected for its real-world complexity, featuring:
* Extensive missing values (NaNs).
* Inconsistent data types and formats.
* Significant outliers and noise (e.g., prices of $0 or unrealistic mileage).
* Duplicate entries requiring rigorous deduplication.

---
## Project Objectives

1.  **Data Cleaning:** To perform extensive data cleaning and ensure data integrity.
2.  **Price Factor Analysis:** To identify key variables that drive used car market values.
3.  **Market Insights:** To uncover hidden patterns and trends within the automotive secondary market.
4.  **Predictive Modeling:** To build and evaluate a Machine Learning model capable of predicting car prices with high accuracy.
5.  **Workflow Mastery:** To demonstrate a complete data pipeline using Python.

---
## Project Workflow

This project was executed in three main phases:

### 1. Data Cleaning & Preprocessing (Completed)
Focusing on data quality to prepare a reliable foundation for analysis:
* **Handling Irrelevant Features**: Removed non-predictive columns (e.g., URL, ID, VIN, Image URL).
* **Deduplication**: Identified and removed duplicate listings to prevent data leakage.
* **Outlier Management**: Applied domain knowledge to filter unrealistic data:
    * Price range limited to **$1,000 - $100,000**.
    * Odometer capped at **300,000 miles**.
    * Vehicle year restricted to **1990 and newer**.
* **Imputation Strategy**:
    * Categorical features (e.g., `condition`, `cylinders`) filled with 'unknown' to preserve data volume.
    * Critical rows with missing target values were dropped.

### 2. Exploratory Data Analysis (EDA) (Completed)
Uncovering insights through visualization:
* **Univariate Analysis**: Analyzed the right-skewed distribution of Price and Odometer.
* **Bivariate Analysis**: Visualized relationships such as *Price vs. Odometer* (negative correlation) and *Price vs. Manufacturer*.
* **Feature Engineering**: Created a new feature **`vehicle_age`** to better represent depreciation than the raw manufacturing year.

### 3. Predictive Modeling (Completed)
Building a Random Forest Regressor to estimate car prices:
* **Target Transformation**: Applied **Log-Transformation (`np.log1p`)** to the target variable (`price`) to normalize its highly skewed distribution.
* **Preprocessing Pipeline**:
    * **Numerical Features**: Scaled using `StandardScaler`.
    * **Categorical Features**: Encoded using `OneHotEncoder` (with handle_unknown='ignore').
* **Model Selection**: Implemented a **Random Forest Regressor** pipeline.
* **Evaluation**: The model was evaluated using R² Score, MAE (Mean Absolute Error), and RMSE.

---
## Tools and Technologies

* **Python**
* **Pandas & NumPy** (Data Manipulation)
* **Matplotlib & Seaborn** (Data Visualization)
* **Scikit-Learn** (Machine Learning & Preprocessing)
* **Google Colab** (Development Environment)

---
## Key Findings & Model Performance

### Market Insights
* **Depreciation Trends:** The analysis confirmed a strong negative correlation between price and both **vehicle age** and **mileage**. The steepest depreciation occurs in the first few years of ownership.
* **Brand Segmentation:** Manufacturers like **Ram, GMC, and Chevrolet** (Trucks/SUVs) command significantly higher median prices compared to economy brands like **Honda or Kia**.
* **Physical Condition:** Cars listed as 'new' or 'like new' carry a significant price premium, while 'fair' or 'salvage' conditions see a sharp drop in valuation.

### Model Results
The Random Forest model demonstrated strong predictive capabilities:
* **High Accuracy:** The model achieved a solid **$R^2$ Score**, indicating it successfully explains the majority of the variance in car prices.
* **Prediction Alignment:** The *Actual vs. Predicted* plot shows a tight cluster along the ideal diagonal line, proving the model is unbiased for the majority of market data ($5k - $50k range).
* **Feature Importance:** The model identified **Odometer** and **Vehicle Age** as the two most critical predictors of price, far outweighing features like paint color or transmission type.
* **Error Analysis:** The model performs most consistently on cars in 'good' to 'excellent' condition. Error rates slightly increase for 'salvage' vehicles, reflecting the subjective nature of pricing damaged goods.
