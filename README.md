# Amazon_Vine_Analysis
## Overview
SellBy pays a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.  Analysis is requested to determine if there is any bias toward favorable reviews from Vine members in the Kitchen dataset.  To assess this bias the dataset was extracted to a DataFrame in Google Colab, and then transformed into four Dataframes (customers_table, products_table, review_id_table and vine_table) that were uploaded to pgAdmin. The vine_table was then further filtered down to only include rows where total vote count was 20 or greater to pick reviews that are more likely to be helpful and to avoid having division by zero errors.  On top of this, we filtered these results down to rows where the number of helpful votes to total votes was 50% or greater.  Using this finalized DataFrame, we assessed the propensity of Paid (vine) versus Unpaid (not_vine) reviews to garner a 5 star review on Kitchen products.

## Results and Analysis

* Filtered Vine Reviews
  * Total Reviews: 1,207
  * ![Screen Shot 2022-07-24 at 6 10 30 PM](https://user-images.githubusercontent.com/98665941/180669604-08e3c195-ace9-4830-a424-4836e76f1093.png)
  * 5 Star Vine Reviews: 509
  * % of Vine Reviews with 5 Stars: 42.17%
  * ![Screen Shot 2022-07-24 at 6 21 45 PM](https://user-images.githubusercontent.com/98665941/180669997-119dfea3-ec5c-423e-a978-c4aeea21669b.png)


* Filtered Non-Vine Reviews
  *  97,839
  *  ![Screen Shot 2022-07-24 at 6 13 29 PM](https://user-images.githubusercontent.com/98665941/180669686-65d86dc1-1c17-4934-8fab-e0d0eea7d40d.png)
  *  5 Star Non-Vine Reviews: 45,858
  *  % of Non-Vine Reviews with 5 Stars: 46.87%
  *  ![Screen Shot 2022-07-24 at 6 24 02 PM](https://user-images.githubusercontent.com/98665941/180670073-eb936707-12dc-4f44-816c-a9be6fe4c992.png)

## Summary
Initial analysis does not indicate positivity bias for paid (Vine) reviews as the percentage of 5 star reviews for paid reviews is lower than the unpaid reviews.  At 46.9% versus 42.2%, 5 star unpaid reviews are almost 5% more likely than paid 5 star reviews in the dataset.  Not recommended to make substantive decision basis this analysis due to the low instance (1,207) of paid reviews, but the trend may be indicative that kitchen items are less susceptible to bias for paid reviews.  Would recommend further analysis basis the product_id with a higher tolerance to "helpful votes" to determine if this trend continues.  
