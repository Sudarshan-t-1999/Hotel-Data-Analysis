# Hotel Data Analysis

![Screenshot (4)](https://user-images.githubusercontent.com/76962685/194711762-4cf6f8e6-d497-4290-8eb8-fc57e2fdcdd5.png)

* This Dashboard was made as part of [Codebasics Resume Project Challenge](https://codebasics.io/event/codebasics-resume-project-challenge) known as <b>Provide Insights to Revenue Team in Hospitality Domain</b>. The data for this project is available for download in the above site.

## Steps involved
* First aggregate all the data in the files **fact_bookings.csv, fact_aggregated_bookings.csv, dim_hotels.csv, dim_rooms.csv, fact_aggregated_bookings.csv, dim_date.csv** using the `VLOOKUP` formula after changing the format of Date from **dd-mmm-yy** to **dd-mm-yy** and changing the column names using `PROPER` formula.
* Add a Helper column in fact_aggregated_bookings.csv containing the values of Property_Id, Check_In_Date, Room_Category in order to help lookup the corresponding values of Successful_Bookings and Capacity.
* Select the data and press `Ctrl+T` to convert the data into a table and give a name for the table.
* Copy the table from **metrics_list.xlsx** and paste it in a new sheet.
* To calculate the Sum of Revenue Realized use the formula `=SUM(table_name[Revenue_Realized])`.
* To calculate the Total Number of Bookings use the formula `=ROWS(table_name[Booking_Id])`.
* To calculate the Average Rating use `=AVERAGE(table_name[Ratings_Given])`.
* To calculate the Total Capacity use `=SUM(table_name[Capacity])`.
* To calculate the Total Number of Successful Bookings use `=SUM(table_name[Successful_Bookings])`. 
* To calculate the Occupancy percentage use `=SUM(table_name[Successful_Bookings])/SUM(hotel[Capacity])`, then click on the percent sign in the **Home** tab in the **Number** block to convert the value into percentage.
* To calculate the Total Number of Cancelled Bookings use `=COUNTIF(hotel[Booking_Status], "Cancelled")`.
* To calculate the Cancellation Rate use `=Total_cancelled_bookings/ROWS(table_name[Booking_Id])`.

![Screenshot (8)](https://user-images.githubusercontent.com/76962685/194771646-c23fdb2c-8aab-4887-b6a2-f60ed6c1927d.png)
* To create the chart **Revenue per Week**, create a Pivot Table by clicking on Insert and under Tables click PivotTable.
* This opens the Create PivotTable dialog box, click on the **Select a table or range** radio button, enter the name of the table.
* Also select the **Add this data to the Data Model** checkbox fo every pivot table made.
* If the **PivotTable Fields** is not showing, click on Analyze then click Field List under Show.
* Drag the Week No from the list and drop it in the Rows section, then drag the Revenue_Generated and Revenue_Realized columns and drop them into values section.
* Then click on **PivotChart** under Analyze and select the type of chart, then click Ok. Then cut and paste the chart in a new sheet.
* Repeat the above steps and create the required charts.
* In order to plot Occupancy vs Week No, right click the table name and click Add Measure, then enter the Measure Name, enter the formula `=(SUM(table_name[No_Guests])/SUM(table_name[Capacity]))*100`, then click Ok.
* After pasting the charts in the new sheet, insert a new pivot table in the sheet.
* Drag the **Property_Id** and **Property Name** and drop them in the Rows section and drop the columns **Revenue Generated, Revenue Realized, Occupancy, Ratings_Given, No_Guests** in the Values section.
* To calculate the Average of the Ratings Given, click on the drop-down arrow next to the Ratings Given, then click on **Value Field Settings**, select Average under Summarize Values By, then click Ok.
* In order to represent the values with bars, drag and drop all the columns again into the Values section next to each other, select each of the values in the table and click on **Conditional Formatting**, then select whichever colour you want under Data Bars.
* In order to hide the values in the bars, select the values, click on **Format**, then on **Format Cells**, in Category click **Custom**, under Type replace General with ;;;, then click Ok.
* To put filters, right click on the columns that you want to filter on and click on **Add as Slicer**.
* In order to make the charts change according to the filters applied by the slicers, right click on the Slicers and click **Report Connections** and select the pivot tables with charts that need to change.
* In order to show the main parameters, click on **Insert**, under **Illustrations**, click on **Shapes** and select the shape you want.
* To fill the shape with the values, enter the formula for values in Formula bar after selecting the shape.
