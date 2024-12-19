# HPN-power-bi-project

# HPN(heavy power nutrition) Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/e462eff0-bad5-49c5-a31c-f2b88e44eb37/ReportSection877afa6de346169275e0?experience=power-bi

## Problem Statement

This dashboard provides valuable insights to the company, enabling a better understanding of customer satisfaction with the supplement. It helps assess user feedback, highlighting areas for improvement based on various ratings. By identifying these areas, the company can enhance product quality and customer experience effectively.

Additionally, the dashboard provides data on average delivery times and other key metrics. By addressing delays or issues in the supply chain, the company can ensure timely delivery and improved service efficiency.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : For calculating average delay time, null values were not taken into account as only less than 1% values are null in this column. 
- Step 6 : In the report view, theme was designed with the help of microsoft powerpoint.
- Step 7 : Since the data contains various ratings, thus in order to represent ratings, a new visual was added using the three ellipses in the visualizations pane in report view. 
- Step 8 : Visual filters (Slicers) were added for four fields named "Product category".

- Step 10 : A bar chart was also added to the report design area representing the number of satisfied & neutral/unsatisfied customers. While creating this visual, field named "Gender" was also added to the Legends bucket, thus number of customers are also seggregated according the gender. 

In our dataset, Some parameters were assigned value 0, representing those parameters are not applicable for some customers.

All these values have been ignored while calculating average rating for each of the parameters mentioned above.

 
- Step 14 : Calender table was created in which,

for creating new column following DAX expression was written;
       
        Calender = 
        VAR vmaxyear= YEAR(MAX(FactTable_Transaction[OrderDate]))
        VAR vminyear=YEAR(MIN(FactTable_Transaction[OrderDate]))

        Return
            ADDCOLUMNS(
                FILTER(
        CALENDARAUTO(),
         YEAR([Date])>=vminyear &&
         YEAR([Date]) <= vmaxyear
          ),
          "year", YEAR([Date]),
          "Day", DAY([Date]),
          "Month num", MONTH([Date]),
          "Month", FORMAT([Date],"mmm"),
          "Week num", WEEKDAY([Date]),
          "weekday", FORMAT([Date],"ddd"),
          "Qtr",FORMAT([Date],"\QQ")

        )
        
Snap of new Calender table ,

![Screenshot 2024-12-19 230323](https://github.com/user-attachments/assets/6e97cfb4-f390-45e8-bced-9372e1af6bb2)

        

# Snapshot of Dashboard 

![Screenshot 2024-12-19 230712](https://github.com/user-attachments/assets/b7d22691-e801-4e3a-b5cf-b2837bda6b39)

![Screenshot 2024-12-19 230731](https://github.com/user-attachments/assets/e4170e6c-58e8-4770-b1c6-acbc4cc7649c)
 
![Screenshot 2024-12-19 230747](https://github.com/user-attachments/assets/25d481c8-0453-4406-a0a1-88b1a2192fe7)



A  report was created on Power BI Desktop & it was then published to Power BI Service.


