## DEVELOPED BY: SriVarshan P
## REGISTER NO: 212222240104
## DATE:

# Ex.No: 08     MOVING AVERAGE MODEL AND EXPONENTIAL SMOOTHING
 
## AIM:
To implement Moving Average Model and Exponential smoothing Using Python.
## ALGORITHM:
1. Import necessary libraries
2. Read the tank loss time series data from a CSV file,Display the shape and the first 20 rows of
the dataset
3. Set the figure size for plots
4. Suppress warnings
5. Plot the first 50 values of the 'Value' column
6. Perform rolling average transformation with a window size of 5
7. Display the first 10 values of the rolling mean
8. Perform rolling average transformation with a window size of 10
9. Create a new figure for plotting,Plot the original data and fitted value
10. Show the plot
11. Also perform exponential smoothing and plot the graph
## PROGRAM:
```python
# Import necessary libraries
import pandas as pd
import matplotlib.pyplot as plt
import warnings

# Suppress warnings
warnings.filterwarnings("ignore")

# Load the dataset
file_path = 'russia_losses_equipment.csv'
data = pd.read_csv(file_path)

# Display the shape and the first 20 rows of the dataset
shape = data.shape
first_20_rows = data.head(20)

shape, first_20_rows

# Set figure size for plots
plt.figure(figsize=(10, 6))

# Extract the 'tank' column
tank_data = data['tank']

# Plot the first 50 values of the 'tank' column
plt.plot(tank_data[:50], label='Original Data')
plt.title("First 50 Values of 'Tank' Losses")
plt.xlabel("Index")
plt.ylabel("Tank Losses")
plt.legend()
plt.show()

# Perform rolling average transformation with a window size of 5
rolling_mean_3 = tank_data.rolling(window=3).mean()

# Display the first 10 values of the rolling mean with window size 5
rolling_mean_3.head(10)

# Perform rolling average transformation with a window size of 10
rolling_mean_10 = tank_data.rolling(window=10).mean()

# Create a new figure for plotting
plt.figure(figsize=(16, 8))

# Plot the original data and the rolling averages
plt.plot(tank_data, label='Original Data', color='red', alpha= 0.8)
plt.plot(rolling_mean_3, label='Rolling Mean (Window=3)', color='blue')
plt.plot(rolling_mean_10, label='Rolling Mean (Window=10)', color='green')
plt.title("Tank Losses with Rolling Averages")
plt.xlabel("Index")
plt.ylabel("Tank Losses")
plt.legend()
plt.show()


# Perform exponential smoothing and plot the graph
exp_smoothing = tank_data.ewm(alpha=0.1).mean()  
# Plot exponential smoothing
plt.figure(figsize=(10, 6))
plt.plot(tank_data, label='Original Data', color='blue', alpha=0.5)
plt.plot(exp_smoothing, label='Exponential Smoothing', color='red')
plt.title("Tank Losses with Exponential Smoothing")
plt.xlabel("Index")
plt.ylabel("Tank Losses")
plt.legend()
plt.show()

```

## OUTPUT:

### Plot Dataset

![image](https://github.com/user-attachments/assets/dd8e1ec8-7f63-46f1-a6f8-9dfe8e180d1d)


### GIVEN DATA

![image](https://github.com/user-attachments/assets/db59d5c9-8c10-4f7f-8ba0-4625d71b4ea1)


### Moving Average

![image](https://github.com/user-attachments/assets/c02a3ab9-da24-4afc-97de-0b494dc5f91e)



### Exponential Smoothing

![image](https://github.com/user-attachments/assets/4dece61f-18b1-4a3d-957f-25a8b4bb62d3)



## RESULT:
Thus, the program to implement the Moving Average Model and Exponential smoothing using python is executed successfully.
