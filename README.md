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
![Screenshot fill](https://github.com/user-attachments/assets/b91de9c0-8295-4f79-ba15-b233be18fb4d)

#### DATA AGGREGATION
```Python
Customer_Count = Customer_Country.pivot_table(values = "Profit",index = "CustomerName", aggfunc = np.sum)

Customer_Count
```
![Screenshot aggregation](https://github.com/user-attachments/assets/6850ebaa-03fe-4a5b-ae34-79ddff6c74d2)

#### DATA SORTING
```Python
Customer_Count.sort_values("Profit", ascending = False)
```
![Screenshot aggregation](https://github.com/user-attachments/assets/4e4fd4b1-9f16-40c7-b246-421c259499cd)

#### RESULT
```Python
Customer_Count.sort_values("Profit", ascending = False).head(10)
```
![result](https://github.com/user-attachments/assets/6e8d3d61-da62-4b2d-aa2a-3702f3615fc1)

#### DATA VISUALIZATION
```Python
Customer_Count.sort_values("Profit", ascending = False).head(10).plot(kind = "bar", title = "Top 10 Most-Profitable Customers in the United State")

#label
plt.xlabel("CustomerName")
plt.ylabel("Profit") 

plt.show()
```
![Screenshot vissualization](https://github.com/user-attachments/assets/5c817a7a-421a-4f21-8f03-f54627652641)










