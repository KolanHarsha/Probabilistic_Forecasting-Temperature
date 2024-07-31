# Probabilistic_Forecasting-Temperature

## **Kaggle Community Challenge 04/02/2024-07/21/2024** 

https://www.kaggle.com/competitions/probabilistic-forecasting-i-temperature

This project provides a solution to the Kaggle open community challenge on probabilistic temperature forecasting, which entails predicting the likelihood of various potential future temperatures rather than offering a single deterministic forecast. The proposed methodology employs an ensemble of models, combining traditional time series models—Holt-Winters + ARIMA(9,1,0) for the residuals to generate initial forecasts, and machine learning models—LightGBM used to produce the final forecast along with a range of possible temperature outcomes, each with an associated probability. This reflects the inherent uncertainty in weather predictions. The proposed solution achieved a Continuous Ranked Probability Score (CRPS) of 1.2035, securing the 10th position on the final leaderboard as part of Team Naive Forecasters.

## Dataset
There are 64,320 rows of training data spanning from 2016-07-01 to 2018-05-01. There are 5,360 rows of data in the test dataset, spanning from 2018-05-02 to 2018-06-26. The data consists of a time-stamp and 6 anonymized features. The target is the Temperature column.
The temperature is recorded once in 15 minutes i.e. 96 times/day.

## **Methodology**
### **Exploratory Data-Analysis**
![image](https://github.com/user-attachments/assets/c91aa074-fc12-47fa-b4fa-e8e4b2fce503)

The auto-correlation chart for 96 lags reveals that the temperature at all lags is significantly above the horizontal threshold (well above zero). Consequently, we will generate 96 time-lagged temperature features in our approach. Additionally, we will create cosine and sine features to capture cyclic patterns.

#### **HeatMap**
![image](https://github.com/user-attachments/assets/11f01759-8e04-48d5-94d5-f95779a05c70)

### **WorkFlow**

#### **1. Holtwinter's + ARIMA(9,1,0)**

![image](https://github.com/user-attachments/assets/98e8cdfb-1fba-4eee-9c53-cc3df5f8f5bb)

#### **2. LightGBM**

![image](https://github.com/user-attachments/assets/afc9e851-8c05-4b04-986b-79dc1da08539)

### **Performance of Validation Data**

The Continuous Ranked Probability Score (CRPS) on validation data using the above workflow is 0.25934600174955524

#### **Coverage-Report**
![image](https://github.com/user-attachments/assets/ffda5762-cb3e-44ae-ba2b-66e6bb09b234)

The below figure shows median prediction, the target and the quantiles (shown as prediction intervals) for the validation data:

![image](https://github.com/user-attachments/assets/b7bfa8c6-9495-4d5b-915e-434bd4f1acd6)

Examining the coverage report, the ensemble model has met all the coverage criteria for the validation data. Therefore, the model was retrained using the entire training dataset and then used to perform forecasting on the test data. The Continuous Ranked Probability Score (CRPS) for the test data is 1.2035.
## **Contributors**
- Sai Harsha Vardhan Reddy, Kolan- skolan@horizon.csueastbay.edu, harsha62334@gmail.com

- Veera Venkata Sai Kalyan, Kaparaju- vkaparaju@horizon.csueastbay.edu, kvvsaikalyan01@gmail.com

Thanks for reading!
