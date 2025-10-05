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
3.  **Market Insights:** To uncover patterns and trends within the used car market, such as popular brands, price-mileage correlation, etc.
4.  **Workflow Practice:** To practice an end-to-end data analysis workflow from raw data to business insights.

---
## Project Workflow

This project is divided into two main phases:

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

**2. Exploratory Data Analysis (EDA) & Visualization (Next Phase)**
With a clean dataset, the next phase is to dive deeper to find insights through:
* Univariate and bivariate analysis.
* Data visualization to identify correlations and patterns.
* Answering specific business questions related to the used car market.

---
## Tools and Technologies

* **Python**
* **Pandas** (for data manipulation and cleaning)
* **NumPy** (for numerical operations)
* **Matplotlib** & **Seaborn** (for data visualization)
* **Google Colab** (as the development environment)

---
## Key Findings (To Be Added)

This section will be updated upon completion of the Exploratory Data Analysis (EDA) phase. Expected insights include:
* The correlation between price, mileage, year, and condition.
* The most common car makes and models in the market.
* Price distributions across different regions.
