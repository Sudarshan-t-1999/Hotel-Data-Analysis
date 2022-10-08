# Hotel Data Analysis

![Screenshot (4)](https://user-images.githubusercontent.com/76962685/194711762-4cf6f8e6-d497-4290-8eb8-fc57e2fdcdd5.png)

* This Dashboard was made as part of [Codebasics Resume Project Challenge](https://codebasics.io/event/codebasics-resume-project-challenge) known as <b>Provide Insights to Revenue Team in Hospitality Domain</b>. The data for this project is available for download in the above site.

## Steps involved
* First aggregate all the data in the files **fact_bookings.csv, fact_aggregated_bookings.csv, dim_hotels.csv, dim_rooms.csv, fact_aggregated_bookings.csv, dim_date.csv** using the `VLOOKUP` formula after changing the format of Date from **dd-mmm-yy** to **dd-mm-yy**.
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
