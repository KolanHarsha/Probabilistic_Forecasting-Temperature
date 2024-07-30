# Probabilistic_Forecasting-Temperature

## **Kaggle Community Challenge 04/02/2024-07/21/2024** 

https://www.kaggle.com/competitions/probabilistic-forecasting-i-temperature

This project provides a solution to the Kaggle open community challenge on probabilistic temperature forecasting, which entails predicting the likelihood of various potential future temperatures rather than offering a single deterministic forecast. The proposed methodology employs an ensemble of models, combining traditional time series models—Holt-Winters + ARIMA(9,1,0) for the residuals to generate initial forecasts, and machine learning models—LightGBM used to produce the final forecast along with a range of possible temperature outcomes, each with an associated probability. This reflects the inherent uncertainty in weather predictions. The proposed solution achieved a Continuous Ranked Probability Score (CRPS) of 1.2035, securing the 10th position on the final leaderboard as part of Team Naive Forecasters.

## **WorkFlow**

### **1. Holtwinter's + ARIMA(9,1,0)**

![image](https://github.com/user-attachments/assets/98e8cdfb-1fba-4eee-9c53-cc3df5f8f5bb)

### **2. LightGBM**

![image](https://github.com/user-attachments/assets/afc9e851-8c05-4b04-986b-79dc1da08539)

## **Methodology**
### **Exploratory Data-Analysis**
![image](https://github.com/user-attachments/assets/c91aa074-fc12-47fa-b4fa-e8e4b2fce503)

The auto-correlation chart shows that the 
