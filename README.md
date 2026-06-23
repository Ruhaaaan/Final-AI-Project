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
