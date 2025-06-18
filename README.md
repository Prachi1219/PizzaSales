# Pizza Sales Data Analysis

### Dashboard screenshot: ![Dashboard](https://github.com/user-attachments/assets/e4fbd8a4-1e0a-4df0-b00d-42fb0a917ee7)


## Problem Statement

There is a Pizza manufacturing outlet, producing variety of Pizzas with different categories. We have different KPI's(Key Performance Indicators) to get the sales and revenue of the Pizza Sales. 

The requirement states that we need to calculate the total revenue, total pizzas sold, total orders placed, per order how many pizzas are sold, average order value and the visualize the daily and hourly trends for total orders and the average pizza sold for each category.

Also calculate the preference of customers, the most disliked pizza, sales of different pizza sizes.

### Steps Followed :

- Step 1: The dataset is a CSV file with all the details of Pizza sales.
- Step 2: Open SQL Server Management Studio, create a DB and import the CSV Flat file into SQL Server Management Studio.
- Step 3: Created the SQL queries in DB for all the KPI's and the Requirements to validate from the Dashboard.(Please see attached word doc(SQL_Queries).
- Step 4: Open the New Excel, linked the SSMS Database with Excel using Server Name and selected the table name and uploaded the data from Database to Excel.
- Step 5: Performed Data Cleansing by updating some values to valid values, extracted some date values from the excel data by using excel formulas.
- Step 6: Created Pivot table from Insert tab and selecting Pivot table, for calculating the total revenue by performing sum on Total Price.
- Step 7: Calculated Average order value by dividing total revenue / total number of orders column
- Step 8: Calculated the Total quantities of Pizza sold and populated in Pivot.
- Step 9: Calculated the total orders of Pizza and populated in Pivot.
- Step 10: Calculated the average Pizza sold per order and populated in Pivot.
- Step 11: Added the KPI count to Dashboard in excel and linked the Dashboard to the Pivot table created using GETPIVOT function so that if any updates are done in Pivot table, it get automatically reflected in Dashboard.
- Step 12: Created Pivot Table on order day and sum of orders column to get the daily trends and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.
- Step 13: Created Pivot Table on order time and sum of orders column to get the hourly trends and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.

    Daily and hourly trends(Step 12 and 13)
    ![DailyAndHourlyTrends](https://github.com/user-attachments/assets/89db46f0-b137-4a61-a795-6468c8b79bc9).
  
  
- Step 14: Created Pivot Table on Pizza Category and Sum of total price column to get the percentage of sales by Pizza category and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.
- Step 15: Created Pivot Table on Pizza Size and Sum of total price column to get the percentage of sales by Pizza Size and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.
- Step 16: Created Pivot Table on Pizza Category and Sum of total quantity column to get the sum of pizza sold by Pizza category and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.

    Percentage of Pizza sold by pizza category, pizza size
    ![PercentageCharts](https://github.com/user-attachments/assets/6e31320e-f80f-42fe-b039-adf1f0b04538)

- Step 17: Created Pivot Table on Pizza Name and Sum of total quantity column to get the Top 5 Pizza sellers and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.
- Step 18: Created Pivot Table on Pizza Name and Sum of total quantity column to get the Bottom 5 Pizza sellers and created chart by selecting the chart format under Home tab and then formatted the chart. Then validated the count with results obtained from sql queries created and populated the chart in dashboard.
- Step 19: Added the slicer for order date, to analyze the Pizza Sales on the Different dates.


### Excel Formulas used for Data Cleansing and Visualization
(1) To get the daily trend, extract the order day from the given order_date column.

                = Text(select column cell),"dddd"
(2) As the order_id values are duplicates, so we will use the formula to get the count.

                =COUNTIF(select the column(order_id range, first record of the column)
                            Then divide the above formula by 1 :
                = 1/=COUNTIF(select the column(order_id range, first record of the column)
After applying the above formula we get the values in decimals and if we sum up the decimal value of particular order_id, then it will sum up to 1.
so this is how the duplicates are removed.
