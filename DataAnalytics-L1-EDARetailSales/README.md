# EDA on Retail Sales Data

## Objective
Exploratory data analysis on a retail sales dataset to uncover sales patterns, customer trends, and actionable business insights.

## Dataset
Sample Superstore Sales Dataset — ~9,994 orders (2014–2017), covering products, categories, regions, sales, and profit.

## Tools
Python, pandas, matplotlib, seaborn, Jupyter Notebook

## Analysis covered
- Data inspection: shape, dtypes, null check
- Descriptive statistics
- Monthly & quarterly sales trends
- Customer segment and regional breakdown
- Top 10 best-selling products, revenue by category
- Correlation heatmap
- Discount vs profit relationship
- Business recommendations

## Key findings
- Sales peak every Q4, Q1 is consistently weakest
- Discount is negatively correlated with profit (-0.22)
- Furniture/Technology turn loss-making past ~30-40% discount
- Consumer segment drives the most order volume

## How to run
```
pip install pandas matplotlib seaborn jupyter
jupyter notebook EDA_Retail_Sales.ipynb
```
