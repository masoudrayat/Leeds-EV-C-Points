# Leeds EV Chargepoint Utilization Analysis

<a id="overview"></a>
## Project Overview

This project focused on analyzing a dataset of electric vehicle charging events at various charging points in Leeds. The dataset, which includes 3,176,803 entries and 8 columns, covers a year from 2017-01-01 to 2018-01-01. It includes details like start and end dates, energy consumption, and plugin duration.

### Key Highlights:
- Identified 25,126 unique charging points or stations.
- Visualization of charging events.
- Analysis of total energy consumption.
- Analysis of Charging Point IDs for average plugin duration.
- Using histograms, examined energy consumption and plugin duration distribution.
- Investigated peak charging times and temporal trends.
- Examined the correlation between plugin duration and energy consumption.
- Data exploration was completed using Google Colab, and data querying was performed with PySpark.

<a id="data-exploration"></a>
## Data Exploration and Preprocessing

The data exploration and preprocessing steps involve:
- Importing necessary libraries
- Loading the dataset
- Cleaning and preparing the data for analysis

<a id="visualizations"></a>
## Visualizations

The project includes various visualizations to understand the utilization patterns of EV chargepoints. These visualizations are created using libraries such as Matplotlib and Seaborn.

<a id="pyspark-queries"></a>
## Query with PySpark

PySpark is used for querying the dataset to extract meaningful insights. The queries focus on understanding the usage patterns based on different parameters like time of day and day of the week.

<a id="dependencies"></a>
## Dependencies and Installation

- Python 3.x
- Pandas
- Matplotlib
- Seaborn
- PySpark

<a id="usage"></a>
## Usage
To run the analysis, execute the provided Jupyter Notebook. The notebook contains all the necessary code for data loading, preprocessing, visualization, and querying.

```bash
jupyter notebook Leeds_EV_Chargepoint_Utilization.ipynb
```

### Importing Libraries
```python
import matplotlib
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from pyspark.sql import SparkSession
from pyspark.sql.functions import sum as _sum
from pyspark.sql.functions import col, dayofweek, concat, to_timestamp, hour, lit, count
```

### Loading Data
```python
# Load data
DATA_PATH = './electric-chargepoint-analysis-2017-raw-domestics-data.csv'
df = pd.read_csv(DATA_PATH)
```

### Data Preprocessing
```python
# Data preprocessing steps
df['Start Date'] = pd.to_datetime(df['Start Date'])
df['End Date'] = pd.to_datetime(df['End Date'])
df['Energy (kWh)'] = df['Energy (kWh)'].astype(float)
```

### Visualization Example
```python
# Visualization of total energy consumption
plt.figure(figsize=(10,6))
sns.histplot(df['Energy (kWh)'], bins=50, kde=True)
plt.title('Distribution of Energy Consumption')
plt.xlabel('Energy (kWh)')
plt.ylabel('Frequency')
plt.show()
```

### PySpark Query Example
```python
# PySpark setup
spark = SparkSession.builder.appName("EV Chargepoint Analysis").getOrCreate()
spark_df = spark.createDataFrame(df)


