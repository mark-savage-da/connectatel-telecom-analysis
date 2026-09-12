# ConnectaTel Telecom Analysis

## Project Overview
This project analyzes customer behavior at **ConnectaTel**, a telecommunications company operating in Latin America. The objective is to understand how customers use call and text services, identify data quality issues, detect unusual usage patterns, and segment users by age and intensity of usage in order to generate actionable business recommendations.

The notebook covers the full analytical workflow, from raw data exploration and data cleaning to user-level aggregation, descriptive analysis, outlier detection, segmentation, and executive interpretation for decision-making.

## Business Context
ConnectaTel needs a better understanding of how its customer base actually behaves in order to improve plan design, identify valuable customer groups, and detect business opportunities related to retention and upselling.

From a business perspective, this analysis is useful to:
- understand usage behavior in calls and text messages
- detect inconsistent or low-quality data before making decisions
- identify low-, medium-, and high-usage customers
- evaluate which segments may be more valuable for the business
- support the design of better telecom plans based on real customer behavior

## Datasets Used
This project uses three datasets:

### 1. `plans.csv`
Contains the commercial structure of the telecom plans currently offered by the company, including:
- plan name
- included messages
- included minutes
- monthly GB
- monthly fee
- extra charges for additional usage

### 2. `users_latam.csv`
Contains customer-level information, including:
- user ID
- first name
- last name
- age
- city
- registration date
- assigned plan
- churn date

### 3. `usage.csv`
Contains service-level usage logs for each customer, including:
- event ID
- user ID
- type of event (`call` or `text`)
- usage date
- call duration
- message length

## Project Objectives
The main objectives of this analysis are:

- evaluate the quality of the source data before analysis
- identify missing values, invalid values, and sentinel values
- standardize dates and detect out-of-range records
- aggregate service usage at the customer level
- analyze customer behavior using descriptive statistics and visualizations
- detect outliers and interpret whether they represent data errors or real business behavior
- segment customers by usage intensity and age group
- translate the findings into business recommendations for stakeholders

## Analytical Workflow
The notebook follows a structured analytical process:

### 1. Data Loading and Initial Exploration
The three datasets are imported and reviewed to understand:
- structure
- dimensions
- column names
- data types
- initial content preview

### 2. Data Quality Review
A full data quality assessment is performed to identify:
- missing values
- null proportions
- possible logical absences
- invalid entries
- sentinel values
- inconsistent labels
- date problems

### 3. Data Cleaning
The cleaning stage includes:
- replacing sentinel values such as `-999` in `age`
- converting invalid values such as `?` in `city` into nulls
- converting date columns into datetime format
- detecting dates outside the expected range
- preserving logical nulls in `duration` and `length` when they depend on event type

### 4. User-Level Aggregation
The usage dataset is aggregated by `user_id` to generate customer-level metrics:
- `cant_mensajes`
- `cant_llamadas`
- `cant_minutos_llamada`

This aggregated dataset is then merged with the customer table to create a more complete user profile.

### 5. Descriptive Analysis
The project includes descriptive analysis for:
- customer age
- number of messages
- number of calls
- total call minutes
- plan distribution

This allows a better understanding of central tendency, spread, and general customer behavior.

### 6. Data Visualization
Histograms and boxplots are used to:
- evaluate the distribution of the main variables
- compare behavior by plan type
- identify whether variables are symmetric or right-skewed
- visually detect outliers

### 7. Outlier Detection
Outliers are analyzed using:
- boxplots
- IQR-based limits

The goal is not only to detect extreme values, but also to decide whether they represent:
- data capture issues
- or valid high-intensity customer behavior

### 8. Customer Segmentation
Customers are segmented into usage groups:
- `Bajo uso`
- `Uso medio`
- `Alto uso`

They are also segmented by age group:
- `Joven`
- `Adulto`
- `Adulto Mayor`

This helps connect customer behavior with commercial interpretation.

### 9. Executive Insights
The final stage translates the technical analysis into business conclusions focused on:
- data quality implications
- customer usage behavior
- valuable segments
- extreme usage patterns
- strategic recommendations for telecom plan design

## Key Tasks Performed
This project includes the following concrete tasks:

- imported and explored multiple structured datasets
- reviewed missing values and null proportions
- identified sentinel values and invalid categories
- standardized date columns and validated years
- corrected invalid entries in key customer variables
- validated logical missingness in telecom usage variables
- aggregated event-level records into customer-level behavioral metrics
- created histograms and boxplots for key numeric variables
- calculated IQR thresholds for outlier detection
- segmented users by usage intensity
- segmented users by demographic age groups
- wrote an executive analysis for stakeholders

## Key Findings
Some of the most relevant findings from the analysis include:

- the source data contained relevant quality issues such as null values, sentinel values, and dates outside the expected range
- `churn_date` had a very high proportion of missing values, but these were interpreted as a logical absence of cancellation rather than an error
- missing values in `duration` and `length` depended on event type and therefore were preserved as structural nulls
- customer behavior was heterogeneous, with most users concentrated in low- or medium-usage patterns and a smaller group showing much higher service consumption
- the strongest outliers were found in total call minutes, suggesting the existence of more intensive users
- high-usage users appear to be the most commercially relevant group for retention and upselling strategies

## Business Recommendations
Based on the analysis, ConnectaTel could consider the following actions:

- design **upselling campaigns** for customers with high usage who are still on lower-value plans
- maintain **simple and affordable plans** for low-usage customers to improve retention
- create more differentiated offers for high-intensity users
- use age-based segmentation to improve targeting and messaging
- strengthen data quality controls before future analysis and reporting
- monitor extreme usage customers separately, since they may represent strategic revenue opportunities

## Personal Voice & Learning

- I learned that an **outlier should not automatically be treated as an error**.
- **High-usage customers** may represent valuable business opportunities rather than invalid observations.
- This analysis helped me connect technical data validation with business decisions in **customer segmentation, retention, and upselling**.

## Repository Structure
A recommended repository structure for this project is:

```text
connectatel-telecom-analysis/
│
├── README.md
├── connectatel-telecom-analysis.ipynb
└── datasets/
    ├── plans.csv
    ├── users_latam.csv
    └── usage.csv
