# Amazon Vine Analysis

**Overview**

This project is a mock scenario where a data analyst, analyzes product reviews for a startup called _Big Market_. Big Market is a marketing company that helps business optimize their marketing efforts. One of their clients is _Sellby_, who are about to release a large catalog of products on a leading retail website. Sellby wants to know how the reviews of their products compared to similar products sold by their competitors. They also want to enroll in a program that gives free products to selected reviewers and they wants to know if it&#39;s worth the cost. So, the data analyst was tasked to analyze _Amazon_ reviews written by members of the paid _Amazon Vine program_. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, beauty products dataset was analyzed using:

**PySpark** to perform the ETL process to extract the dataset, transform the data, connect to an **AWS RDS** instance, and load the transformed data into **pgAdmin**. Later, **Pandas** was used to determine if there is any bias toward favorable reviews from Vine members in the dataset.

**Data Source:** https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon\_reviews\_us\_Beauty\_v1\_00.tsv.gz

**Work Files:**  [challenge\_schema.sql](https://github.com/paulviet/Amazon_Vine_Analysis/blob/main/challenge_schema.sql), [Amazon\_Reviews\_ETL.ipynb](https://github.com/paulviet/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb), [Vine\_Review\_Analysis.ipynb](https://github.com/paulviet/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb)

**Results**

- **How many Vine reviews and non-Vine reviews were there?**

At the time the analysis was performed, there was a total of **647** Vine reviews compared to **74113** Non-Vine Reviews. These votes were the ones that matches the following criteria:

1. The Review has been voted up at least 20 times, to pick reviews that are more likely to be helpful and to avoid having division by zero errors later.
2. 50% or more of these upvotes were voting the review as most helpful.

- **How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?**

The total of Vine reviews with 5-stars was, **224**. While the Non-Vine 5-star reviews was 42118.

These votes were the ones that matches the same criteria above.

- **What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?**

The percentage of 5 star for Vine reviews was **34.6%** while it was **56.8%** for non-Vine reviews.

**Summary**

When looking at the numbers of Vine reviews (647) compared to Non-Vine Reviews (74113). And the percentage of 5 star for Vine reviews (34.6%) and non-Vine reviews (56.8%). Its hard to say for certain whether the Vine program creates bias in reviews.

However, not limiting the analysis to Beauty products and adding wide rang of other products, might give as a different insight. Also looking at 4-stars and 3 stars rated review might give a better understanding of the Vine program.
 Plus, there are other factors that could play a role in how effective the program is, such as who the reviewer is. For example, a celebrity or an influencer could change how the customers feel about the helpless of the review.