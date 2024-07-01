# Leeds EV Chargepoint Utilization Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Key Highlights](#key-highlights)
- [Data Exploration and Preprocessing](#data-exploration-and-preprocessing)
- [Project Structure](#project-structure)
- [Visualizations](#visualizations)
- [Query with PySpark](#query-with-pyspark)
- [Dependencies and Installation](#dependencies-and-installation)
- [Usage](#usage)

## Project Overview
This project focused on analyzing a dataset of electric vehicle charging events at various charging points in Leeds. The dataset, which includes 3,176,803 entries and 8 columns, covers a year from 2017-01-01 to 2018-01-01. It includes details like start and end dates, energy consumption, and plugin duration.

## Key Highlights
- Identified 25,126 unique charging points or stations.
- Visualization of charging events.
- Analysis of total energy consumption.
- Analysis of Charging Point IDs for average plugin duration.
- Using histograms, examined energy consumption and plugin duration distribution.
- Investigated peak charging times and temporal trends.
- Examined the correlation between plugin duration and energy consumption.
- Data exploration was completed using Google Colab, and data querying was performed with PySpark.

## Data Exploration and Preprocessing
The data exploration and preprocessing steps involve:
- Importing necessary libraries
- Loading the dataset
- Cleaning and preparing the data for analysis

## Project Structure

The project is organized into the following directories and files:

- `notebooks/`: Contains the Jupyter Notebook used for the analysis.
  - `Leeds_EV_Chargepoint_Utilization.ipynb`: The main Jupyter Notebook that performs the analysis and generates the report.
  - `link`: A link to the dataset.

## Visualizations
The project includes various visualizations to understand the utilization patterns of EV chargepoints. These visualizations are created using libraries such as Matplotlib and Seaborn.

## Query with PySpark
PySpark is used for querying the dataset to extract meaningful insights. The queries focus on understanding the usage patterns based on different parameters like time of day and day of the week.

## Dependencies and Installation
- Python 3.x
- Pandas
- Matplotlib
- Seaborn
- PySpark

## Usage
To run the analysis, execute the provided Jupyter Notebook. The notebook contains all the necessary code for data loading, preprocessing, visualization, and querying.

```bash
jupyter notebook Leeds_EV_Chargepoint_Utilization.ipynb
spark = SparkSession.builder.appName("EV Chargepoint Analysis").getOrCreate()
spark_df = spark.createDataFrame(df)
