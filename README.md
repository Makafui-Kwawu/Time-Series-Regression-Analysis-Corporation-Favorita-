# 💼 Time Series Sales Machine Learning Prediction Project




In this machine learning regression project, the goal is to develop a model that can accurately predict the value of the dependent variable based on the values of the independent variables. The model is developed by training the algorithm on a dataset of historical data. The algorithm learns from the data and identifies patterns that can be used to predict the value of the dependent variable.

Once the model is trained, it can be used to predict the value of the dependent variable for new data points. This can be used to make decisions about future outcomes, such as predicting sales, forecasting demand, or assessing risk.

## Project Overview

This project follows the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework to explore and analyze the sales data. In this project, we'll predict store sales on data from **Corporation Favorita**, a large Ecuadorian-based grocery retailer.

Specifically, we are to build a model that more accurately predicts the unit sales for thousands of items sold at different Favorita stores.


## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Project Structure](#project-structure)
- [Data Dictionary](#data-dictionary)
- [Project Highlights](#project-highlights)
- [Summary](#summary)
- [Hypothesis Investigated](#hypothesis-investigated)
  - [Results](#results)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Model Selection](#model-selection)
- [Recommendations](#recommendations)
- [Getting Started](#getting-started)
- [License](#license)
- [Author](#author)

## Project Structure📂

- `code/`: Contains the dataset used for analysis and the Jupyter notebook detailing the data exploration, preprocessing, and model building steps.
- `article/`: Holds project-related article.
- `LICENSE`: Project license.
- `README.md`: Project overview, links, highlights, and information.

## Data Dictionary

| **Dataset** | **Description** |
|------------|-----------------|
| train.csv  | Training data containing time series of features store_nbr, family, and onpromotion, as well as the target sales. |
|            | - `store_nbr`: Identifies the store where the products are sold. |
|            | - `family`: Identifies the type of product sold. |
|            | - `sales`: Total sales for a product family at a specific store on a given date (can be fractional). |
|            | - `onpromotion`: Total number of items in a product family that were being promoted at a store on a given date. |
| test.csv   | Test data with the same features as the training data. Predict target sales for these dates. |
| transaction.csv | Contains date, store_nbr, and transactions made on specific dates. |
| sample_submission.csv | Sample submission file in the correct format. |
| stores.csv | Store metadata, including city, state, type, and cluster. |
|            | - `cluster`: Grouping of similar stores. |
| oil.csv    | Daily oil price data, including values during both the train and test data timeframes. |
| holidays_events.csv | Holidays and events data, with metadata. |


# Project Highlights🚀

- Employed a holistic approach, embracing the CRISP-DM framework, to gain a deep understanding of retail dynamics.
- Mined invaluable insights from extensive exploratory data analysis, unveiling hidden trends and patterns within the dataset.
- Engineered advanced predictive models, featuring the formidable XGBoost algorithm, to forecast sales with unprecedented accuracy.
- Implemented rigorous hyperparameter tuning, unlocking the full potential of our models and achieving unparalleled predictive performance.
- Crafted a compelling and informative article, sharing the project's compelling journey, groundbreaking results, and its potential to reshape the future of retail forecasting.

## Summary

| Code | Name                                     |                                             Published Article                                              |                                                                                                                                                    Deployed Dashboard |
| ---- | ---------------------------------------- | :--------------------------------------------------------------------------------------------------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| LP 3 | Sales Time Series Prediction | [Read Article](https://medium.com/@sm.kwawu/time-series-regression-analysis-corporation-favorita-9bf8e518a352) | [View Dashboard](https://app.powerbi.com/groups/me/reports/ec366f41-305d-441b-a829-fbe4ab7ab550/152078cc5237c0300935?experience=power-bi) |

## Hypothesis Investigated

**Null Hypothesis (H0)** : Promotional activities do not have a significant impact on sales.

**Alternate Hypothesis (H1)** : Promotional activities have a significant impact on sales.

## Rationale

The rationale for testing these hypotheses is to determine whether there is empirical evidence to support the idea that promotions have a meaningful impact on sales in supermarkets.

By testing these hypotheses and examining the correlation between promotions and sales, businesses can gain valuable insights into the dynamics of supermarket sales and make evidence-based decisions regarding their promotional strategies.


### Results

| Test Conducted               | scipy.stats.ttest_ind     | P-Value                |
| ---------------------------- | ------------------ | ---------------------- |
| Independent Samples T - Test | 193.83 | 0.0000 |

In conclusion, the scipy.stats.ttest_ind calculated between the number of products under promotion (as indicated by the "onpromotion" column) and sales in supermarkets is approximately 193.83. The corresponding p-value obtained from the  analysis is very close to zero (P-value: 0.0000). Based on the results of this analysis, we reject the null hypothesis.

There is a statistically significant positive relationship (193.83) between the number of products under promotion and sales in supermarkets. This suggests that promotions have a significant influence on sales, and as the number of products under promotion increases, sales tend to increase as well.



## Exploratory Data Analysis (EDA)📊


A snapshot of the conducted exploratory data analysis, aimed at addressing pivotal business inquiries during the analysis process.

| ![storesbytype](https://github.com/snyamson/LP3-Super-Store-Time-Series-Forecasting/assets/58486437/dae0298b-2477-4772-a650-31a74b839266)         | ![storesbystate](https://github.com/snyamson/LP3-Super-Store-Time-Series-Forecasting/assets/58486437/549cf603-45e6-43a6-9304-760c36c5f324)       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![oil trend](https://github.com/snyamson/LP3-Super-Store-Time-Series-Forecasting/assets/58486437/468f4fe4-84d4-4e7a-a58a-d85739646a49) | ![newplot](https://github.com/snyamson/LP3-Super-Store-Time-Series-Forecasting/assets/58486437/79b272b7-319c-48de-901c-467ca57b9a78) |

## Model Selection


![Model](https://github.com/Makafui-Kwawu/Time-Series-Regression-Analysis-Corporation_Favorita/assets/160020850/02e79d25-7683-4e5f-86c1-4ade6ea44ae4)

After carefully assessing the performance of our models using key evaluation metrics, it is evident that the XGBoost model stands out as the most effective choice for our dataset. The RMSLE (Root Mean Squared Logarithmic Error) serves as a crucial indicator, and the XGBoost model achieved the lowest RMSLE of 0.007 among all models evaluated. This indicates that the XGBoost model provides the most accurate and precise predictions when compared to ARIMA, SARIMA, and Linear Regression models.

Therefore, for this specific forecasting task, we are adopting the XGBoost model for its superior predictive accuracy.


## Recommendations

1. **Promotion Optimization:** Based on the analysis of the impact of promotions on sales, consider optimizing promotion strategies. Identify which types of promotions (e.g., discounts, BOGO offers) have the most significant influence on sales and tailor promotional campaigns accordingly. By focusing promotional efforts on what truly drives sales, you can maximize the return on investment.

2. **Focus on High-Performing Cities**: The top-performing city, "Quito," stands out with the highest sales. It's essential to allocate additional resources and marketing efforts to maintain and potentially increase sales in Quito. Additionally, cities like "Guayaquil," "Cuenca," "Ambato," and "Santo Domingo" have also shown strong sales performance. Consider developing city-specific strategies to capitalize on these markets.

3. **Cluster-Centric Approach**: The analysis reveals that certain clusters, such as "Cluster 14," "Cluster 6," and "Cluster 8," exhibit remarkable sales figures. Invest in understanding the unique characteristics of these clusters and tailor product assortments, promotions, and inventory management strategies to maximize sales potential in these areas.

4. **Cross-Analysis Opportunities**: Explore opportunities to combine the strengths of high-performing cities, clusters, store types, and states. For example, consider aligning promotions with holidays and events in top cities and clusters to maximize sales impact. Additionally, assess whether specific store types thrive in particular cities or clusters, and use this information to refine expansion plans.

## Getting Started🏁

1. Clone this repository: `[git clone https://github.com/Makafui-Kwawu/Time-Series-Regression-Analysis-Corporation_Favorita.git]`
2. Navigate to the project directory: `LP3-Super-Store-Time-Series-Forecasting`
3. Explore the Jupyter notebooks for detailed steps and code execution.
4. Read the published article for a comprehensive understanding of the project.

## License📜

This project is licensed under the [MIT License](LICENSE).

## Author✍️

Success Makafui Kwawu

Connect with me on LinkedIn: [LinkedIn Profile](https://linkedin.com/in/smkwawu/)

---

Feel free to star ⭐ this repository if you find it helpful!
