# ConnectaTel Telecom Analysis

## Overview
This project analyzes customer behavior at ConnectaTel, a telecommunications company operating in Latin America. The objective is to understand usage patterns in calls and text messages, identify data quality issues, detect outliers, and segment customers by age and usage level to generate business recommendations.

## Business Goal
The analysis helps ConnectaTel:
- identify customer usage patterns
- detect high-value and low-value customer segments
- improve retention and upselling opportunities
- design better telecom plans based on real usage behavior

## Datasets
This project uses three datasets:

- **plans.csv**  
  Includes telecom plan information such as monthly price, included messages, included minutes, monthly GB, and extra charges.

- **users_latam.csv**  
  Includes customer information such as user ID, age, city, registration date, plan, and churn date.

- **usage.csv**  
  Includes detailed service usage logs such as event type (`call` or `text`), usage date, call duration, and message length.

## Analysis Workflow
The notebook follows these stages:

1. Data loading and exploration  
2. Data quality review  
3. Data cleaning  
4. User-level aggregation  
5. Descriptive analysis and visualizations  
6. Outlier detection  
7. Customer segmentation  
8. Executive business insights  

## Key Tasks Performed
- handled missing values and invalid entries
- replaced sentinel values such as `-999` in `age`
- converted invalid categories such as `?` in `city` into missing values
- corrected impossible dates
- aggregated usage behavior by user
- created customer segments by usage and age
- analyzed distributions and outliers with histograms and boxplots
- translated findings into business recommendations

## How to Run
You can run this notebook in:

### Google Colab
1. Open Google Colab
2. Upload the `.ipynb` notebook
3. Upload the datasets
4. Run all cells from top to bottom

### Jupyter Notebook
1. Open Jupyter Notebook locally
2. Make sure the datasets are accessible
3. Run all cells in order

## Requirements
This project uses:
- pandas
- numpy
- matplotlib
- seaborn

## Reproducibility Notes
To reproduce the analysis correctly:
- keep the expected dataset names
- run the notebook from top to bottom
- do not skip cleaning steps
- rebuild `user_profile` after cleaning if needed

## Main Outputs
- cleaned and structured telecom customer data
- user-level usage metrics
- distribution and outlier analysis
- customer segmentation by age and usage
- executive recommendations for ConnectaTel

## Author
Miguel Torres
