# Sales_Data_1000_Rows_Data_Cleaning-
1000 Rows Sales data cleaned
# Power BI – Module End Evaluation

## Project Overview

This project was completed as part of the Power BI Module End Evaluation. The objective was to clean and transform a sales dataset, create visualizations, and perform DAX calculations using Microsoft Power BI.

**Dataset:** `SalesData_1000Rows_WithIssues_copy.csv`

**Tools Used:**
- Microsoft Power BI Desktop
- Power Query Editor
- DAX (Data Analysis Expressions)

---

## Q1: Data Cleaning and Loading

Imported the sales dataset into Power BI using Power Query Editor.

### Data Cleaning Steps

1. Removed duplicate rows.
2. Replaced missing values in `CustomerName` with `Unknown`.
3. Removed rows with missing values in `Region`.
4. Removed rows with missing values in `Product`.
5. Standardized `OrderDate` to Date format.
6. Changed numerical columns from Text to appropriate numerical data types.
7. Identified missing values in numerical columns and investigated them.
8. Checked column quality to identify errors and empty values.

After cleaning, the transformed dataset was loaded into the Power BI data model.

---

## Q2: Visualizations and Insights

Created three visualizations to analyze order distribution, popular products, and profit trends.

### 1. Order Distribution by Region – Pie Chart

**Fields Used:**
- Legend: Region
- Values: Count of OrderID

**Results:**

| Region | Orders | Percentage |
|---|---:|---:|
| East | 259 | 27.26% |
| South | 246 | 25.89% |
| West | 223 | 23.47% |
| North | 222 | 23.37% |

**Insight:** East recorded the highest number of orders, while North recorded the lowest. The distribution was relatively balanced across all four regions.

### 2. Top 5 Trending Products – Column Chart

**Fields Used:**
- X-axis: Product
- Y-axis: Count of OrderID
- Filter: Top 5 products by Count of OrderID

**Results:**

| Rank | Product | Orders |
|---:|---|---:|
| 1 | Monitor | 129 |
| 2 | Laptop | 127 |
| 3 | Bookshelf | 126 |
| 4 | Headphones | 120 |
| 5 | Cabinet | 119 |

**Insight:** Monitor was the most frequently ordered product, with 129 orders.

### 3. Profit Trend Over Time – Line Chart

**Fields Used:**
- X-axis: OrderDate (Year hierarchy)
- Y-axis: Sum of Profit

**Insight:** The line chart displays annual profit fluctuations over time and helps identify changes in profit across different years.

---

## Q3: DAX Calculations

Created the following DAX elements as required by the assignment.

### 1. Calculated Table – EastRegionOrders

**Purpose:** To create a separate table containing only orders from the East region.

```dax
EastRegionOrders =
FILTER(
    SalesData_1000Rows_WithIssues_copy,
    SalesData_1000Rows_WithIssues_copy[Region] = "East"
)
```

### 2. Calculated Column – ProfitCostDifference

**Purpose:** To calculate the difference between Profit and Cost for each order.

```dax
ProfitCostDifference =
SalesData_1000Rows_WithIssues_copy[Profit]
-
SalesData_1000Rows_WithIssues_copy[Cost]
```

### 3. Measure – TotalProfit

**Purpose:** To calculate the total profit earned across the dataset.

```dax
TotalProfit =
SUM(SalesData_1000Rows_WithIssues_copy[Profit])
```

The measure was displayed using a Card visual, showing approximately 5 million in total profit.

---

## Key Learnings

- Importing datasets into Power BI.
- Cleaning and transforming data using Power Query.
- Handling missing values and duplicate records.
- Standardizing date formats and numerical data types.
- Creating Pie, Column, and Line charts.
- Applying Top N filters.
- Writing DAX formulas.
- Creating calculated tables, calculated columns, and measures.
- Analyzing data through visualizations.

---

## Conclusion

This project provided practical experience in data cleaning, transformation, visualization, and DAX calculations using Power BI.

It helped strengthen my understanding of how raw sales data can be transformed into meaningful business insights.

**Project Status:** Completed

**Tool:** Microsoft Power BI Desktop
