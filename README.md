# Sales_Analysis_for_an_Automobile_Company-USA
A Data Science Project that Analysed  the sales performance of an Automobile company Based in the United States. The company’s sales transaction data generated over the past years was used for this  analysis.

##  PROBLEM STATEMENT
Who are their Top 10 Most-Profitable Customers  in the United State ?

## DATA PRE-PROCESSING
#### DATA LOADING

## Import all the necessary python packages 
```Python
import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt

```
#reading the sales data into panda data frame
```Python
bikes_df = pd.read_csv("C:/Users/uthma/OneDrive/Desktop/Data Set/bikes.csv")

bikes_df.head()
```
![Screenshot PANDA1](https://github.com/user-attachments/assets/cf677480-dba6-45a7-95c8-c215e2fc4c89)

## Data Modification
```Python
#Adding the following 3 columns to your pansdas Dataframe:  bikes_df
# TotalCostPrice : To be obtained by (OrderQuantity x CostPrice_usd)


bikes_df["TotalCostPrice"] = bikes_df["OrderQuantity"] * bikes_df["CostPrice_usd"] 



# SalesRevenue : To be obtained by (OrderQuantity x SellingPrice_usd)


bikes_df["SalesRevenue"] = bikes_df["OrderQuantity"] * bikes_df["SellingPrice_usd"] 



# Profit : To be obtained by (SalesRevenue - TotalCostPrice)



bikes_df["Profit"] = bikes_df["SalesRevenue"] - bikes_df["TotalCostPrice"]


bikes_df.head()

```
![Screenshot modify](https://github.com/user-attachments/assets/3f3781f2-b44b-4b32-b71f-7299fb7429fa)

## DATA ANALYSIS
#### DATA FILTERING

```Python
Customer_C = bikes_df["CustomerCountry"] == "United States"
Customer_Country = bikes_df[(Customer_C)]

Customer_Country
```






