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
=IF(DATEVALUE(TEXT([@[DATE RECEIVED]],”dd-mm-yyyy”))),”valid date”, ”not a date”)



