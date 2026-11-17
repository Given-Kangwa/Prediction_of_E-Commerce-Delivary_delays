2. Project progress report
:::writing{variant="document" id="73182"}
# PROJECT PROGRESS REPORT

**Project Title:** Predicting E-Commerce Delivery Delays Using Data Mining Techniques  
**Dataset:** Brazilian E-Commerce Public Dataset by Olist  
**Current Stage:** Data Understanding, Integration and Exploratory Data Analysis  
**Reporting Date:** 17 November 2026

## 1. Project Overview

The project aims to develop a Decision Tree classification model to predict whether an e-commerce order will be delivered on time or delayed. The project uses the Brazilian E-Commerce Public Dataset by Olist, obtained through KaggleHub.

The target variable, `delivery_status`, is encoded as:
- 0 – On Time
- 1 – Delayed

An order is classified as delayed when its actual delivery date is later than its estimated delivery date.

## 2. Work Completed

### 2.1 Dataset Acquisition and Understanding

Successfully downloaded and inspected the Olist dataset using KaggleHub. The dataset contains nine CSV files covering orders, customers, products, sellers, payments, order items, reviews, geolocation and product category translations.

The initial inspection identified the structure, dimensions and missing values of the main datasets.

### 2.2 Data Cleaning and Target Construction

Inspected order statuses and delivery dates to identify eligible observations.

- Retained delivered orders with valid actual delivery dates.
- Excluded cancelled, unavailable and other non-delivered orders from the binary classification task.
- Created the binary target variable `delivery_status`.
- Obtained 96,470 eligible orders.

The resulting target distribution is:
- On Time: 88,644 orders (91.89%).
- Delayed: 7,826 orders (8.11%).

This revealed a significant class imbalance that will be considered during model evaluation.

### 2.3 Data Integration and Preprocessing

Aggregated order item records and payment records by `order_id` to prevent duplicate orders during integration.

Integrated the following datasets:
- Orders
- Customers
- Order items
- Payments

The resulting dataset contains 96,470 rows and 23 columns.

Validation confirmed:
- Zero duplicate order IDs.
- Zero remaining missing values after treatment.
- One order with missing payment information was retained using an estimated payment amount calculated from product price and freight charges. This imputation will be documented.

Derived additional temporal features, including purchase year, month, day, day of the week and purchase hour, as well as the estimated delivery window.

### 2.4 Exploratory Data Analysis

Initial descriptive statistics and visualizations have been completed.

The following findings were observed:

**Delivery status distribution:** Approximately 91.89% of eligible orders were delivered on time, while 8.11% were delayed.

**Monthly delivery delays:** March recorded the highest delay rate at 17.15%, followed by November at 14.31% and February at 13.41%. June recorded the lowest rate at 2.21%.

**Weekday delivery delays:** Monday had the highest apparent delay rate, at approximately 9%, while Sunday had the lowest, at approximately 7.5%. Differences across weekdays were relatively small.

**Freight charges:** Delayed orders showed a slightly higher median freight charge than on-time orders, although the distributions overlapped considerably.

**Descriptive statistics:** Product prices, freight charges and payment amounts showed evidence of right-skewed distributions and potentially extreme values requiring further investigation.

## 3. Current Challenges and Considerations

The target variable is imbalanced, meaning that accuracy alone may not adequately measure model performance.

Potential outliers have also been identified in financial and delivery-window variables.

Additionally, predictor selection must prevent data leakage. Only information genuinely available at the defined prediction point should be used as model input.

## 4. Next Steps

The remaining work will focus on:

1. Completing exploratory analysis of customer locations, order values and purchase timing.
2. Investigating outliers, skewness and relationships between variables.
3. Conducting confounding-variable analysis.
4. Applying an appropriate mixed-attribute similarity measure, such as Gower distance, with a worked example.
5. Completing preprocessing, including missing-value treatment, outlier handling and normalization where appropriate.
6. Establishing a baseline and training a Decision Tree classifier.
7. Evaluating the model using a confusion matrix, precision, recall, F1-score and accuracy.
8. Discussing practical implications, ethical considerations and scalability.

## 5. Current Status

The dataset has been successfully acquired, inspected, cleaned, integrated and validated. Initial exploratory analysis has also been completed, revealing class imbalance and potential relationships between purchase timing, freight charges and delivery delays.

The project is currently progressing through the exploratory data analysis stage, with preprocessing and model development remaining.

**Conclusion:** The foundational data preparation work has been completed successfully. The next priority is to deepen the exploratory analysis and establish a reliable feature set before training the Decision Tree model.
:::