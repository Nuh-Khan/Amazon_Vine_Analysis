# Amazon_Vine_Analysis
Big Data analysis using Google Colab, Pyspark, Postgres/pgAdmin, AWS RDS, SQL

## Overview

The goal of this project is to examine Amazon reviews authored by members of the paid **Amazon Vine program**. This service enables manufacturers and publishers to obtain reviews for their products and assess any potential biases between **Vine** members and **Non-Vine** member reviews.

Companies pay a fee to Amazon and may offer free products to Vine members, who are then obligated to submit a review. To determine if there is any bias towards favorable reviews from Vine members compared to non-members, we need to identify the percentage of 5-star ratings out of the total ratings. For this exercise, we were asked to choose from 50 datasets to extract, transform, and load into a dataframe to conduct our analysis. Throughout the analysis, we use:

- `PySpark` for extracting the dataset, transforming the data, connecting to `AWS RDS` instances, and loading the transformed data into `pgAdmin`.
- `Google Colab` for importing `PySpark` libraries and connecting to `Postgres` to create `SQL` tables and export the results.

From the available datasets, I opted to analyze reviews submitted by users in the **"Camera"** category.

The dataset used for this analysis can be found [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Camera_v1_00.tsv.gz).

## Results


The dataset contained over 1.8 million reviews. To concentrate on reviews likely to be more helpful, we filtered the dataset based on:

* Total Votes count equal to or greater than 20.
![TotalVoteCount](https://github.com/Nuh-Khan/Amazon_Vine_Analysis/blob/main/Images/total_votes-count.png)

* Helpful Votes percentage of Total Votes equal to or greater than 50%.
![Helpful](https://github.com/Nuh-Khan/Amazon_Vine_Analysis/blob/main/Images/helpful.png)

This filtering reduced the total number of reviews from 1.8 million to 51.1K, allowing us to address the following questions:

**1. What is the number of Vine and non-Vine reviews?**

* **Vine** members contributed 10.7% (607) of the reviews, while the remaining 89.3% came from **Non-Vine** members (50,522).

**2. How many 5-star Vine reviews were there? How many 5-star non-Vine reviews were there?**

* **Vine** members provided 257 out of 607 5-star reviews.
* **Non-Vine** members offered 25,220 out of 50,522 5-star reviews.

**3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?**

* 42.34% of **Vine** member reviews received a 5-star rating.
* 49.92% of **Non-Vine** member reviews received a 5-star rating.


![All3](https://github.com/Nuh-Khan/Amazon_Vine_Analysis/blob/main/Images/all3.png)

## Summary

Based on the results, **Vine** members did not exhibit bias when rating products, as the proportion of 5-star ratings was around 7.6% lower for **Vine** members compared to **Non-Vine** members (42.3% vs. 49.9%). This implies that Vine customers might be more discerning when providing their reviews. To further validate this assumption, we should analyze all the data without filtering it by the ratio of helpful to total votes, as was done in this analysis. Examining the complete data set would offer more insight and help us strengthen our assumption.

Moreover, performing the same analysis with datasets from various product categories can yield a more holistic view of whether **Vine** member reviews are biased.


