Aviato Case Study (Aviato is a fictitious Operating System company that sells its OS to companies on a subscription basis)

--Slide 1 
The Problem
Approach 
Methodology
Key Findings
Recommendations

2024/01/26

Created by Zac Wu

--Slide 2
Problem statement
- Does Customer Experience have an impact on growth of Aviato’s annual subscription revenue? If yes, which Customer Experience metrics influence annual subscription revenue growth?

- What is the potential impact created (additional $ value) by providing better Customer Experience?

--Slide 3
Step-by-step approach
Data Preparation and Cleaning 
Consolidate data to include all the customer information & metrics
Data cleaning (trailing space, data types)
Ensure that the data is in a format suitable for statistical analysis

Exploratory Data Analysis
Summary statistics & outliers (scatter plot, box plot, bar plot, correlation matrix, etc)
Define annual revenue growth & dependent variable (revenue growth % vs. $) 

Correlation Analysis  
Point-Biserial Correlation (1 continuous variable and 1 binary variable) 
Pearson Correlation (2 continuous variables)

Regression Analysis
Model the relationship and estimate the impact of CX metrics on revenue.

Customer Segmentation 
Break out by segment and industry 

Findings & Recommendations


--Slide 4
Map categorical values to numeric (0 or 1)
For example, Knowledge Event

Exploratory Data Analysis
Define the upper and lower bounds to identify outliers, and remove outliers in annual revenue growth before any meaningful analysis
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR

IQR = Q3 - Q1

Correlation & Regression Analysis 
Binary Categorical Variables:
Variables: Knowledge Event, NowForum Event, OtherEvents Event, Partner Involvement.
Analysis: Calculate point-biserial correlation and p-values for each variable.
Numerical Variables:
Variables: average_nps, Product Adoption, # of Version Upgrades.
Analysis: Utilize Pearson Correlation analysis and perform regression analysis using the Ordinary Least Squares model.
Further Analysis:
Segmentation: Filter data by Customer Industry and segment.
Conduct additional correlation analysis to explore industry-specific trends.

corr_knowledge, p_value_knowledge = pointbiserialr(df['OtherEvents Event'], df['annual_revenue_growth_adj'])

OLS = Ordinary Least Squares

--Slide 5
Key Findings
The analysis reveals that among all the Customer Experience metrics, the Average Net Promoter Score (NPS) seems to have the most impact on annual subscription revenue growth. It is also the only CX metric that has an impact on annual subscription revenue growth.
The dependent variable is annual revenue growth in $. 

Key Findings (cont'd)
From the OLS Regression results, the regression equation is below: 
annual_revenue_growth (in $) = 17300 x average_nps - 88480
When the average Net Promoter Score is 0, the model predicts a negative annual revenue growth of approximately -$88,480.
The analysis indicates that a minimum average NPS of 5.1 is required to achieve non-negative revenue growth.
With each point increase in NPS, customers are expected to have an additional annual revenue growth of $17,300.
Investigating various customer segments and industries indicates positive correlations, with the average NPS exerting a bigger impact on revenue growth for Very Large Enterprise & Commercial customers and the Technology, Retail, and Wholesale industries compared to the overall average.

--Slide 6
Recommendations
1. Focus on Improving NPS
Given that NPS has the most significant impact on annual subscription revenue growth, the company Aviato should prioritize efforts to improve customer satisfaction and experience. 
2. Set a Minimum NPS Benchmark
Establishing a minimum average NPS of 5.1 is crucial to achieving positive revenue growth. This benchmark can serve as a performance target.
3.  Targeted Strategies for Key Segments
Tailor customer engagement strategies specifically for Very Large Enterprise & Commercial customers and the Technology, Retail, and Wholesale industries, where NPS has a greater influence.


Appendix
Dep. variable = annual_revenue_growth_adj

Indep. variable = average_nps
