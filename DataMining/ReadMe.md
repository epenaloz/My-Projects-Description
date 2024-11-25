## Data Mining Assignments
#### Libraries Used: Python 3.6, Spark 3.1.2
These assingments are assingments from my Data Mining Course. Each assignment requires Python and Spark only. The usage of Spark Dataframes or Spark SQL is not allowed. 

Below will be descriptions of the assignments, the algorithms implemented, and more.

Each assignment utilized the Yelp Dataset. We used subsets of the original Yelp dataset, which can be found here. 


### Homework 1: Exploring Yelp Dataset
Task: We were tasked to write a program to answer the following queries for data exploration
1. The total number of reviews
2. The number of reviews in 2018
3. The number of distinct users who wrote reviews
4. The top 10 users who wrote the largest number of reviews and the number of reviews they wrote
5. The number of distinct businesses that have been reviewed
6. The top 10 businesses that had the largest number of reviews and the number of reviews they had

### Homework 2: SON Algorithm, Apriori using Spark Frame Work (Frequent Itemsets)
Task: We were tasked to implement the SON algorithm and any algorithm of our choice to find frequent itemsets. The goal is to handle large data in a distributed environment while applying the algorithms we learned in class. Frequent item sets are sets of items that appear frequently together. This is useful data mining, especially in market-based environments. In this assignment we leveraged the Yelp Data and solved 3 cases.

**Case 1**: Calculate the combinations of frequent businesses qualified as frequent given a certain threshold. Here, we created baskets for each user, containing the business IDs that the user has reviewed. Each business ID is treated uniquely. 

**Case 2**: This is similar to case 1 but this time we are finding combinations of frequent user IDs. Here, we created baskets for each business, containing the user IDs for which the business has reviews. Each user ID is treated uniquely. 

I implemented Apriori to find frequent singles, pairs, triples, etc. My code continues to find frequent itemsets until there are no more frequent itemsets above the threshold. It outputs a TXT file for both cases, printing out the frequent itemsets. 

### Homework 2: Ta Fend Dataset (Kaggle)
**Case 3**: This case uses another data set called, "Ta Feng Dataset", which is found on Kaggle: https://bit.ly/2miWqFS
We have to apply our algorithm from Case 1 to this dataset. However, we were tasked to generate a **data pipeline** in where the input is the raw Ta Fend data set, there is a mid-output of a new CSV of the data after data cleansing/prepping, and the final output is a CSV file containing one column for "Date-CustomerID" and another column containing the "ProductID"
