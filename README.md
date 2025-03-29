# Airbnb Price Prediction and Market Analysis

## Project Overview

This project focuses on predicting Airbnb listing prices and extracting valuable insights into the Airbnb market using a substantial dataset of over 230,000 listings. By employing machine learning techniques, specifically regression modeling, and conducting exploratory data analysis (EDA), the aim is to understand the key factors influencing listing prices and uncover underlying market dynamics. This information can be beneficial for Airbnb hosts looking to optimize their pricing strategies and for potential guests seeking to understand pricing trends.

## Dataset

The dataset used in this project contains detailed information about Airbnb listings, encompassing 18 features. The main features that are used include:

**Numerical Features:**

* `latitude`: Geographic latitude of the listing.
* `longitude`: Geographic longitude of the listing.
* `minimum_nights`: The minimum number of nights a guest can book the listing.
* `number_of_reviews`: The total number of reviews the listing has received.
* `reviews_per_month`: The average number of reviews the listing receives per month.
* `calculated_host_listings_count`: The number of listings the host has in the current geography.
* `availability_365`: The number of days the listing is available for booking within a year.
* `number_of_reviews_ltm`: The number of reviews the listing has received in the last twelve months.

**Categorical Features:**

* `room_type`: The type of room offered (e.g., Entire home/apt, Private room, Shared room, Hotel room).
* `neighbourhood`: The specific neighborhood the listing is located in.
* `city`: The city in which the listing is located.

## Methodology

The project followed a structured approach:

1.  **Data Loading and Exploration:** Loading the dataset and performing initial exploratory analysis to understand its structure, identify missing values, and get a feel for the data.
2.  **Data Preprocessing:**
    * Handling missing values appropriately.
    * Encoding categorical features using techniques like one-hot encoding to make them suitable for machine learning models.
    * Potentially applying transformations to numerical features (e.g., log transformation to price) to address skewness.
3.  **Exploratory Data Analysis (EDA):**
    * Visualizing the distribution of key features (e.g., price, minimum\_nights, reviews).
    * Analyzing the distribution of room types across different locations using scatter plots.
    * Examining correlations between features using heatmaps and pair plots.
    * Investigating review patterns based on room type and neighborhood.
4.  **Model Development:**
    * Splitting the data into training and testing sets to evaluate model performance on unseen data.
    * Developing regression models to predict the `price` of Airbnb listings.
    * Experimenting with different regression algorithms, including:
        * Linear Regression
        * Decision Tree Regressor
        * Random Forest Regressor
5.  **Model Evaluation:**
    * Evaluating the performance of each model using appropriate regression metrics such as:
        * R² Score (Coefficient of Determination)
        * Mean Absolute Error (MAE)
        * Root Mean Squared Error (RMSE)
    * Comparing the performance of the different models to identify the most effective one.

## Key Findings & Insights

* **Price Prediction:** The **Random Forest Regressor** demonstrated the best performance in predicting Airbnb listing prices, achieving an R² score of approximately 0.605 on the test data.
* **Significant Price Influencers:** Features such as `minimum_nights`, `number_of_reviews`, `reviews_per_month`, and `calculated_host_listings_count` were found to have a significant impact on listing prices.
* **Review Distribution Patterns:** The distribution of reviews per month varied considerably across different room types and neighborhoods. "Entire home/apt" and "Private room" listings in popular areas like Hollywood and Bedford-Stuyvesant tended to receive a higher volume of reviews.
* **Minimum Stay Preferences:** The majority of listings had short minimum stay requirements (1-2 nights), with a notable concentration also at 30 nights. Longer minimum stay durations were negatively correlated with the number of reviews received.
* **Geographic Listing Distribution:** Airbnb listings were not uniformly distributed geographically, showing distinct clusters in certain areas. "Entire home/apt" and "Private room" were the dominant room types within these clusters.
* **Skewness in Price:** The price distribution was found to be right-skewed, with a large number of listings at lower prices and a long tail of more expensive listings. A log transformation was applied to address this.

## Model Performance

The performance of the trained regression models was as follows:

|         Model        | R² Score |    MAE   |   RMSE  |
|:--------------------:|:--------:|:--------:|:-------:|
|  Linear Regression   |  0.432   |  0.416   |  0.529  |
|     Decision Tree    |  0.241   |  0.439   |  0.612  |
|     Random Forest    |  0.605   |  0.330   |  0.442  |



## Potential Applications

The insights and the predictive model developed in this project can be used for various applications:

* **Dynamic Pricing for Hosts:** Airbnb hosts can leverage the model to understand how different factors influence their listing's price and potentially implement dynamic pricing strategies to optimize revenue.
* **Informed Decision Making for Guests:** Potential guests can gain a better understanding of pricing trends in different areas and for various listing types, allowing them to make more informed decisions when booking accommodations.
* **Market Analysis:** The findings can provide valuable insights into the overall Airbnb market, helping to identify pricing trends, popular areas, and the impact of different listing characteristics.

## Future Work

Potential areas for future work include:

* **Hyperparameter Tuning:** Optimizing the hyperparameters of the best-performing model (e.g., Random Forest) using techniques like GridSearchCV or RandomizedSearchCV.
* **Feature Engineering:** Creating new features from existing ones or incorporating external data sources (e.g., local amenities, seasonality, public transportation data) to potentially improve model accuracy.
* **Exploring Advanced Models:** Investigating the performance of more advanced machine learning models, such as gradient boosting algorithms or neural networks.
* **Deployment:** Deploying the trained model as an API or a web application to make it accessible for practical use.

## Repository Contents

* `notebooks/`: Contains Jupyter Notebooks for data exploration, preprocessing, model training, and evaluation.
* `README.md`: This file, providing an overview of the project.


## Contributing

Contributions to this project are welcome. Please feel free to submit pull requests or open issues for any suggestions or improvements.
