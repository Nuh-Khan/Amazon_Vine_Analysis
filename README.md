# Amazon_Vine_Analysis
Big Data analysis using Google Colab, Pyspark, Postgres/pgAdmin, AWS RDS, SQL

## Overview

The goal of this project is to examine Amazon reviews authored by members of the paid **Amazon Vine program**. This service enables manufacturers and publishers to obtain reviews for their products and assess any potential biases between **Vine** members and **Non-Vine** member reviews.

Companies pay a fee to Amazon and may offer free products to Vine members, who are then obligated to submit a review. To determine if there is any bias towards favorable reviews from Vine members compared to non-members, we need to identify the percentage of 5-star ratings out of the total ratings. For this exercise, we were asked to choose from 50 datasets to extract, transform, and load into a dataframe to conduct our analysis. Throughout the analysis, we use:

- `PySpark` for extracting the dataset, transforming the data, connecting to `AWS RDS` instances, and loading the transformed data into `pgAdmin`.
- `Google Colab` for importing `PySpark` libraries and connecting to `Postgres` to create `SQL` tables and export the results.

From the available datasets, I opted to analyze reviews submitted by users in the **"Camera"** category.

The dataset used for this analysis can be found [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Camera_v1_00.tsv.gz).
