# # Exp 6 Analysis and Visualization of COVID-19 Dataset using Python

**Date:24/08/2026

## AIM:

To analyse a large real-world COVID-19 dataset using Python and visualize key trends and relationships using multiple types of graphs for meaningful insights.

## DESIGN STEPS:

### Step 1:

Clone the repository from GitHub.

### Step 2:

Create a Python project in the preferred IDE (VS Code/PyCharm/Jupyter Notebook).

### Step 3:

Create the Python program for analysing and visualizing the COVID-19 dataset using **Pandas** and **Matplotlib** libraries.

### Step 4:

Load the **`covid_cases.csv`** dataset using Pandas and explore the dataset by displaying its shape and column names.

### Step 5:

Check and handle missing values in the dataset, if any.

### Step 6:

Perform basic data exploration by finding the total number of records and generating the statistical summary using the `describe()` function.

### Step 7:

Use Matplotlib to create different visualizations:

* **Line Graph:** Trend of confirmed cases over time globally.
* **Bar Chart:** Top 10 countries by total confirmed cases.
* **Pie Chart:** Case distribution of the top 5 affected countries.
* **Scatter Plot:** Relationship between confirmed cases and deaths.
* **Histogram:** Distribution of active cases.

### Step 8:

Add appropriate titles, axis labels, legends, and other necessary labels to the graphs.

### Step 9:

Execute the program and analyze the generated visualizations to identify meaningful trends and relationships in the COVID-19 dataset.

## PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt

# Load the COVID-19 dataset
df = pd.read_csv("covid_case.csv")

# Display first 5 records
print("First 5 Records:")
print(df.head())

# Dataset information
print("\nDataset Information:")
print(df.info())

# Check missing values
print("\nMissing Values:")
print(df.isnull().sum())

# Basic statistical analysis
print("\nStatistical Summary:")
print(df.describe())

# Total COVID-19 cases by country
country_cases = df.groupby("Country")["Confirmed"].sum().sort_values(ascending=False)

print("\nTotal Confirmed Cases by Country:")
print(country_cases)

# Total deaths by country
country_deaths = df.groupby("Country")["Deaths"].sum().sort_values(ascending=False)

print("\nTotal Deaths by Country:")
print(country_deaths)

# Total recovered cases by country
country_recovered = df.groupby("Country")["Recovered"].sum().sort_values(ascending=False)

print("\nTotal Recovered Cases by Country:")
print(country_recovered)

# ---------------- Visualization ----------------

# 1. Confirmed cases by country
plt.figure(figsize=(8, 5))
country_cases.plot(kind="bar")
plt.title("Total Confirmed COVID-19 Cases by Country")
plt.xlabel("Country")
plt.ylabel("Confirmed Cases")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# 2. Deaths by country
plt.figure(figsize=(8, 5))
country_deaths.plot(kind="bar")
plt.title("Total COVID-19 Deaths by Country")
plt.xlabel("Country")
plt.ylabel("Deaths")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# 3. Recovered cases by country
plt.figure(figsize=(8, 5))
country_recovered.plot(kind="bar")
plt.title("Total Recovered COVID-19 Cases by Country")
plt.xlabel("Country")
plt.ylabel("Recovered Cases")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# 4. COVID-19 trend over time
df["Date"] = pd.to_datetime(df["Date"])

daily_cases = df.groupby("Date")["Confirmed"].sum()

plt.figure(figsize=(10, 5))
daily_cases.plot(kind="line")
plt.title("COVID-19 Confirmed Cases Over Time")
plt.xlabel("Date")
plt.ylabel("Confirmed Cases")
plt.grid()
plt.tight_layout()
plt.show()

# 5. Active cases by country
active_cases = df.groupby("Country")["Active"].sum().sort_values(ascending=False)

plt.figure(figsize=(8, 5))
active_cases.plot(kind="bar")
plt.title("Active COVID-19 Cases by Country")
plt.xlabel("Country")
plt.ylabel("Active Cases")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()


```


## OUTPUT:
<img width="635" height="697" alt="image" src="https://github.com/user-attachments/assets/bd0338ba-fe8e-4cae-90d8-d5b095f98e53" />
<img width="656" height="761" alt="image" src="https://github.com/user-attachments/assets/006130db-40ad-4c9b-a9e4-4c2d020db7e3" />
<img width="434" height="351" alt="image" src="https://github.com/user-attachments/assets/742df643-0f77-4fb3-bc3c-269ccebac131" />
<img width="1024" height="633" alt="image" src="https://github.com/user-attachments/assets/2bf7073d-72ac-43e8-9fd1-9e4557d91654" />
<img width="1039" height="639" alt="image" src="https://github.com/user-attachments/assets/609d9618-b76d-473b-ac73-75ea4eaece98" />
<img width="1018" height="610" alt="image" src="https://github.com/user-attachments/assets/6770bc71-e142-4ad0-90ff-ef293a85241b" />
<img width="1025" height="620" alt="image" src="https://github.com/user-attachments/assets/324d992e-4eb0-446c-afbc-9c836a10f45d" />

<img width="1025" height="620" alt="image" src="https://github.com/user-attachments/assets/3471ef44-9f57-4d06-8941-0de60e0dcdb1" />





## RESULT:

The COVID-19 dataset was successfully analysed using Python. The dataset was explored using Pandas, and meaningful trends and relationships were visualized using different types of graphs such as line graph, bar chart, pie chart, scatter plot, and histogram using Matplotlib.
