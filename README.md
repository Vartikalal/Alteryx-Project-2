# Data Wrangling
`Tools: Alteryx, Excel`

The Business Problem Part 1
Pawdacity is a leading pet store chain in Wyoming with 13 stores throughout the state. This year, Pawdacity would like to expand and open a 14th store. Your manager has asked you to perform an analysis to recommend the city for Pawdacity’s newest store, based on predicted yearly sales.

Your first step in predicting yearly sales is to first format and blend together data from different datasets and deal with outliers.

Your manager has given you the following information to work with:

The monthly sales data for all of the Pawdacity stores for the year 2010.
NAICS data on the most current sales of all competitor stores where total sales is equal to 12 months of sales.
A partially parsed data file that can be used for population numbers.
Demographic data (Households with individuals under 18, Land Area, Population Density, and Total Families) for each city and county in the state of Wyoming. For people who are unfamiliar with the US city system, a state contains counties and counties contains one or more cities.
Map of Wyoming Counties

Steps to Success
Step 1: Business and Data Understanding
Your project should include a description of the key business decisions that need to be made.

Step 2: Building the Training Set
To properly build the model, and select predictor variables, create a dataset with the following columns:

City
2010 Census Population
Total Pawdacity Sales
Households with Under 18
Land Area
Population Density
Total Families

This dataset will be your training set to help you build a regression model in order to predict sales in Project 2.2. Every row should have sales data because we're trying to predict sales.

Notes

You should be consolidating the data at the city level and not at the store level. We only have data at the city wide level so any analysis at the store level will not be sufficient to complete this analysis.

We simply need to focus on cleaning up and blending the data together in this step.

If you’ve done everything correctly, the sum for each of the above columns should be:

Census Population: 213,862
Total Pawdacity Sales: 3,773,304
Households with Under 18: 34,064
Land Area: 33,071
Population Density: 63
Total Families: 62,653
with 11 rows of data

For Alteryx users:

Use the Autofield Tool to help quickly convert your data fields into the appropriate datafields for analysis.
Research these three specific formulas to help you get rid of unwanted characters in the Formula tool: ReplaceFirst, Left, FindString
Step 3: Dealing with Outliers
Once you have created the dataset, look for outliers and figure out how deal with your outliers. Use the IQR method to determine if there are outlier cities for each of the variables and then justify which city that has at least one outlier value should be removed.

IQR Steps

To calculate the upper fence and the lower fence, here are the exact steps:

1 . Calculate 1st quartile Q1 and 3rd quartile Q3 of the dataset. You can use the Excel function QUARTILE.INC or QUARTILE.EXC

2 . Calculate the Interquartile Range: IQR = Q3 - Q1

3 . Add 1.5 IQR to Q3 to get the upper fence: Upper Fence = Q3 + 1.5 IQR

4 . Subtract 1.5 IQR to Q1 to get the lower fence: Lower Fence = Q1 - 1.5 IQR

5 . Values above the Upper Fence and values below the Lower Fence are outliers





The Business Problem Part 2
Pawdacity is a leading pet store chain in Wyoming with 13 stores throughout the state. This year, Pawdacity would like to expand and open a 14th store. Your manager has asked you to perform an analysis to recommend the city for Pawdacity’s newest store, based on predicted yearly sales.

In the first part, you've already cleaned up the dataset and dealt with outliers.

In this project, you will take this dataset that you cleaned up and use this dataset to train a linear regression model in order to predict sales

Here are the criterias given to you in choosing the right city:

The new store should be located in a new city. That means there should be no existing stores in the new city.
The total sales for the entire competition in the new city should be less than $500,000
The new city where you want to build your new store must have a population over 4,000 people (based upon the 2014 US Census estimate).
The predicted yearly sales must be over $200,000.
The city chosen has the highest predicted sales from the predicted set.

Steps to Success
Step 1: Build a Linear Regression Model
Analyze the dataset you created in Project 2.1 and look at the distribution of your data. You can create histograms to look at each of your continuous and categorical data to determine the nature of the data you’re working with.

Important: You should have 10 rows of data before you begin modeling the dataset. The correct answers will assume that you removed Gillette from the dataset. If you decided to remove a different outlier in P2.1, you will have to adjust your dataset for this project.

Build a linear regression model to help you predict total sales.

Step 2: Perform the Analysis
Use your regression model to calculate predicted sales for all of the cities and use the criteria given to you to make a recommendation.



