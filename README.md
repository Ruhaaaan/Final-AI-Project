# Smart Traffic Flow Prediction Using Weather and Historical Data

An intelligent, real-time traffic flow prediction system developed as part of the Machine Learning course. This project combines regression and classification machine learning techniques to forecast traffic volume and status based on historical patterns and real-time meteorological conditions.

---

## 👥 Team & Course Information

| Project Details | Information |
| :--- | :--- |
| **Course** | Machine Learning (Section AM) |
| **Submitted To** | Abdul Samad |
| **Team Members** | • Hassan Ahmed Khan (SP24-BSAI-0038)<br>• Shoaib Jamal (SP24-BSAI-0031)<br>• Ruhaan Reyaz (SP24-BSAI-0046) |

---

## 📌 Problem Statement
Urban traffic congestion is a growing challenge that leads to increased travel delays, heightened pollution levels, and driver stress. Conventional traffic management systems rely heavily on static techniques—such as fixed-interval traffic signals and pre-scheduled transit routes—which fail to adapt to dynamic, real-time changes caused by fluctuating weather conditions, time of day, and sudden local events.

### The Solution
This project introduces a hybrid, data-driven traffic prediction system. By analyzing historical traffic flow alongside real-time weather analytics, the system provides accurate forecasts to assist city authorities in proactive traffic management and help commuters optimize their travel routes.

---

## 🎯 Objectives

* **Primary Objective:** To predict traffic flow with high accuracy by integrating weather conditions and historical traffic data, enabling real-time traffic management and route optimization.
* **Secondary Objectives:**
    * Build a hybrid predictive framework using both **Regression** (volume estimation) and **Classification** (congestion level) techniques.
    * Benchmark and compare the performance of multiple ML architectures (`Linear Regression`, `Logistic Regression`, `Decision Trees`, `Random Forest`, and `LSTM`).
    * Develop a functioning real-time pipeline that ingests current weather data via the **OpenWeather API** and displays immediate traffic predictions.

---

## ⚙️ Methodology

The project implementation lifecycle is split into four distinct phases:

### 1. Data Collection
* **Traffic Data:** Sourced from public datasets and local transportation authorities. Key features include traffic density, vehicle volume, and average speed.
* **Weather Data:** Includes environmental features such as temperature, precipitation (`rain_1h`), snow accumulation (`snow_1h`), humidity, and visibility.
    * *Note: Continual numerical values like temperature, rain, and snow are normalized using `MinMaxScaler`.*

### 2. Data Preprocessing
* **Data Cleaning:** Addressing raw data gaps by eliminating noise, identifying outliers, and handling missing values through robust statistical imputation.
* **Feature Engineering:** Extracting temporal components (hour of the day, day of the week, peak hours) and merging them with the weather indices to build an optimized feature set.

### 3. Model Architecture & Selection
The pipeline utilizes a split modeling strategy:

┌─── Regression (Exact Volume) ───► Linear Regression / LSTM (RNN)
                  │
📊 Predictive Model ──┤
│
└─── Classification (Status)   ───► Logistic Regression / Decision Tree / Random Forest




* **Regression Models (Predicting Exact Volume):**
    * *Linear Regression:* Serves as a fast, highly interpretable baseline.
    * *LSTM (Long Short-Term Memory RNN):* Tailor-made for capturing complex, long-term temporal dependencies in time-series sequences.
* **Classification Models (Predicting Traffic Congestion Status):**
    * *Logistic Regression:* Computes baseline probabilities for discrete traffic classes.
    * *Decision Tree:* Offers an interpretable, rule-based logic structure.
    * *Random Forest:* An ensemble approach that aggregates multiple decision trees to minimize overfitting and maximize classification robustness.

### 4. Deployment
The trained models are bundled into a pipeline integrated with a real-time front-end interface built using **Gradio**. This UI takes user/live inputs and serves instant inference predictions.

---

## 📊 Results & Evaluation

The system successfully processes real-time weather and temporal inputs to output high-fidelity traffic insights.

### Regression Model Performance
* **Metrics Tracked:** Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE).
* **Key Finding:** The **LSTM model** proved to be the most robust architecture for sequence-based forecasting due to its capacity to track historical time dependencies, while Linear Regression provided a lightweight baseline.
* *Visualized via comparative line plots showing Actual vs. Predicted Traffic Volume.*

### Classification Model Performance
* **Metrics Tracked:** Accuracy, Precision, Recall, and F1-Score.
* **Key Finding:** The **Random Forest classifier** significantly outperformed both Logistic Regression and standard Decision Trees when categorizing traffic states (`Low`, `Medium`, `High`).
* *Visualized and verified using Confusion Matrices.*

### Real-Time Live Integration
* The system successfully uses the **OpenWeather API** to pull live regional data, transforming immediate environmental updates into reactive traffic alerts instantly.

---

## 🔮 Conclusion
This project demonstrates how combining weather analytics with deep learning/machine learning models can solve critical urban infrastructure challenges. By blending numerical volume forecasting (`LSTM`) with digestible categorical alerts (`Random Forest`), the platform provides highly actionable insights for both city planners and everyday commuters. 

The optimized, production-ready neural network is saved as a reusable `.h5` model file, paving the way for seamless integration into broader smart-city infrastructures, GPS navigation platforms, and mobile transit applications.
