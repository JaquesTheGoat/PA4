# Data Wrangling and Data Visualization Project - Programming Assignment 4

## Description

This repository contains a Python-based data wrangling and data visualization project that utilizes Matplotlib, Pandas, and Seaborn to manipulate and analyze the ECE Board Exam dataset. The project focuses on creating specific data frames and visualizations to present the results.

## Objectives

1. Identify the codes and functions needed in cleaning and visualizing data.
2. Apply and use different codes and functions to create a Python program for data wrangling and data visualization.

## Problem 1: Data Frame Creation

### Task

Create specific data frames based on given conditions from the ECE Board Exam dataset. Filter data on certain features such as `Track`, `Hometown`, and `Gender`.

**Function:**

```python

import pandas as pd


# Load the dataset from the CSV 
board = pd.read_csv('board.csv')
board   

```

**Output:**

![image](https://github.com/user-attachments/assets/ad93cf9c-33d6-4dcb-8940-f44131423ee8)
![image](https://github.com/user-attachments/assets/5e76c488-912e-44be-8891-c7e8605fffea)



### Required Data Frames

* **Data Frame 1 (Filename: Instru)**
	+ Columns: `["Name", "GEAS", "Electronics >70"]`
	+ Condition: Track = Instrumentation, Hometown = Luzon
 + input:
```python

# Create the Instru DataFrame by filtering for 'Track' equal to 'Instrumentation', 'Hometown' as 'Luzon', and 'Electronics' score over 70
Instru = board[(board['Track'] == 'Instrumentation') & (board['Hometown'] == 'Luzon') & (board['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]

# Show the records of the Instru DataFrame
Instru.head()
```
   
 Expected output:<b />

![image](https://github.com/user-attachments/assets/0e1a26ba-e339-4137-902c-0bece44c42cd)


* **Data Frame 2 (Filename: Mindy)**
	+ Columns: `["Name", "Track", "Electronics", "Average >=55"]`
	+ Condition: Hometown = Mindanao, Gender = Female
 + input:
```python




Mindy = board[(board['Hometown'] == 'Mindanao') & (board['Gender'] == 'Female')].copy()

# Calculate the average of the 'Math', 'Electronics', and 'GEAS' columns
Mindy['Average'] = Mindy[['Math','Electronics','GEAS','Communication']].mean(axis=1)

# Now create the Mindy DataFrame based on the 'Average' column
Mindy = Mindy[Mindy['Average'] >= 55]

# Display the rows of the Mindy DataFrame
Mindy[['Name', 'Track', 'Electronics', 'Average']]

```
	
Expected output:<b />

![image](https://github.com/user-attachments/assets/1ef40774-7b58-456d-a7e6-ce1f8d2407e8)

## Problem 2: Data Visualization

### Task

Create a visualization that shows how features such as `Track`, `Gender`, and `Hometown` contribute to the **average grade**.

+ function:
```python
# Import matplotlib for plotting
import matplotlib.pyplot as plt   

# Load the CSV file into a DataFrame
df = pd.read_csv('board.csv')     
```
#### + input:

```python
# Set figure size for the plot
plt.figure(figsize=(6, 5))        

# Create bar chart of Electronics by Track
plt.bar(df['Track'], df['Electronics'])  


```

### Expected Output

<img width="521" height="454" alt="Screen Shot 2025-09-23 at 3 58 15 PM" src="https://github.com/user-attachments/assets/6fb23962-21a9-4fdf-a7c4-46e5b65c7485" />

--- 
+ input:
```python

# Shows the gender
plt.figure(figsize=(6, 5))
plt.bar(board['Gender'], board['Electronics'])

```

<img width="572" height="451" alt="Screen Shot 2025-09-23 at 3 58 37 PM" src="https://github.com/user-attachments/assets/48d3414e-3979-49c5-92cf-60b494e07210" />

--- 
+ input:
```python
# Shows the Hometown
plt.figure(figsize=(6, 5))
plt.bar(board['Hometown'], board['Electronics'])

```

<img width="528" height="444" alt="Screen Shot 2025-09-23 at 3 58 54 PM" src="https://github.com/user-attachments/assets/b686691e-c0df-472b-902c-177ed4f23507" />




### Insights

* Does chosen track in college, gender, or hometown contribute to a higher average score?<b />

	+ The analysis reveals that a student's college track and hometown have a significant impact on their average score, with certain tracks and hometowns associated with higher average scores. On the other hand, gender does not appear to be a determining factor in achieving a higher average score.

--- 


# SUMMARY

In this programming assignment, I learned how to perform data wrangling and data visualization using Python libraries such as Pandas and Matplotlib. I applied these skills to analyze the ECE Board Exam dataset and created specific data frames and visualizations to present the results.

## Key Takeaways:
+ Data wrangling involves cleaning and manipulating data to prepare it for analysis.
+ Data visualization is an effective way to communicate insights and trends in data.
+ Matplotlib is a powerful library for creating static, animated, and interactive visualizations in Python.

## Common Errors:
+ Incorrect data typing and formatting
+ Failure to handle missing or duplicate data
+ Insufficient data cleaning and preprocessing
+ Misinterpretation of data visualization results


