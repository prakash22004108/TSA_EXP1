# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the CSV file
file_path = "NYCTaxiFares.csv"
data = pd.read_csv(file_path)

# Convert pickup_datetime to datetime format
data['pickup_datetime'] = pd.to_datetime(data['pickup_datetime'])

# Display basic information about the dataset
print("Dataset Info:")
print(data.info())

# Display summary statistics
print("\nSummary Statistics:")
print(data.describe())

# Countplot of fare class distribution
plt.figure(figsize=(8, 5))
sns.countplot(x='fare_class', data=data, palette='viridis')
plt.title('Fare Class Distribution')
plt.xlabel('Fare Class')
plt.ylabel('Count')
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.show()

# Bar plot of average fare amount by passenger count
plt.figure(figsize=(12, 6))
passenger_fares = data.groupby('passenger_count')['fare_amount'].mean().sort_values()
passenger_fares.plot(kind='bar', color='blue')
plt.title('Average Fare Amount by Passenger Count')
plt.xlabel('Passenger Count')
plt.ylabel('Average Fare Amount')
plt.xticks(rotation=0)
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.show()
```









# OUTPUT:
![image](https://github.com/user-attachments/assets/9a13c70e-ba6c-4f86-9552-871eb61d71f1)






# RESULT:
Thus we have created the python code for plotting the time series of given data.
