#  Big Data Recipe & Culinary Recommendation Pipeline

A scalable Data Engineering and Recommendation pipeline built using **PySpark** and **Google Colab** to process and analyze massive culinary datasets from Food.com.

## Project Overview
Processing large-scale interaction data requires efficient distributed computing. This project leverages PySpark to clean, merge, and analyze over **1.13 Million user interaction records** alongside a metadata repository of **230,000+ unique recipes**. 

The goal was to engineer a robust data pipeline capable of aggregating rating distributions, evaluating category-level performance, and generating tag-based recipe recommendations.

## Key Features & Technical Highlights

 **Scalable Data Ingestion:** Processed large CSV files (`RAW_interactions.csv` & `RAW_recipes.csv`) using PySpark’s distributed `DataFrameReader` with options for `multiLine` text parsing and schema inference.
 **Resilient Data Cleaning & Type Casting:** Used `try_cast` and `fillna()` routines to handle malformed string fields, safely casting columns to `integer` and `float` types without crashing execution.
 **Relational Data Merging:** Combined interaction logs with recipe metadata using optimized **Left Joins** on `recipe_id` to preserve full user rating history.
 **Category Performance Analysis:** Evaluated average ratings across tag categories, identifying top-performing culinary themes (e.g., *eggs-dairy*, *prepared-potatoes*, *memorial-day*) scoring between 4.78 and 4.93 out of 5.0.
 **Interactive Recommendation Logic:** Implemented similarity filtering functions (`suggest_by_tag` & `recommend_similar_in_tag`) to allow dynamic recipe discovery.

## Dataset Schema

 **Interactions (`RAW_interactions.csv`):** 1.13M+ records containing `user_id`, `recipe_id`, `date`, `rating`, and `review`.
 **Recipes (`RAW_recipes.csv`):** 230K+ records containing `id`, `name`, `tags`, and ingredients metadata.

##  Future Enhancements

 **Collaborative Filtering:** Implement PySpark’s **ALS (Alternating Least Squares)** machine learning algorithm for personalized user-level recommendations.
 **Weighted Rating System:** Incorporate Bayesian average rating calculations to adjust for niche recipes with low review counts.

* **Collaborative Filtering:** Implement PySpark’s **ALS (Alternating Least Squares)** machine learning algorithm for personalized user-level recommendations.
* **Weighted Rating System:** Incorporate Bayesian average rating calculations to adjust for niche recipes with low review counts.
