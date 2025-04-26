
 ## PROBLEM STATEMENT: 
 What are the Top Most-Profitable 5 States for the Bike Product Category in the United States ?

## DATA PRE_PROCESSING
#### DATA LOADING
importing all the neccessary python packages


```Python
# run this cell to impport all the 3 packages at once 

# solution 

import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt

print("the packages have been successfully imported")


# reading the sales data into  pandas dataframe
```Python
bikes_df = pd.read_csv("C:/Users/HP/OneDrive/Documents/_DATA SCIENCE BOOK CAMP TRANINIG/DATA SET/bikes.csv")
bikes_df.head()
```
![READ CSV FILE SCREENSHOT](https://github.com/user-attachments/assets/c53f0b69-3744-48e1-91bf-dd4edc84a9c3)


#### DATA MODIFICATION

```Python
# (1). Adding the following 3 extra columns to your pansdas Dataframe:  bikes_df


 TotalCostPrice : To be obtained by (OrderQuantity x CostPrice_usd)


bikes_df["TotalCostPrice"] = bikes_df["OrderQuantity"] * bikes_df["CostPrice_usd"] 


 SalesRevenue : To be obtained by (OrderQuantity x SellingPrice_usd)


bikes_df["SalesRevenue"] = bikes_df["OrderQuantity"] * bikes_df["SellingPrice_usd"] 



 Profit : To be obtained by (SalesRevenue - TotalCostPrice)



bikes_df["Profit"] = bikes_df["SalesRevenue"] - bikes_df["TotalCostPrice"]


bikes_df.head()
```
![DATA MODIFICATION SCREENSHOT](https://github.com/user-attachments/assets/a67f135f-62ce-45e2-b0f8-5d550f5986a4)



## DATA ANALYSIS
#### DATA FILTERING
 filitering out only the data relevant to solving the problem statement

```Python

is_us = bikes_df["CustomerCountry"] == "United States"
is_bike = bikes_df["ProductCategory"] == "Bikes"
bike_in_us = bikes_df[(is_us) & (is_bike)]
bike_in_us.head()
```


![DATA FILTERING SCREENSHOT](https://github.com/user-attachments/assets/fcfae0ce-f9a2-47d0-9e6e-80317a1422f6)

total_profit_by_states = bike_in_us.pivot_table(values = "Profit", index = "CustomerState", aggfunc = np.sum)
total_profit_by_states   




#### DATA AGREGATION

```Python
total_profit_by_states = bike_in_us.pivot_table(values = "Profit", index = "CustomerState", aggfunc = np.sum)
total_profit_by_states    
```

![DATA AGGREGATION SCREENSHOT](https://github.com/user-attachments/assets/732ff718-92ca-40b0-b202-062e23339939)


#### DATA SORTING/RANKING
Sorting the aggregated data in order to rank the states according to the top most profitable states

```Python
total_profit_by_states.sort_values("Profit", ascending = False) 
```
![DATA SORTING](https://github.com/user-attachments/assets/ef9d4a44-397e-4377-bead-3c6348cfa227)


#### RESULT
The Top Most-Profitable 5 States for the Bike Product Category in the United States 

```Python

Top_5_most_profitable_states_us = total_profit_by_states.sort_values("Profit", ascending = False).head()
Top_5_most_profitable_states_us
```
![DATA_RESULT](https://github.com/user-attachments/assets/758e3306-c188-4446-bd45-0f314746cf3d)


## DATA VISUALIZATION



![PANDAS SCREEN SHOT](https://github.com/user-attachments/assets/05fc55e4-15b3-4701-9b7c-4543b53eae57)






 
