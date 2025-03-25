## Contents
This repo contains data, results, and information regarding housing prices in Charlottesville in relation to enrollment at the University of Virginia

### including: 

Readme - explanation of the repository

Licensing - explans the terms under which this repository can be cited

Scripts - contains all source code for the project, scripts used with explanation of commands

Data - Contains all data for the project and a Data Appendix outlining analysis and variables for each respective dataset

Output - contains all output generated from data analysis including tables and figures 

## Section 1: Software and Platform

### Software:

Python: 3.10 via Google Colab

Python: 3.10 via Jupyter Notebook

### Addons: 

Pandas

Numpy

matplotlib

sklearn

- tree

- train_test_split

- RandomForestRegressor

### Platform:

Windows 10

## Section 2: Map of Documentation

README

LICENSE

SCRIPTS

- final_code.ipnyb

DATA

- CPI.csv
- Data Appendix
- Real_Estate_(Residential_Details).csv
- Real_Estate_(Sales).csv
- UVA Enrollment Data.csv
- merged_df_cleaned.csv
- reg_df.csv
- reg_df2.csv
  
OUTPUT

- allvariable_importance.PNG
- allvariable_prediction_rsq.PNG
- allvariable_tree.PNG
- enroll_prediction_rsq.PNG
- enroll_tree.PNG
- grade_scale.PNG
- price_beds.PNG
- price_enrollment.PNG
- price_footage.PNG
- price_grade.PNG
- price_year.PNG
- price_yearbuilt.PNG
- Predicted vs Actual.png
- Predicted vs Actual - Total Enrollment.png
- Average Sale Amount vs Enrollment by Year.png

REFRENCES.md

## Section 3: Reproducing Results

Step 1: importing addons

Start by importing pandas, numpy, matplotlib, sklearn, LinearRegression, r2_score, plt (import tree, RandomForestRegressor, and train_test_split from sklearn) these will be used for data cleaning, plotting, and running a random forest regressor model respectively

Step 2: import data

Real_Estate_(Residential_Details).csv and Real_Estate_(Sales).csv are downloaded from https://opendata.charlottesville.org/datasets are uploaded into a "Data" a folder in Jupyter notebook. Upload all files under the "Data" folder in this repository and merge the csv files. Download the CPI values from from US Bureau of Labor Statistics and upload it into Jupyter notebook. Download the enrollement data from UVA data digest from the UVA library and upload it into Jupyter notebook. 

Step 3: Clean Data

Create a dataframe called "merged_df" that joins the housing data according to "ParcelNumber". Clean the "merged_df" to create the "merged_df_cleaned" data frame. Upload the Create a dataframe called 'CPI_clean' from the CPI values. In the 'CPI_clean' dataframe convert 'DATE' to a datetime format and extract the year (SaleDate). Extract a 2 digit year and then convert to a full year, drop the two-year column, compute the average CPI per year.  Merge the 'CPI_clean' data frame with the "merged_df_cleaned" on the the variable 'SaleDateYr' to adjust the 'SaleAmount' for inflation based on the year 2024.  Merge the enrollement data frame with the "merged_df_cleaned" on the the variable 'Year'.  

On the "merged_df_cleaned" drop all empty values from the dataframe, drop all values where teh sale amount is 0, drop all values that equal 'no dat', drop the extreme outliers (Debrooms equal 2215), drop the yearsbuilt that are prior to 1950 and after 2025, convert housing grades into numeric scores using the "grade_scale.PNG" in the OUTPUT folder for reference i.e. A++ == 10. Also drop duplicate entries from the large dataset and compute the mean and standard deviation of 'SaleAmount_2024' to find the z score, drop values that have a z score greater than 3, to clean the 'SaleAmount_2024' variable.

Step 4: Analysis

use sklearn to import tree and train_test_split. 

resample and process data, fit to the decision tree, visualize results

split data into training rows and testing rows, bootstrap, split into a train/test set,

bootstrap by creating a sample, fitting to decision tree, computing the rsq, and then making and saving predictions

build a random forest model, fit the rf model, model predictions
