<h1 align="center">Swiggy Sales Dashboard</h1>

<p align="center">
  Sales analysis of a sample food delivery dataset, with an interactive dashboard layout and a written report.<br>
  <sub>Power BI Lab Practicals 10 - 12 · Business Analytics / Descriptive Analytics</sub>
</p>

<p align="center">
  <img alt="Tool" src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?logo=powerbi&logoColor=black">
  <img alt="Data" src="https://img.shields.io/badge/Data-350%20orders-2E9E94">
  <img alt="Charts" src="https://img.shields.io/badge/Charts-6-EB6834">
  <img alt="Type" src="https://img.shields.io/badge/Type-Academic%20project-1F3F6E">
</p>

> **Note:** The dataset is synthetic sample data created for learning. It is not real Swiggy data.

---

## Table of contents

1. [Overview](#overview)
2. [Dashboard preview](#dashboard-preview)
3. [Key insights](#key-insights)
4. [Dashboard features](#dashboard-features)
5. [Dataset](#dataset)
6. [DAX measures](#dax-measures)
7. [Repository structure](#repository-structure)
8. [Getting started](#getting-started)
9. [Practicals covered](#practicals-covered)
10. [Author](#author)

---

## Overview

This project analyses food delivery sales across 8 Indian cities from January to September 2026. It answers questions such as:

- Which cities, cuisines and restaurants bring in the most revenue?
- At what time of day do customers order the most?
- How do customers pay, and how often are orders cancelled?
- How does revenue change from month to month?

The work includes a cleaned dataset, a dashboard with filters, KPI cards and six charts, and a report with recommendations.

## Dashboard preview

| All cities | Filtered by city (Hyderabad) |
| --- | --- |
| ![Dashboard overview](images/dashboard_overview.png) | ![Dashboard filtered by Hyderabad](images/dashboard_hyderabad.png) |

## Key insights

| Metric | Result |
| --- | --- |
| Total revenue | ₹1,94,440 (delivered orders) |
| Orders | 350 placed, 330 delivered, 20 cancelled |
| Average order value | ₹589 |
| Average rating | 3.93 out of 5 |
| Average delivery time | 32.9 minutes |
| Cancellation rate | 5.7% |
| Top city | Hyderabad, 16.6% of revenue |
| Top cuisine | Biryani, 23.6% of revenue |
| Peak meal slot | Dinner, 36.2% of revenue |
| Most used payment mode | UPI, 49.7% of orders |
| Best and weakest month | February (₹27,680) and April (₹18,732) |

## Dashboard features

**Filters:** City, Cuisine, Meal slot, Payment mode, Month, and a Reset button.

**KPI cards:** Total revenue, Total orders, Average order value, Average rating, Average delivery time, Cancellation rate.

**Charts:**

1. Monthly revenue trend (line)
2. Payment mode share (doughnut)
3. Revenue by city (bar)
4. Revenue by cuisine (bar)
5. Revenue by meal slot (column)
6. Top 6 restaurants (column)

All cards and charts update when a filter changes.

## Dataset

`Swiggy_Sales_Data` has 350 rows and 18 columns, covering 8 cities, 8 cuisines and 24 restaurants.

| Column | Type | Description |
| --- | --- | --- |
| `Order_ID` | Text | Unique order number |
| `Order_Date` | Date | Date the order was placed |
| `Month` | Text | Month name (Jan to Sep) |
| `Month_No` | Whole number | Month number, used to sort months |
| `Day_of_Week` | Text | Day of the week |
| `City` | Text | City of delivery |
| `Restaurant` | Text | Restaurant name |
| `Cuisine` | Text | Cuisine category |
| `Meal_Slot` | Text | Breakfast, Lunch, Snacks, Dinner or Late Night |
| `Items_Ordered` | Whole number | Number of items in the order |
| `Order_Value` | Whole number | Item total before discount (₹) |
| `Discount` | Whole number | Discount applied (₹) |
| `Delivery_Fee` | Whole number | Delivery charge (₹) |
| `Final_Amount` | Whole number | Amount paid (₹); 0 for cancelled orders |
| `Payment_Mode` | Text | UPI, Credit/Debit Card, Cash on Delivery or Swiggy Money |
| `Delivery_Time_Min` | Whole number | Delivery time in minutes |
| `Customer_Rating` | Whole number | Rating from 1 to 5; blank for cancelled orders |
| `Order_Status` | Text | Delivered or Cancelled |

Revenue counts delivered orders only.

## DAX measures

These measures assume the table is named `Swiggy_Sales`.

```dax
Total Revenue =
CALCULATE ( SUM ( Swiggy_Sales[Final_Amount] ), Swiggy_Sales[Order_Status] = "Delivered" )

Total Orders =
COUNTROWS ( Swiggy_Sales )

Average Order Value =
DIVIDE (
    [Total Revenue],
    CALCULATE ( COUNTROWS ( Swiggy_Sales ), Swiggy_Sales[Order_Status] = "Delivered" )
)

Average Rating =
AVERAGE ( Swiggy_Sales[Customer_Rating] )

Average Delivery Time =
CALCULATE ( AVERAGE ( Swiggy_Sales[Delivery_Time_Min] ), Swiggy_Sales[Order_Status] = "Delivered" )

Cancellation Rate =
DIVIDE (
    CALCULATE ( COUNTROWS ( Swiggy_Sales ), Swiggy_Sales[Order_Status] = "Cancelled" ),
    COUNTROWS ( Swiggy_Sales )
)
```

## Repository structure

```text
swiggy-sales-dashboard-powerbi/
├── data/
│   ├── Swiggy_Sales_Data.csv
│   └── Swiggy_Sales_Data.xlsx
├── dashboard/
│   └── swiggy_dashboard.html
├── report/
│   ├── Swiggy_Sales_Report_Full.pdf
│   ├── Swiggy_Sales_Report_Full.docx
│   └── Swiggy_PowerBI_Cover_Page.docx
├── images/
│   ├── dashboard_overview.png
│   └── dashboard_hyderabad.png
└── README.md
```

## Getting started

**View the dashboard preview**

1. Download `dashboard/swiggy_dashboard.html`.
2. Open it in a web browser. An internet connection is needed to load the chart library.

**Use the data in Power BI**

1. Open Power BI Desktop and choose **Get data**, then **Text/CSV** (or **Excel workbook**).
2. Select the file in the `data` folder and click **Transform Data**.
3. Set `Order_Date` to Date, the amount columns to Fixed decimal number, and `Customer_Rating` to Whole number.
4. Click **Close & Apply**, then add the measures from the [DAX measures](#dax-measures) section.
5. Build the slicers, cards and charts listed under [Dashboard features](#dashboard-features).

## Practicals covered

| Practical | Topic |
| --- | --- |
| 10 | Import and transform data |
| 11 | Data model, DAX and visuals |
| 12 | Dashboard and report |

## Author

**Deepesh Srivastav**
University Roll No.: 1250258178
Submitted to: Miss Monica
Course: Business Analytics / Descriptive Analytics
