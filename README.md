# Sales_Analysis_for_an_Automobile_Company_USA
 A Data Science Project that Analysed  the sales performance of an Automobile company Based in the United States. The company’s sales transaction data generated over the past years was used for this  analysis.
 ## PROBLEM STATEMENT: 
 What are the Top Most-Profitable 5 States for the Bike Product Category in the United States ?
## DATA PRE_PROCESSING
#### DATA LOADING
# importing all the neccessary python packages


```Python
# run this cell to impport all the 3 packages at once 

# solution 

import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt

print("the packages have been successfully imported")


```
```
# reading the sales data into  pandas dataframe

bikes_df = pd.read_csv("C:/Users/HP/OneDrive/Documents/_DATA SCIENCE BOOK CAMP TRANINIG/DATA SET/bikes.csv")
bikes_df.head()
#### DATA MODIFICATION

```
# (1). Adding the following 3 extra columns to your pansdas Dataframe:  bikes_df


# TotalCostPrice : To be obtained by (OrderQuantity x CostPrice_usd)


bikes_df["TotalCostPrice"] = bikes_df["OrderQuantity"] * bikes_df["CostPrice_usd"] 





# SalesRevenue : To be obtained by (OrderQuantity x SellingPrice_usd)


bikes_df["SalesRevenue"] = bikes_df["OrderQuantity"] * bikes_df["SellingPrice_usd"] 



# Profit : To be obtained by (SalesRevenue - TotalCostPrice)



bikes_df["Profit"] = bikes_df["SalesRevenue"] - bikes_df["TotalCostPrice"]


bikes_df.head()
## DATA ANALYSIS
#### DATA FILTERING


```

```


 
