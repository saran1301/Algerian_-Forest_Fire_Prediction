# Forest Fire Prediction: Analyzing and Forecasting Fire Risk

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Data Cleaning](#data-cleaning)
4. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
5. [Feature Engineering](#feature-engineering)
6. [Feature Scaling](#feature-scaling)
7. [Results and Insights](#results-and-insights)
8. [Conclusion](#conclusion)
9. [Future Scope](#future-scope)

---

## Introduction
Forest fires are a major environmental concern, causing extensive damage to biodiversity, property, and human lives. This project leverages machine learning techniques to predict fire severity using meteorological and forest-related indices. The goal is to provide actionable insights that can help forest management teams preemptively allocate resources and mitigate fire risks.

---

## Dataset Overview
The dataset comprises **244 instances** of weather data and forest fire observations collected from two Algerian regions: **Bejaia** and **Sidi Bel Abbes**. Key attributes include:

- **Weather Features**: Temperature, Relative Humidity, Wind Speed, and Rainfall.
- **Fire Weather Index (FWI)**: Indicators like Fine Fuel Moisture Code (FFMC), Duff Moisture Code (DMC), Drought Code (DC), and Initial Spread Index (ISI).
- **Outcome**: Binary classes representing fire occurrence (`fire` and `not fire`).

---

## Data Cleaning
To ensure data quality, we performed the following steps:
1. **Handling Missing Values**: Removed rows with missing or anomalous data points.
2. **Region Encoding**: Added a new `Region` column for classification (`0` for Bejaia and `1` for Sidi Bel Abbes).
3. **Column Renaming and Type Conversion**: Standardized column names and converted data types for consistency.
4. **Header Removal**: Eliminated redundant headers embedded within the dataset.

### Final Dataset
The cleaned dataset includes **243 rows** and **13 columns** with no null values.

---

## Exploratory Data Analysis (EDA)
EDA revealed critical patterns in fire occurrence and its relationship with weather conditions:

1. **Fire Distribution**:
   - **Pie Chart**: A balanced distribution of fire (`56.5%`) and no-fire (`43.5%`) cases.
   - **Classes Visualization**: ![image](https://github.com/saran1301/Algerian_Forest_Fire_Prediction/blob/9812c900bf6277110830688456d1af00ee27fd3b/src/Visualisations/Pie%20Chart%20of%20Classes.png)

2. **Correlation Analysis**:
   - Strong correlations observed between `FWI`, `DC`, and `DMC`.
   - **Plots** : 
![image](https://github.com/saran1301/Algerian_Forest_Fire_Prediction/blob/cc816b3af747906bb15b5b231ceef1c3e4da4dfb/src/Visualisations/Correlation_Plots.png)

3. **Monthly Trends**:
   - August and September recorded the highest fire occurrences across both regions.
   - **Monthly Fire Analysis**: ![image](https://github.com/saran1301/Algerian_Forest_Fire_Prediction/blob/9812c900bf6277110830688456d1af00ee27fd3b/src/Visualisations/Fire%20Analysis%20of%20Sidi-Bel%20Region.png)
     ![image](https://github.com/saran1301/Algerian_Forest_Fire_Prediction/blob/9812c900bf6277110830688456d1af00ee27fd3b/src/Visualisations/Fire%20analysis%20of%20Bejaia%20Region.png)


### Insights:
- The `FWI` index serves as a reliable predictor for fire severity.
- Seasonal trends indicate increased fire activity during dry months.

---

## Feature Engineering
1. **Target Variable**:
   - Fire severity (`Classes`) encoded as binary values (`1` for fire, `0` for no fire).
2. **Dimensionality Reduction**:
   - Removed highly correlated features (`>0.87 correlation threshold`) to mitigate multicollinearity.

---

## Feature Scaling:
- Standardized features to improve model convergence and accuracy.
- **Scaling Visualization**: ![image](https://github.com/saran1301/Algerian_Forest_Fire_Prediction/blob/9812c900bf6277110830688456d1af00ee27fd3b/src/Visualisations/Feature%20Scaling.png)

---

## Results and Insights
1. **Key Metrics**:
   - **MAE**:
      - Linear Regression : 32.86525174026157
      - Lasso Regression : 65.25587759909162
      - Ridge Regression : 32.8973410601745
      - ElasticNet Regression : 1.8915134363047041
      - Lasso CV : **0.68**69133919948954
      - Ridge Regression CV : 0.856690888884327
      - ElasticNet CV : 0.7295307419548667
   - **R²**: 
      - Linear Regression : -40.88439899735745
      - Lasso Regression : -118.23635392199061
      - Ridge Regression : -41.19757581061491
      - ElasticNet Regression : 0.8731354681001338
      - Lasso CV : **0.97**37146046555863
      - Ridge Regression CV : 0.9729928114396739
      - ElasticNet CV : 0.9789324233433637
2. **Model Comparison**:
   - **Lasso CV** emerged as the best model with minimal error and high generalizability.

3. **Insights**:
   - Regions with high `FWI` values require proactive monitoring during dry seasons.
   - Resource allocation can be optimized by focusing on August and September, as identified by the monthly analysis.

---

## Conclusion
This project successfully demonstrates the use of machine learning to predict fire severity in forest regions. By identifying high-risk periods and regions, forest management teams can take preemptive measures to minimize losses.

---

## Future Scope
1. **Data Augmentation**:
   - Incorporate additional weather features like atmospheric pressure or soil moisture for improved accuracy.
2. **Geospatial Analysis**:
   - Map high-risk areas using GIS tools.
3. **Real-Time Predictions**:
   - Deploy models on IoT-enabled weather stations for dynamic monitoring.
