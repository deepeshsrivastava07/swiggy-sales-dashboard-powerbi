Swiggy Sales Dashboard (Power BI Lab Practicals 10 - 12)
A sales analysis project on a sample Swiggy food delivery dataset. It includes a dashboard layout with filters, KPI cards and six charts, plus a written report with a cover page.
The data is synthetic sample data created for learning. It is not real Swiggy data.
What is in this repository
File	Description
Swiggy_Sales_Data.xlsx	Dataset, 350 orders and 18 columns (Excel)
Swiggy_Sales_Data.csv	Same dataset in CSV, ready to import into Power BI
swiggy_dashboard.html	Interactive dashboard layout preview (open in a browser)
Swiggy_Sales_Report_Full.pdf	Final report with cover page, analysis and dashboard pages
Swiggy_Sales_Report_Full.docx	Editable Word version of the report
Swiggy_PowerBI_Cover_Page.docx	Cover page only
Dataset
350 orders from January to September 2026 across 8 cities, 8 cuisines and 24 restaurants.
Columns: Order_ID, Order_Date, Month, Month_No, Day_of_Week, City, Restaurant, Cuisine, Meal_Slot, Items_Ordered, Order_Value, Discount, Delivery_Fee, Final_Amount, Payment_Mode, Delivery_Time_Min, Customer_Rating, Order_Status.
Revenue counts delivered orders only (Final_Amount). Cancelled orders have Final_Amount set to 0 and no rating.
Dashboard
Filters: City, Cuisine, Meal slot, Payment mode, Month
KPI cards: Total revenue, Total orders, Average order value, Average rating, Average delivery time, Cancellation rate
Charts: Monthly revenue trend, Payment mode share, Revenue by city, Revenue by cuisine, Revenue by meal slot, Top 6 restaurants
To open the preview, download swiggy_dashboard.html and open it in a browser (it loads Chart.js from a CDN, so an internet connection is needed).
Key findings
Revenue of ₹1,94,440 from 330 delivered orders, with an average order value of ₹589
Biryani is the top cuisine (23.6% of revenue) and Hyderabad the top city (16.6%)
Dinner is the peak slot (36.2% of revenue) and UPI is the most used payment mode (49.7% of orders)
February was the strongest month (₹27,680) and April the weakest (₹18,732)
Cancellation rate is 5.7%, and the average delivery time is about 33 minutes
Practicals covered
Practical	Topic
10	Import and transform data
11	Data model, DAX and visuals
12	Dashboard and report
How to use the data in Power BI
Open Power BI Desktop and choose Get data > Text/CSV (or Excel workbook).
Select Swiggy_Sales_Data.csv and click Transform Data to check the column types.
Set Order_Date as Date, the amount columns as Fixed decimal number, and Customer_Rating as Whole number.
Build the cards, slicers and charts listed above on a report page.
Author
Deepesh Srivastav University Roll No.: 1250258178 Business Analytics / Descriptive Analytics Course, submitted to Miss Monica

Claude finished the response

