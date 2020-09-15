# E-commerce-analysis

## Data Section:

•	The table A Conversion and table B Attribution datasets are merged using transaction ID (Conv_ID) and blank values in user_id column is replaced with respective user ids

•	The merged data has 211060 observations.(table A conversion has 79643 rows and table B attribution has 211060)

•	In order to know through which channel transactions has been done, I have created new data set based on highest normalized value in IHC_Conversion for each users. It has 79615 rows.

•	A Day column is created from the transaction date column (e.g 3/25/2018 is Sunday)

Tools used: Python, Power BI

## Methods Section:

Exploratory data analysis (EDA), Cohort Analysis, Customer Segmentation, Churn Detection, Summary Statistics.

## Analysis Section:

### Cohort analysis:

A cohort is a group of users who share something in common, eg: first purchase month. Cohort analysis can be helpful when it comes to understanding the loyalty of your customers and monitor the customer and revenue retention.

### Churn detection:

Step 1: RFM table and T value is calculated from the data
T= total age of the user (Users first transaction day to last day)
From the RFM table ,many of the user have frequency, recency, and monetary = 0. That's because Lifetimes only considers users who have made repeated transaction.

Step 2: Beta-geometric/negative binomial (bg/nbd) model is applied to identify the user has churned or likely to churn.

•	A user relationship has two phases: “alive” and  “dead”. When a user “dies,” He never buys again from the company. Each customer has their individual buy and die probability.

•	The BG/NBD model assumes that death can only occur after a repeat transaction. Because of this, user with only one transactions will have a 100% probability of being alive, which is suspect. 

Step 3: Churn risk on customers who have made at least one repeat transaction is considered and have assumed a user with <25% chance of being alive to have churned.
