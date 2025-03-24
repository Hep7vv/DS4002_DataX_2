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

- Project 2 Code

DATA

- CPI.csv
- Data Appendix
- National Median Home Prices.csv
- cleaned_housing.csv
  
OUTPUT

- grade_scale.csv

References 

## Section 3: Reproducing Results

Step 1: importing addons

Start by importing pandas, numpy, matplotlib, and sklearn (import tree, RandomForestRegressor, and train_test_split from sklearn) these will be used for data cleaning, plotting, and running a random forest regressor model respectively

Step 2: import data

Download all files under the "Data" folder in this repository. create a dataframe called "merged_df" that joins the housing data according to "ParcelNumber". 

create a dataframe from the CPI data 

Step 3: Clean Data

drop all empty values from the dataframe, drop all values where teh sale amount is 0, drop all values that equal 'no dat', drop the extreme outliers (Debrooms equal 2215), drop the yearsbuilt that are prior to 1950 and after 2025, Convert Housing grades into numeric scores using the "grade_scale.PNG" in the OUTPUT folder for reference i.e. A++ == 10. 

With the CPI datafrome convert 'DATE' to a datetime format and extract the year (SaleDate). etract a 3 digit year and then convert to a full year, drop the two-year column, compute the average CPI per year, Merge the yearly average CPI back into the original DataFrame with the housing data.

drop duplicate entries from the large dataset

compute the mean and standard deviation of sale amount to find the z score, drop values that have a z score greater than 3

Step 4: Analysis

use sklearn to import tree and train_test_split. 

resample and process data, fit to the decision tree, visualize results

split data into training rows and testing rows, bootstrap, split into a train/test set,

bootstrap by creating a sample, fitting to decision tree, computing the rsq, and then making and saving predictions

build a random forest model, fit the rf model, model predictions
