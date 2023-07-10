![Readme header image](https://i.imgur.com/fgRuUwz.png)


## :speech_balloon: Intro

This repository contains our **work performed for the Capstone Project of the MBD-PT January 2022**. Here, you will find several notebooks performing detailed analysis of the data, identification of Market Drivers, segmentation of stores, predictions of future sales and design of appropriate promotional strategies to extract the most value upon Beer sales in Spain, having data for years 2021 and 2022. The **data** used has been provided by Circana and contains beer sales from January 2021 to March 2023.

## :rocket: How to use this repository

Here, you'll find a collection of notebooks, along with three folders: datasets, images, and data_checkpoints.

### Notebooks
The notebooks provided in the main branch have been previously run, as they contain some computationally intensive code snippets that take a significant amount of time to complete. There are several notebooks covering different aspects, and we'll delve deeper into the code in the following sections.

### Datasets
The datasets folder contains various data files, including the data provided by Circana and our master dataset, named `circana_data.csv`. The master dataset has been created by preparing and merging the provided data with additional data obtained from external sources.

### Data Checkpoints
The data_checkpoints folder contains CSV files with the results of applying different algorithms (depending on the specific part being executed). Given the computational and time-intensive nature of the code, the results are stored as checkpoints. These checkpoints can be easily extracted and utilized in other tools, such as business intelligence (BI) platforms.

### Images
The images folder houses various types of images. Some images are used as inputs in our notebooks, while others are generated within the notebooks as graphs. For the sake of reducing the notebook size, the graph images are stored in HTML format. This format enables efficient storage while preserving the visual representations of the graphs. This specific approach is implemented in part 5, which focuses on the promotion strategy.

---

Feel free to explore the notebooks, leverage the provided datasets, utilize the stored results, and examine the images to gain a comprehensive understanding of the project. Our **recommendation** is to first check the actual output of each notebook instead of running all of them. Then, you can go through the data_checkpoints or images to gain a more complete view of the results.
You can also clone the repository and then execute each of the notebooks, starting from part 1. As we are not changing the input data, we will have the same results in the different notebooks. If new data is added (increasing, in example, the time extension, the notebooks could be run against this new data, if the structure of it is not modified)

## :package: Notebooks introduction

The overall code is structured in 5 parts, each of them included in a different notebook. In the current section we would explain the contents of each of the notebooks, as well as the approach followed by the team, giving an orientation and simplifying search of specific contents.

### Part 1: Descriptive analytics

On this part we will start by preparing the provided data (sales, dictionary, climate/weather, promotions and projections) and we will bring data from external sources (population, national and regional holiddays and football matches). Once having a cohesive dataset, we start an EDA which covers, in detail, sales evolution through time, sales per store, sales per product, weather correlation with sales, analysis by province and price elasticity by product.
Finally, we have obtained a consolidated dataset for sales and promotions, that will be used in the next stages.
The work on this notebook is mainly formed by visualizations plotted with sns or matplotlib.

Please, find here the notebook: [Part 1 - Descriptive Analytics](Part_1-Descriptive_Analytics.ipynb)

### Part 2: Applying regression for finding the drivers of beer sales

We have already identified some drivers through the performance of Part 1. At this point, we want to increase our understanding with a more Machine Learning approach. For that, we will apply different regression type models (Linear Regression, Random Forest and XGBoost) to then analyze the feature importance on the model which is performing better. Our target variable for those models will be sales in value. We will compare the feature importance of the best performing model for each of the top 3 manufacturers in terms of sales.

Please, find here the notebook: [Part 2 - Regression Market Drivers](Part_2-Regression_market_drivers.ipynb)

### Part 3: Clustering: a new approach on stores segmentation

One of the challenges presented by the client is to provide a new way of classifying and segmenting beer stores in Spain, instead of the conventional method, which revolves on store type and size. The approach followed consists on a traditional machine learning pipeline, start by preparing data, applying feature engineering (taking into consideration the previously identified market drivers) and then applying a mini-batch Kmeans algorithm, providing a visualization of the clusters found.

Please, find here the notebook: [Part 3 - Clustering Store Segmentation](Part_3-Clustering_store_segmentation.ipynb)

### Part 4: Forecasting. Anticipating to be ahead

The client has asked for the predictions of sales, by segment and manufacturer, for all 2023 and 2024. Here, the work has been structured into 2 different notebooks, the first one comprending predictions for sales in volume and the second one with predictions for sales in value (which is bringing price evolution into the equation). The approach followed has been the same in both notebooks. We have started with an EDA focused on sales forecasting. Then, we have, first for each segment, and then for each manufacturer, in a separate way, apply different forecasting models: autoarima, autoarima with hyperparameter tuning, LightGBM and LightGBM with hyperparameter tuning. We have picked the best model and we have made predictions short-term (4 weeks ahead) and long-term (covering the required period). We have built an additional LightGBM model which much more granularity, introducing stores inside our models, as it can be useful for client's resource allocation. Finally, we have built our best model in a combined approach for segments and manufacturers, getting those predictions stored in csv files. 
It is worth mentioning that we are working with 116 weeks of data, trying to predict 94 weeks, so our predictions are not going to be really accurate long term. We strongly recommend to use the models in the short term forecasting and enrich the available data until applying for long-term.

Please, find here the notebook for volume: [Part 4.1 - Demand Volume Forecasting](Part_4.1-Demand_Volume_Forecasting.ipynb)
and the notebook for value: [Part 4.2 - Demand Value Forecasting](Part_4.2-Demand_Value_Forecasting.ipynb)

### Part 5: Creating additional value: Promotion Strategy

As a result of all the work performed and already collected in the different notebooks, we have found that the company can enhance its promotion strategy, which will increase the potentail benefit achieve. This is trying to be an innovative approach that requires creativity as some of the needed data for creating a really strong strategy is not present, but we have been able to deal with it successfully. In the notebook, we started by applying some EDA focus on promotions. We have tried to unfold percentage of sales under promotions, types of promotions, duration of promotions and impact on volume. 
Once having that, we have computed the promotion effectiveness backward-looking. For that, we have need to calculate sales uplift as well and the main drivers of those uplifts. For that, we have followed the machine learning pipeline, preparing data, feature engineering, correlation analysis and performing the model (XGBoost). With that, we have been able to identify the key variables that are causing that sales uplift to, afterwards, deep dive on each of them, as well as the impact of value destroyers in the promotion effectiveness.

Please, find here the notebook: [Part 5 - Promotion Strategy](Part_5-Promotion_Strategy.ipynb)




## :penguin: Authors

**Heba Aahed Mushtaha**
- Email : heba.mushtaha@student.ie.edu 
- Github : https://github.com/hebamushtaha

**Salma Elguendy**
- Email : salma.elguendy@student.ie.edu 
- Github : https://github.com/salmaelguendy

**Diana Fernandez**
- Email : dianaf@student.ie.edu
- Github : https://github.com/dianisley

**Alfonso Ferrándiz Hervella**
- Email : alfonsofhervella@student.ie.edu 
- Github : https://github.com/fonsofhervella

**Juan Francisco Horrillo**
- Email : juan.horrillo@student.ie.edu 
- Github : https://github.com/juanhorrillo

**Dareen Shaheen**
- Email : dareen.shaheen@student.ie.edu
- Github : https://github.com/DareenShaheen




[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)

