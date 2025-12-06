# CSE160-Group-6-Final-Project
---

## Details
---
* Semester: Fall 2025
* Team Name: Jolly and Educated Data Science Lovers (JEDSL)

## Group Members:
* Luca Cevaer-Corey <lac525@lehigh.edu>
* Dean Clark <dmc227@lehigh.edu>
* Ester Frank <esf228@lehigh.edu>
* Joshua Guo <jog229@lehigh.edu>
* Sophia Pham <slp227@lehigh.edu>

## Problem Statement
---
<b>Finding affordable yet desirable housing in New York City (and state) is a persistent challenge.</b>

To aid with this, our goal is to create a model that can most accurately predict the price of a residential housing unit based on many different predictive features that we compiled.

## How to Run 
---

## Required Data Sources

Download the following datasets before running any scripts:

### Housing + Real Estate
NYC Real Estate Sales 2017
https://archive.nyu.edu/handle/2451/44425

NYC Real Estate Sales 2018
https://archive.nyu.edu/handle/2451/44426

### Crime Data
NYPD Arrest Data (Year-to-Date)
https://data.cityofnewyork.us/Public-Safety/NYPD-Arrest-Data-Year-to-Date-/uip8-fykc/about_data

### Neighborhood / Census Features
Smart Location Database (SLD)
https://catalog.data.gov/dataset/smart-location-database8

### Geographic Crosswalks
ZIP ↔ Census Tract Crosswalk (HUD USPS)
https://www.huduser.gov/portal/datasets/usps_crosswalk.html

FIPS Code Lookup
https://rowzero.com/datasets/fips-codes-lookup

## Data Cleaning
<b>Note: All of the scripts in this project are in R Markdown (rmd) notebooks, similar to a Jupyter Notebook. We recommend you use an Integrated Development Environment (IDE) such as Rstudio to be able to run all of the steps in a concise and visual manner.</b>

```
cleaning/
  ├─ Arrest_Data_Clean.Rmd
  ├─ NYC_RealEstate_2017.Rmd
  ├─ NYC_RealEstate_2018.Rmd
  ├─ dog_license_cleaning.Rmd
  ├─ sld_cleaning.Rmd
  ├─ tract_geoid_to_zip_cleaning.Rmd
  └─ FIPS_data.zip
```


1. Open RStudio.
2. Run the cleaning notebooks in this order:
  sld_cleaning.Rmd
  NYC_RealEstate_2017.Rmd
  NYC_RealEstate_2018.Rmd
  Arrest_Data_Clean.Rmd
  tract_geoid_to_zip_cleaning.Rmd
3. Ensure all cleaned datasets save to the correct locations.
4. Open the model/ directory and run:
  ```
  model/
    ├─ Arrest_Data_Modeling.Rmd
    ├─ Arrest_Data_Visualization.Rmd
    ├─ Arrest_Data_Tasks.Rmd
    └─ nycSLDModeling.Rmd
  ```

## Output
  Running the full workflow produces:
  Cleaned housing, crime, and census datasets
  A merged dataset for modeling
  Regression models predicting NYC housing prices
  Evaluation metrics (RMSE, cross-validation scores)
  Visualizations of borough-level patterns and feature relationships



### Modeling
* Use regression-based modeling to estimate housing values accross the 5 different boroughs in NYC --> employs linear regression ot capture relationships between teh indeprendent variables and housing prices
* Perform this process for both the SLD data and the crime data

### Model Evaluation
* Use the Root Mean Squared Error (RMSE) as the primary loss function
* K-fold cross-validation employed to assess the model's generalization ability and stability across various subsets of the data

