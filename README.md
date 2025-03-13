About Dataset
Context
This is a small subset of dataset of Book reviews from Amazon Kindle Store category.

Content
5-core dataset of product reviews from Amazon Kindle Store category from May 1996 - July 2014. Contains total of 982619 entries. Each reviewer has at least 5 reviews and each product has at least 5 reviews in this dataset.
Columns

- asin - ID of the product, like B000FA64PK
- helpful - helpfulness rating of the review - example: 2/3.
- overall - rating of the product.
- reviewText - text of the review (heading).
- reviewTime - time of the review (raw).
- reviewerID - ID of the reviewer, like A3SPTOKDG7WBLN
- reviewerName - name of the reviewer.
- summary - summary of the review (description).
- unixReviewTime - unix timestamp.

Acknowledgements
This dataset is taken from Amazon product data, Julian McAuley, UCSD website. http://jmcauley.ucsd.edu/data/amazon/

License to the data files belong to them.

Inspiration
- Sentiment analysis on reviews.
- Understanding how people rate usefulness of a review/ What factors influence helpfulness of a review.
- Fake reviews/ outliers.
- Best rated product IDs, or similarity between products based on reviews alone (not the best idea ikr).
- Any other interesting analysis




 ## Kindle Review Sentiment Analysis using Word2Vec and XGBoost (Tuned)

# Project Overview

This project performs sentiment analysis on Kindle Reviews using Word2Vec embeddings and an improved XGBoost model with RandomizedSearchCV for hyperparameter tuning.

# Dataset Description

Dataset: Kindle Reviews Dataset

Key Columns: reviewText (text data), overall (rating)

Sentiment Mapping: Ratings ≥ 4 are treated as Positive (1), otherwise Negative (0)

# Project Workflow

# 1. Data Preprocessing

✅ Removal of special characters and numbers✅ Conversion to lowercase✅ Stopword removal✅ Lemmatization for improved word generalization✅ Rare word removal for noise reduction

# 2. Word2Vec Model Training

vector_size=200

window=7

min_count=3

epochs=20

# 3. Feature Extraction

Averaged Word2Vec vectors for each review are used as features.

# 4. Hyperparameter Tuning (XGBoost)

Used RandomizedSearchCV for faster optimization

Key tuned parameters:

n_estimators: [100, 200, 300]

max_depth: [3, 5, 7]

learning_rate: [0.01 – 0.3]

subsample: [0.7, 0.8, 1.0]

colsample_bytree: [0.7, 0.8, 1.0]

# 5. Model Training & Evaluation

Tuned model achieved 80.4% accuracy on the test set.

📈 Results

Model

Accuracy

Baseline Word2Vec

75%

Enhanced Word2Vec (Tuned XGBoost)

80.4%