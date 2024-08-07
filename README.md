# Sales-Insights-Dashboard-Power-BI

## Dashboard Link: Not published

### Report pdf: https://github.com/riteshhbhandari/Sales-Insights-Power-BI/blob/main/Sales-Insights-Power-BI-Project1.pdf

**Problem Statement**

This dashboard helps the computer hardware company understand their sales performance better. It tracks key performance indicators (KPIs) such as revenue, sales quantity, and regional breakdowns. By analyzing these metrics, the company can identify areas for improvement and strategize to enhance overall sales performance. The dashboard also highlights trends in sales data, enabling the company to make informed business decisions and optimize their operations.

Since certain regions may underperform, identifying and addressing these discrepancies can help in targeting efforts to boost sales. Additionally, tracking average sales quantity and revenue over time will help in understanding market demand and customer preferences.

---

**Steps Followed**

**Step 1**: Load data into Power BI Desktop from a CSV file containing sales data.

<img width="939" alt="01Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/ba7fbaec-8db5-4101-8745-b82f88c7dbd8">

**Step 2**: Open Power Query Editor and in the View tab under the Data Preview section, check "Column distribution," "Column quality," and "Column profile" options.

**Step 3**: By default, profiling is opened for 1000 rows. Select "Column profiling based on entire dataset" for comprehensive analysis.

**Step 4**: Verify that there are no errors or empty values in the columns except for minor discrepancies in the "Sales Quantity" column.
<img width="594" alt="02Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/ad5497ff-03a3-4cc6-979d-759b17cbde68">
<img width="906" alt="04Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/25ad67ed-c2d1-468a-8bc0-d92898c054c6">

**Step 5**: For calculating average sales quantity, null values are not considered as they account for less than 1% of the total dataset.
<img width="786" alt="08Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/e7d6b6ec-cec8-488b-a19d-a4a27db33b96">

**Step 6**: In the Report View, under the View tab, select a theme to enhance visual appeal.

**Step 7**: Since the data includes various sales metrics, add new visuals using the three ellipses in the Visualizations pane in Report View.

**Step 8**: Add Visual filters (Slicers) for fields such as "Region," "Product Category," "Sales Representative," and "Customer Segment."
<img width="889" alt="07Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/9a62a2a4-6802-42c8-8a00-3cf69ad3e992">
<img width="889" alt="06Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/13faaf99-7443-4c4e-9cb7-aabb4d86f6f8">


**Step 9**: Add two card visuals to the canvas, one representing total revenue and the other representing total sales quantity. Use visual-level filters to exclude null values from the calculations.

**Step 10**: Add a bar chart to the report design area to represent the sales quantity by region. Include "Product Category" in the Legends bucket to segregate sales data accordingly.

**Step 11**: Use a line chart to show revenue trends over time.

**Step 12**: In the Report View, under the Insert tab, add two text boxes to the canvas, one displaying the company's name and the other showcasing the company's tagline.

**Step 13**: In the Report View, under the Insert tab, use shapes from the Elements group to insert a rectangle, and use the Image option to add the company's logo to the report design area.

**Step 14**: Create a calculated column to group sales data into different product categories. Use the following DAX expression:

```DAX
Product Category = 
IF(
    SalesData[ProductID] <= 1000, "Category 1",
    IF(SalesData[ProductID] <= 2000, "Category 2",
    IF(SalesData[ProductID] <= 3000, "Category 3",
    "Other Categories")))
```

**Step 15**: Create a new measure to find the total count of sales transactions using the following DAX expression:

```DAX
Count of Sales Transactions = COUNT(SalesData[TransactionID])
```

A card visual is used to represent the count of sales transactions.

**Step 16**: Create a new measure to calculate the percentage of sales by region using the following DAX expression:

```DAX
% Sales by Region = (DIVIDE(SalesData[Count of Sales Transactions], TOTAL(SalesData[Count of Sales Transactions])) * 100)
```

A card visual is used to represent this percentage.

**Step 17**: Create a new measure to calculate total revenue using the following DAX expression:

```DAX
Total Revenue = SUM(SalesData[Revenue])
```

A card visual is used to represent total revenue.

**Step 18**: Publish the report to Power BI Service.

---

**Insights**

A single-page report was created on Power BI Desktop and then published to Power BI Service. The following inferences can be drawn from the dashboard:

**[1] Total Sales Performance**

- **Total Revenue**: 984.87M 
- **Total Sales qty**: 2M
<img width="594" alt="02Sales-Insights-Power-BI-Project" src="https://github.com/user-attachments/assets/38db329e-67a8-415e-88cf-e401e1fd632d">

**[2] Sales Trends**

- **Yearly Revenue Trends**: Displayed in the line chart to observe seasonal variations and peak sales periods.

**[3] Store Category Performance : Top 5 Stores** 
- **Store Category Trends**: Displayed in the line chart to observe seasonal variations and peak sales category.


These insights will help the company in making data-driven decisions to improve sales performance, optimize marketing strategies, and enhance customer satisfaction.
