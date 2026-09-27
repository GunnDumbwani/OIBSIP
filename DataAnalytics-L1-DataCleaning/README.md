# Retail Customer Data Cleaning

Track: Data Analytics (OIBSIP), Level 1 - Task 3

## Objective
Take a deliberately messy customer database export and systematically clean it into an
analysis-ready dataset, documenting every decision made along the way.

## Dataset
`messy_customer_data.csv` - 538 synthetic retail customer records with columns:
CustomerID, Name, Age, Gender, City, SignupDate, PurchaseAmount.

Deliberately includes:
- Missing values in Age, Gender, City, and PurchaseAmount
- 18 exact duplicate rows
- Gender written 8 different ways (Male/male/M/MALE/Female/female/F/FEMALE)
- City written inconsistently (mumbai/MUMBAI/Bombay, bangalore/BANGALORE/Bengaluru)
- SignupDate in 4 different formats (YYYY-MM-DD, DD/MM/YYYY, MM-DD-YYYY, DD-Mon-YYYY)
- A few impossible values (negative age, age of 150, negative purchase amount, one
  ₹99,999.99 outlier)

## Tech Stack
Python, pandas, numpy, Jupyter Notebook.

## Approach
1. Load the data and produce an initial data quality report (nulls, duplicates, category
   spellings, value ranges).
2. Remove the 18 exact duplicate rows.
3. Standardise Gender and City spellings into consistent categories.
4. Parse the 4 mixed date formats into a single datetime column.
5. Fix impossible Age values (outside 0-100) and impute missing/invalid ages with the
   median.
6. Impute missing PurchaseAmount with the median, then cap remaining outliers using the
   IQR method.
7. Fill the small number of missing City values with "Unknown" rather than guessing.
8. Correct final data types (CustomerID and Name as string).
9. Produce a before/after summary table and save the cleaned dataset.

## Before vs. After

| Metric             | Before | After |
|---------------------|--------|-------|
| Rows                | 538    | 520   |
| Total nulls         | 59     | 0     |
| Duplicate rows      | 18     | 0     |
| Gender categories   | 8      | 2     |
| City categories     | 16     | 10    |

## Files in this folder
- `Data_Cleaning_Analysis.ipynb` - full cleaning notebook, run end to end
- `messy_customer_data.csv` - raw, uncleaned dataset
- `cleaned_customer_data.csv` - output file after cleaning
- `README.md`

## How to Run
```
pip install pandas numpy jupyter
jupyter notebook Data_Cleaning_Analysis.ipynb
```
Run all cells top to bottom. No external downloads or API keys needed.
