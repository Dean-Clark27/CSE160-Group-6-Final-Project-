# CSE160-Group-6-Final-Project
---

## Details
---
* Semester: Fall 2025
* Team Name: Jolly and Educated Data Science Lovers (JEDSL)

### Group Members:
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
### Data Cleaning
<b>Note: All of the scripts in this project are in R Markdown (rmd) notebooks, similar to a Jupyter Notebook. We recommend you use an Integrated Development Environment (IDE) such as Rstudio to be able to run all of the steps in a concise and visual manner.</b>

1. SLD Cleaning - sld_cleaning.Rmd
* Consisted of 220740 instances, each a census block group (CBG) with data tied to it from the 2018 census (and some info from the 2010 census)
* Filtered down to just New York state entries by selecting the subset of the dataframe with a State Federal Information Processing System (FIPS) code of 36, which represents NY
* To make the 117 features in the dataset more comprehensible, the columns were assigned more descriptive names to investigate the dataset
* -> This helped determine which features were important, which columns with missing features we wanted to remove, and how the features related to each other
changed the names back
* 24 columns were removed from the dataset as a baseline due to redundancy and missing values, all whose information is covered by other, more descriptive features of the dataset
* Using an additional dataset holding a FIPS code lookup table, the county names were appended to the SLD to give the programmers (us) more context about the areas we are dealing with

2. Real Estate Cleaning - NYC_RealEstate_2017.Rmd, NYC_RealEstate_2018.Rmd
* Data on real estate sales from 2018 and 2017
* Reduced features to only focus on the important information, such as price, date, year, borough, type of building, etc. 
* Removed sales for buildings that were unusable (defined as being $0-10) by making them NA and excluding that from the new dataframe
* There were different types of real estate in the dataset, including warehouses and retail buildings
* Since the scope of this project is based around housing, we took the first three categories of single-family and multi-family homes and used that for our data → this model is to be used for real estate houses in NYC
* Reduced from 84k-88k rows to about 26k rows after filtering out types of real estate and only including usable sales (for both years)
* NOTE: We only included singe-family and multi-family homes. This can be expanded to otehr building types such as condos and apartments for better representation of housing in certain areas of NYC

3. Crime data...

4. Additional cleaning...

### Modeling
* Use regression-based modeling to estimate housing values accross the 5 different boroughs in NYC --> employs linear regression ot capture relationships between teh indeprendent variables and housing prices
* Perform this process for botht eh SLD data and the crime data

### Model Evaluation
* Use the Root Mean Squared Error (RMSE) as the primary loss function
* K-fold cross-validation employed to assess the model's generalization ability and stability across various subsets of the data

