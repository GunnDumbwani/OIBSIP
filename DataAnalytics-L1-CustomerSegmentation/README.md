# Customer Segmentation Analysis

Track: Data Analytics (OIBSIP), Level 1 - Task 2

## Objective
Apply RFM (Recency, Frequency, Monetary) analysis and K-Means clustering to segment an
e-commerce company's customer base into distinct behavioural groups, so marketing efforts
can be targeted instead of one-size-fits-all.

## Dataset
Online_Retail_Transactions.csv - a transactional export with columns:
InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country

Around 900 customers, ~14,500 order lines across one year. Includes some realistic
messiness: a small number of cancelled orders (negative quantity, invoice numbers prefixed
"C") and about 1% of rows with a missing CustomerID. Both are cleaned out before the
analysis, as shown in the notebook.

## Tech Stack
Python, pandas, numpy, scikit-learn (KMeans, StandardScaler), matplotlib, seaborn,
Jupyter Notebook.

## Approach
1. Load data and check for nulls / inconsistent rows.
2. Clean: drop rows with missing CustomerID, drop cancellations (negative quantity),
   compute per-line revenue.
3. Engineer RFM features per customer (Recency, Frequency, Monetary).
4. Log-transform Frequency and Monetary since they're right-skewed, then standardise
   all three features.
5. Use the elbow method to pick the number of clusters (k=4).
6. Fit K-Means, visualise the clusters (Recency vs Monetary, Frequency vs Monetary).
7. Profile each cluster's average RFM values and turn them into named segments.
8. Write a marketing recommendation for each segment.

## Key Findings

| Segment | % of Customers | Behaviour |
|---|---|---|
| Champions | 27% | Recent, frequent (13 orders avg), highest spend (£1,361 avg) |
| New / One-off Buyers | 18% | Very recent but only 1-2 orders, lowest spend |
| Occasional Regulars | 36% | Moderate on all metrics, buy every couple of months |
| At Risk / Lapsed | 20% | Haven't ordered in about 8 months, but decent historical value (£674 avg spend) |

The At-Risk segment is 20% of customers and has proven historical value, so a win-back
campaign here is probably cheaper than acquiring a new customer from scratch. That's the
main actionable takeaway from this analysis.

## Files in this folder
- Customer_Segmentation_Analysis.ipynb - full analysis notebook, run end to end
- Online_Retail_Transactions.csv - raw dataset
- rfm_segments.csv - output file, each customer with RFM values + assigned cluster
- README.md
- screenshots/ - 4 PNGs referenced in the notebook (RFM distributions, elbow curve,
  cluster scatter plots, customers-per-segment bar chart)

## How to Run
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook Customer_Segmentation_Analysis.ipynb

Run all cells top to bottom. No external downloads or API keys needed.
