# Bank Dataset (Cleaned)

## Overview
This repository contains the cleaned version of the raw banking dataset (`raw bank_data cleaned.csv`). The data has been preprocessed to handle missing values, standardize formats, and prepare it for exploratory data analysis (EDA), business intelligence reporting, or machine learning modeling.

---

## Dataset Details
* **File Name:** `raw bank_data cleaned.csv`
* **Format:** Comma-Separated Values (`.csv`)
* **Encoding:** UTF-8
* **Status:** Cleaned & Ready for Analysis

---

## Data Dictionary
*(Note: Update the descriptions and data types below to match the exact columns in your CSV file)*

| Column Name | Data Type | Description | Example |
| :--- | :--- | :--- | :--- |
| `customer_id` | String / Integer | Unique identifier for each bank customer. | `CUST_10045` |
| `age` | Integer | Age of the customer in years. | `34` |
| `gender` | Categorical | Customer gender (standardized). | `Female`, `Male` |
| `account_type` | Categorical | Type of bank account held by the customer. | `Savings`, `Checking` |
| `balance` | Float | Current account balance. | `12450.75` |
| `transaction_date` | Date | Standardized date of the transaction (`YYYY-MM-DD`). | `2025-11-15` |
| `credit_score` | Integer | Customer's credit score. | `720` |
| `is_active` | Boolean | Indicates whether the account is currently active (`1` = Yes, `0` = No). | `1` |
| `churn` | Boolean | Target variable indicating if the customer left the bank (`1` = Yes, `0` = No). | `0` |

---

## Data Cleaning & Preprocessing Steps
The following transformations were applied to convert the raw data into this cleaned dataset:
1. **Removed Duplicates:** Dropped exact duplicate rows based on unique transaction/customer IDs.
2. **Handled Missing Values:** 
   * Imputed missing numerical fields (e.g., `balance`, `credit_score`) using the median/mean.
   * Filled missing categorical fields with `"Unknown"` or the mode.
3. **Standardized Formats:** 
   * Converted all date columns to ISO 8601 format (`YYYY-MM-DD`).
   * Stripped leading/trailing whitespace and standardized text casing (e.g., `"male"` / `"M"` $\rightarrow$ `"Male"`).
4. **Outlier Treatment:** Capped or removed extreme anomalies in numerical columns (e.g., negative ages or impossible balances).
5. **Data Type Correction:** Ensured numerical columns are stored as `int` or `float` rather than strings with currency symbols.

---

## Usage
You can easily load this dataset into Python or R for further analysis:

### Python (Pandas)
```python
import pandas as pd

# Load the cleaned dataset
df = pd.read_csv('raw bank_data cleaned.csv')

# Display basic information and first 5 rows
print(df.info())
print(df.head())
```

### R
```r
# Load the cleaned dataset
df <- read.csv("raw bank_data cleaned.csv", stringsAsFactors = FALSE)

# Inspect the structure
str(df)
head(df)
```

---

## Potential Use Cases
* **Customer Churn Prediction:** Train classification models to identify customers at high risk of leaving.
* **Customer Segmentation:** Cluster customers based on balance, age, and account activity for targeted marketing.
* **Financial Reporting:** Analyze overall deposit trends, regional performance, and account distribution.

---

## License & Attribution
* **Source:** Internal / Raw Bank Data
* **License:** Specify your license here (e.g., MIT, CC BY 4.0, or Proprietary/Internal Use Only).