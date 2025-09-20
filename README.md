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

### Expected Output
<img width="563" alt="Screen Shot 2024-09-20 at 10 47 14 PM" src="https://github.com/user-attachments/assets/bf98554b-8721-4979-92e7-b283b5791719">

--- 
<img width="557" alt="Screen Shot 2024-09-20 at 10 47 28 PM" src="https://github.com/user-attachments/assets/2a0776df-ee8d-4935-b50f-8b45d05f0315">

--- 
<img width="558" alt="Screen Shot 2024-09-20 at 10 47 36 PM" src="https://github.com/user-attachments/assets/a4c894db-87b3-4e16-a149-98791920dadb">




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


