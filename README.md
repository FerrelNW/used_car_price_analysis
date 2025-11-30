# Used Car Price Analysis - A Craigslist Data Case Study

This project is a complete case study on the process of **data cleaning** and **exploratory data analysis (EDA)** using a dataset of used car listings from Craigslist. The main objective is to transform raw, unstructured data into a clean, analysis-ready dataset to uncover actionable market insights.

This project is part of my portfolio to demonstrate proficiency in the end-to-end data analysis workflow, from preprocessing raw data to generating insights.

---
## Dataset

The dataset used is the **Used Car Dataset** from Kaggle, which contains over 400,000 listings scraped from Craigslist.

* **Source:** [Kaggle Used Car Dataset](https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data)

This dataset was intentionally chosen as it represents a real-world data challenge, featuring:
* Extensive missing values.
* Inconsistent data formats.
* Outliers and nonsensical data (e.g., a price of $0).
* Duplicate entries.

---
## Project Objectives

1.  **Data Cleaning:** To perform extensive data cleaning to address various data quality issues.
2.  **Price Factor Analysis:** To analyze the key factors that significantly influence used car prices.
3.  **Market Insights:** To uncover patterns and trends within the used car market.
4.  **Workflow Practice:** To practice an end-to-end data analysis workflow from raw data to business insights.

---
## Project Workflow

This project was executed in two main phases:

**1. Data Cleaning & Preprocessing (Completed)**
This stage involved the following steps to ensure data quality and integrity:
* **Handling Irrelevant Columns**: Dropped columns that are not useful for analysis (e.g., URL, ID, VIN).
* **Handling Duplicate Entries**: Identified and removed identical data entries.
* **Cleaning Outliers**: Filtered out nonsensical car prices (e.g., those below $1,000 or above $1,000,000).
* **Handling Missing Values**: Implemented a multi-step imputation strategy:
    * Dropped the 'size' column due to over 70% missing data.
    * Dropped rows that were missing crucial information (`year`, `manufacturer`, `model`).
    * Filled categorical missing values (e.g., `condition`, `cylinders`) with the **mode**.
    * Filled numerical missing values (e.g., `lat`, `long`) with the **median**.

**2. Exploratory Data Analysis (EDA) & Visualization (Completed)**
With a clean dataset, a detailed analysis was conducted to find insights through:
* **Univariate Analysis:** Understood the distributions of key numerical (`price`, `year`, `odometer`) and categorical (`manufacturer`, `condition`, `type`) variables.
* **Bivariate Analysis:** Explored relationships between variables, such as price vs. mileage and price vs. car condition, using scatter plots and box plots.
* **Multivariate Analysis:** Created a correlation heatmap to quantify the linear relationships between all key numerical variables.

---
## Tools and Technologies

* **Python**
* **Pandas** (for data manipulation and cleaning)
* **NumPy** (for numerical operations)
* **Matplotlib** & **Seaborn** (for data visualization)
* **Google Colab** (as the development environment)

---
## Key Findings

The analysis revealed several key insights into the used car market:

* **Market Landscape:** The market is heavily dominated by American and Japanese manufacturers, with **Ford, Chevrolet, and Toyota** being the most frequently listed brands. The majority of vehicles are listed in **'good' or 'excellent' condition**, with **SUVs, sedans, and trucks** being the most common vehicle types.

* **Primary Price Drivers:** The price of a used vehicle is strongly influenced by a few core factors, confirmed through correlation and bivariate analysis:
    * **Vehicle Age (`Year`):** There is a significant **positive correlation (0.37)** between the manufacturing year and price. Newer cars consistently command higher prices.
    * **Mileage (`Odometer`):** A clear **negative correlation (-0.21)** exists. As a vehicle's mileage increases, its market price tends to decrease.
    * **Condition:** A vehicle's condition is a major price determinant. The median price for a car in 'like new' or 'excellent' condition is substantially higher than for one listed as 'good' or 'fair'.
    * **Manufacturer & Type:** Premium brands and certain vehicle types hold their value better. **Trucks and buses** showed the highest average prices, while luxury manufacturers commanded significantly higher price points than common consumer brands.
