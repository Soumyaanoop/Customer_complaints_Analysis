# Customer_complaints_Analysis

## Project Overview
This data analysis project showcases a dashboard of credit card complaints in different companies. In this project give insights about which company got highest number of complaints, category of issues, how long it takes to solve the complaint. This dashboard lets the companies know the issues and they can improve their services by identifying these issues. 

## Data Source 
The primary data set used for this project is ‘Credit_card_complaints.xlsx’ file.

## Tools
Ms Excel – used for data cleaning, exploration and analysis.  
Tableau – creating reports 

## Dashboard Link 


## Steps followed 

### Data cleaning 

First check the dataset and understand what it contains . This dataset has attributes such as Company names, company response to the customer, complaints category, complaints Id, Complaints receiving dates and its response dates , State, Complaints submitted Via.     
Then check missing values or values in wrong format. The column named avg no of days has wrong value -1 in some rows. So I have to replace -1 with 0.  
Then I found that there are some blank cells, replace it with N/A.
Also I removed some unwanted columns like Dimension, Customer consent approved, Consumer complaint narrative, Sub product, Sub issue ,Tags etc. Then check the Date column for date format is correct or any wrong values are there. I create a new column and use the formula
=IF(DATEVALUE(TEXT([@[DATE RECEIVED]],”dd-mm-yyyy”))),”valid date”, ”not a date”)   Using this formula I understood all date are in correct format and no unwanted values in that column.
Finally our dataset have cleaned successfully. 

### Exploratory Data Analysis 

Exploring this data set for answering key questions. 

-Which company got highest number of complaints?

-Count the number of complaints received in the last 12 months?

-What is the percentage of Timely respond complaints?

-what is the weekly basis trend ?

-what are the top 5 issues about credit card? 

### Creating Dashboard 

 we import and load data from Excel into Tableau. After loading data, we check whether the data is properly loaded or not in the data pane view.

First count number of complaints received. 


Then find no of complaints received in last 12 months. For that I created a calculated field named ‘Max Date Received’ because I want to show last date of particular date value. After that I create a parameter named ‘Max Date Received’. Again create another calculated field named ‘ Rolling 12 months’. Date Diff and Date Trunc functions are used in the calculation field ‘Rolling 12 months’. 

DATEDIFF('month',DATETRUNC('month',[Date received]),DATETRUNC('month',[Parameters].[Max Date Received]))<12

SUM(IF [Rolling 12 month filter]=True Then [Number of Records] END)



Next created Timely responded complaints and its percentage. For this I created a calculation field named ‘ Timely Response’. 

                   SUM(If [Timely response?]='Yes' THEN [Number of Records] END)

After this, calculate the percentage of how many complaints has been timely responded.



Then I found the no of complaints in progress and its percentage.


Then create a graph showing complaints received on weekly basis and monthly basis

![Screenshot 2024-08-17 at 16 48 19](https://github.com/user-attachments/assets/fdb4affe-8243-4589-9a7b-3665a969faf9)


Next I created a sheet for density map for showing the state wise distribution of complaints. Also I created another sheet for Field map. Then swap these two sheets.

![Density map](https://github.com/user-attachments/assets/2838153c-995e-4dab-b5fe-e5f144a188bb)

![Field map](https://github.com/user-attachments/assets/c8ab4b23-87cd-4c41-a775-bc40052a2ce9)


I find top 10 issues reported by customer. For that I use bar chart and apply filter on Issues

![Screenshot 2024-08-17 at 16 50 11](https://github.com/user-attachments/assets/986b63df-ef49-4a33-b522-316dce1fb86e)


Let’s find out company’s response to the complaints. Take number of records over this field. So we can see total number of records in each category of issues. Then choose percentage from quick table calculation. So in this sheet shows number of records in each category of issues, also shows its percentage. 

![Screenshot 2024-08-17 at 16 50 41](https://github.com/user-attachments/assets/1b2fbf05-8c1b-4239-904c-c6988cda8710)


Next I want to show daily complaints . For that I created a calendar. First apply filter on Date received. Then do right click You can see the options from that you can choose date part or date value I am going to use. I select month year.
Screen short


![Screenshot 2024-08-17 at 16 47 40](https://github.com/user-attachments/assets/0942461a-b0ec-437e-8da3-4f47115ef109)


Let;s find which the companies have got highest number of complaints


![Screenshot 2024-08-17 at 16 47 11](https://github.com/user-attachments/assets/4a3a727a-42fc-4895-a85b-2a1247644151)





