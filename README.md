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

The dataset contained over 1.8 million reviews. To focus on reviews that were more likely to be helpful, we filtered the dataset by:

- Count of Total Votes equal to or greater than 20.
![TotalVoteCount](https://github.com/Nuh-Khan/Amazon_Vine_Analysis/blob/main/Images/total_votes-count.png)

- Percentage of Helpful Votes to Total Votes equal to or greater than 50%. 
![Helpful](https://github.com/Nuh-Khan/Amazon_Vine_Analysis/blob/main/Images/helpful.png)

This filtering reduced the total number of reviews from 1.8 million to 51.1K. This allowed us to answer the following questions:

**1. How many Vine reviews and non-Vine reviews were there?**

- **Vine** members made up only 10.7% (607) of the reviews, while the remaining 89.2% were **Non-Vine** members (50,522).

**2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?**

- **Vine** members gave 257 out of 607 reviews a 5-star rating.
- **Non-Vine** members gave 25,220 out of 50,522 reviews a 5-star rating.

**3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?**

- 42.34% of the reviews for **Vine** members were rated 5 stars.
- 49.92% of the reviews for **Non-Vine** members were rated 5 stars.

![All3](https://github.com/Nuh-Khan/Amazon_Vine_Analysis/blob/main/Images/all3.png)
