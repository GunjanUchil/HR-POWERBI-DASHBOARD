# HR-POWERBI-DASHBOARD
A simple Power BI dashboard to analyze the employee details of an organization.
# Introduction
* This project is aimed at developing a Power BI dashboard for generating insights about employees from an organisation.
* The data set can be accessed from this link: [Employee Data](https://view.officeapps.live.com/op/view.aspx?src=https%3A%2F%2Fraw.githubusercontent.com%2FGunjanUchil%2FHR-POWERBI-DASHBOARD%2Fmain%2Fhr-data.xlsx&wdOrigin=BROWSELINK)
# Questions
The analysis that we are going to perform shall answer the following questions:
1. Total number of employees in the organisation.
2. Average salary earned by the employees.
3. Distribution of employees across the various departments.
4. Top and bottom 3 earners.
5. Gender distribution in the organisation.
6. Age distribution in the organisation.
7. Year on year cumulative headcount in the organisation.
8. Average leave balance accumalated by the employees in each department.
9. Count of employees having leave balance of over 20 days.
# DAX formulas used in measures
1. Count of employees in the organisation:
   * `HeadCount = COUNTROWS(Staff)`
2. Average leave balance:
   * `Avg. leave balance = AVERAGE(Staff[Leave Balance])`
3. Average salary:
   * `Avg. Salary = AVERAGE(Staff[Salary])`
4. Cumulative headcount:
   * `Cumulative headcount = 
       var currentDate = LASTDATE(Staff[Date of Join])
RETURN
       CALCULATE([HeadCount], ALL(Staff[Date of Join]), Staff[Date of Join]<=currentDate)`
5. Leave balance over 20 days
   * `LBL over 20 days = CALCULATE([HeadCount], Staff[Leave Balance]>20)`
  
# Dashboard
![Dashboard image](https://github.com/GunjanUchil/HR-POWERBI-DASHBOARD/blob/main/HR%20dashboard.png)

