# Sales-data-analysis-dashboard# Sales Data Analysis Dashboard

An internship mini project that cleans and analyzes Amazon India e-commerce sales data in Excel and presents the results in a dashboard with business insights.

**Workflow:** Data → Cleaning → Analysis → Visualization → Dashboard → Business Insights

## Project Objective

Analyze a sales dataset and produce meaningful insights using data cleaning, analysis, and visualization techniques. The dashboard answers these questions:

- How much did we sell, and in how many orders? (Total Sales, Total Orders)
- How did sales change month by month and day by day?
- Which products and categories sell the most?
- Which states and cities perform best?

## Dataset

- **Name:** Amazon Sale Report (Kaggle)
- **Size:** 128,975 rows × 24 columns
- **Period:** 31 March 2022 to 29 June 2022
- **Currency:** INR
- **Key columns:** Order ID, Date, Status, Fulfilment, Category, SKU, Size, Qty, Amount, ship-city, ship-state, B2B

## Tools Used

- Microsoft Excel (data cleaning, formulas, analysis, charts, dashboard)
- Python and pandas (optional cross-check of the totals)

## Data Cleaning Summary

| Issue | Count | Action |
|---|---|---|
| Duplicate records | 6 | Removed |
| Missing Amount | 7,792 (almost all cancelled orders) | Rows removed |
| Inconsistent state names | 69 spellings | Standardized to 37 values |
| Missing state or city | 31 | Filled with "Unknown" |
| Date stored as MM-DD-YY text | All rows | Converted to a proper date |
| Unused or empty columns | 10 | Dropped |
| Cancelled, pending, returned, damaged orders | n/a | Flagged with a Valid Sale column and excluded from sales |

**Final cleaned dataset:** 121,177 rows.

**Sales rule:** Total Sales counts only valid sales, meaning orders that are not cancelled, pending, returned, rejected, lost or damaged, and have an Amount above 0. Total Orders is the number of distinct Order IDs with at least one valid line.

## Key Results

| KPI | Value |
|---|---|
| Total Sales | ₹69,660,658 |
| Total Orders | 97,965 |
| Average Order Value | ₹711 |

## Business Insights

1. **Two categories drive most of the revenue.** Set (49.9%) and Kurta (27.2%) bring 77% of sales.
2. **Sales are concentrated in a few states.** The top 5 states make 56.4% of sales, led by Maharashtra (17.2%) and Karnataka (13.5%). Bengaluru is the top city.
3. **Sales fell from April to June because order volume dropped.** Sales went from ₹25.7M to ₹20.4M, orders fell 24.8%, and average order value rose from ₹686 to ₹727.
4. **A few styles and sizes are the best sellers.** 6 of the top 10 SKUs are sizes of style JNE3797, and sizes M, L and XL lead.
5. **Cancellations are high.** 14.2% of order lines in the original data were cancelled, at similar rates across categories, which points to stock or shipping rather than a product problem.
6. **Amazon-fulfilled orders carry most of the revenue.** They bring 72.2% of sales. B2B orders are only 0.8%.
7. **Weekends are strongest.** Sunday has the highest sales and Thursday the lowest, a gap of 15.6%.

Each insight has a full recommendation in the Insights sheet of the workbook.

## Dashboard

The dashboard contains KPI cards (Total Sales, Total Orders, Average Order Value) and charts for:

- Monthly Sales (April to June)
- Sales by Category
- Daily Sales Trend
- Top 10 Products (SKU)
- Top 10 States

## Repository Structure

```
sales-data-analysis-dashboard/
│
├── data/
│   ├── original/          Amazon Sale Report.csv
│   └── cleaned/           Amazon_Sale_Report_Cleaned.csv
│
├── analysis/
│   └── Sales_Analysis_Dashboard.xlsx    (Dashboard, Insights, Analysis, Cleaning_Log, Cleaned_Data)
│
├── report/                Project report
├── presentation/          Final presentation
└── README.md
```

## How to Use

1. Download or clone this repository.
2. Open `analysis/Sales_Analysis_Dashboard.xlsx` in Excel.
3. Start with the **Dashboard** sheet, then read **Insights**.
4. The **Analysis** sheet shows every calculation as a live formula on the **Cleaned_Data** sheet.
5. The **Cleaning_Log** sheet lists every data issue and how it was handled.

## Limitations

- The data covers only about three months, and March has a single day, so monthly comparisons use April to June.
- The first and last days of the data are partial, which makes the daily trend dip at both ends.
- Results depend on the sales rule above. Including cancelled orders would give higher totals.

## Author

**Iygine Albert**
LinkedIn: https://www.linkedin.com/in/iyginealbert/
