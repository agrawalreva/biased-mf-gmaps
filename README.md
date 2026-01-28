# Biased MF for Google Maps Rating Prediction | [Full Workbook](https://htmlpreview.github.io/?https://github.com/agrawalreva/biased-mf-gmaps/blob/main/workbook%20copy.html)

This repository implements a personalized rating prediction system for Google Maps reviews using biased matrix factorization (MF) with stochastic gradient descent (SGD). The goal is to predict a user's future rating for a business in California, based on historical review data.

## Dataset

I use the publicly available [Google Maps Reviews dataset (10-core)](https://mcauleylab.ucsd.edu/public_datasets/gdrive/googlelocal/) filtered to California businesses. The 10-core filtering ensures that every user and business has at least 10 interactions, making it suitable for latent factor models.

## Features

- **Preprocessing:** Maps user/item IDs to contiguous indices for matrix factorization.  
- **Exploratory Data Analysis (EDA):** Visualizes rating distribution, long-tail behavior, and temporal trends.  
- **Modeling:**  
  - **Biased MF-SGD:** Captures global, user, and item biases along with latent factors.  
  - **SVD Baseline:** Mean-centered matrix factorization.  
  - **Regression Baselines:** Global mean, user mean, item mean.  
- **Evaluation:**  
  - Regression metrics: RMSE, MAE  
  - Ranking metrics: Precision@K, Recall@K, NDCG@K  
- **Ablation Study:** Compares performance on **head items (popular)** vs **tail items (less popular)** to study long-tail effects.  
- **Error Analysis:** Highlights catastrophic prediction errors for insight into model limitations.  

## Results

- The **Biased MF-SGD** model outperforms baseline methods in RMSE, demonstrating effective learning of latent user/item preferences.  
- Ranking evaluation shows improvements in Precision@K and NDCG@K compared to a popularity-based baseline, highlighting the benefit of personalization.  
- Long-tail items remain challenging due to data sparsity, confirmed by the ablation study.  

## Citation

- McAuley et al., "Image-based recommendations on Google Maps," UCSD Public Datasets.  
- Koren et al., "Matrix Factorization Techniques for Recommender Systems," 2009. 