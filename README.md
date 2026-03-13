# Cohort-17-Smart-Streetlight-Fault-Detection
# SDG Goal :SDG 9 Industry Innovation and Infrastructure
**Description Classify internet of things sensor data from urban lighting systems into operational or faulty states. Evaluate the model using mean time to detect metrics adapted for classification. Fine tune the polling frequency parameters to conserve sensor battery life.**

**Cohort Number:** 17  
**Submission Date:** 13rd March of 2026  

---

## Team Members and Roles

| USN | Name | Role |
| :--- | :--- | :--- |
| 2AV22CS005 <br> 1HK22AI063 <br> 1HK22EC051 | Amruta Suresh Aralelimath <br> Hafeeza Tasneem <br> Hajira Shahanz A | EDA + Data preprocessing |
| 1ST22CS240 <br> 1ST22CS241 <br> 1MV22EC056 <br> 4VM22IS004 | Vasanth Kumar H R <br> Vibhashree R <br> Harshith G K <br> Benaka M | ML Engineer |
| 1HK22AI062 <br> 1GC22CS096 <br> 1EW22IS070 <br> 4AD22EC062 | Zeba Shine <br> Safdar Iqbal <br> Nakshatra S <br> Nayana M B | MTTD+ Polling <br> Frequency Analysis |
| 1DT22IC003 <br> 1GC23CS419 <br> 1GC22CS068 | Akshay S <br> Tasaduque Ullah <br> Mohammed Umar Maniyar | Documentation |
| 1RI22CS108 | Sridhar Y Gowdar | Git Hub Repo |

### Cohort Leaders

| USN | Name | Role |
| :--- | :--- | :--- |
| 1ST22CS240 | Vasanth Kumar HR | President |
| 2AV22CS005 | Amruta Suresh Aralelimath | Vice President |
| 4VM22IS004 | Benaka M | Secretary |
| 1RI22CS108 | Sridhar Y Gowdar | Deputy Secretary |

---

## ABSTRACT
This project focuses on detecting faults in smart streetlight systems using machine learning techniques applied to Internet of Things (IoT) sensor data. Urban lighting infrastructures increasingly use IoT-enabled devices to monitor operational parameters such as voltage, current, power consumption, temperature, and light intensity. The collected sensor data undergoes preprocessing, cleaning, and normalization to improve model performance. Machine learning classification models are trained to categorize streetlight states as either operational or faulty, aiming to reduce maintenance delays and improve urban infrastructure reliability. Performance is evaluated using Mean Time to Detect (MTTD).

## 1. INTRODUCTION
Street lighting plays a critical role in ensuring public safety and traffic visibility. Modern smart streetlights collect operational data such as electrical parameters and environmental conditions. However, faults like bulb failures or sensor malfunctions lead to safety risks and high costs. Traditional fault detection methods often rely on manual inspection, which is slow. Machine learning offers an intelligent solution to automatically detect anomalies and trigger early maintenance alerts, leading to more resilient urban infrastructure.

## 2. PROBLEM STATEMENT
The objective of this project is to develop a machine learning model that classifies IoT sensor data from smart streetlighting systems into two categories: operational or faulty. The model analyzes parameters like voltage, current, power consumption, and temperature to determine status. Rapid fault detection is evaluated using the Mean Time to Detect (MTTD) metric.

## 3. SDG IMPACT ANALYSIS
This project aligns with Sustainable Development Goal 9: Industry, Innovation, and Infrastructure. By automating fault detection, cities can reduce energy wastage, minimize maintenance delays, and enhance public safety. It promotes data-driven decision-making in urban management and supports the growth of smart city technologies.

## 4. DATASET DESCRIPTION
The dataset consists of 25,817 records and 8 attributes collected from urban smart streetlight sensors.
* **Source:** [Kaggle - Street Light Fault Prediction Dataset](https://www.kaggle.com/datasets/vizeno/street-light-fault-prediction-dataset)
* **Target Variable:** `fault_type` (0 = Operational, 1 = Faulty).
* **Attributes:** timestamp, power_consumption (Watts), voltage_levels (Volts), current_fluctuations (Amperes), temperature (Celsius), environmental conditions, and current_fluctuations_env.

## 5. EXPLORATORY DATA ANALYSIS (EDA) AND DATA PREPROCESSING
EDA was performed to identify patterns and anomalies in sensor readings.
* **Data Inspection:** Used `df.head()`, `df.info()`, and `df.describe()` to verify structure and detect inconsistencies.
* **Missing Values:** The dataset was complete, so no major imputation was required.
* **Target Distribution:** Analyzed the proportion of operational vs. faulty states using a count plot.
* **Outlier Detection:** Boxplots were utilized to identify abnormal sensor behavior.
* **Correlation Analysis:** A heatmap was generated to understand relationships between features.
* **Time Series Analysis:** Observed hourly changes in average power consumption.

## 6. MACHINE LEARNING MODELING
The dataset was split into Training Data (80%) and Testing Data (20%). 
* **Logistic Regression:** Achieved an AUC score of 0.95, showing exceptional discriminatory ability.
* **ROC Curve:** Visualized the trade-off between the True Positive Rate (Sensitivity) and False Positive Rate. An AUC of 0.95 indicates an outstanding ability to distinguish between faulty and normal instances.

## 7. MEAN TIME TO DETECT (MTTD) ANALYSIS
MTTD measures the average time to identify a fault after it occurs. Four models were evaluated:
* **Decision Tree:** 7.9 seconds
* **Random Forest:** 479.6 seconds
* **Logistic Regression:** -831.83 seconds
* **Support Vector Machine (SVM):** -932.34 seconds

## 8. POLLING FREQUENCY ANALYSIS
Polling frequency determines how often the system checks streetlight status. Smaller polling intervals result in faster detection but higher system load. There is a direct linear relationship: a 5-second interval detects faults in ~2.5 seconds, while a 60-second interval results in a 30-second delay.

## 9. BEST MODEL JUSTIFICATION
The **Decision Tree** model is selected as the optimal choice. It achieved an MTTD of 7.9 seconds, which is significantly faster and more efficient than the other models. Its simpler implementation and speed make it ideal for real-time monitoring in smart city infrastructure.

## 10. OVERFITTING ANALYSIS
Overfitting was monitored by comparing training and testing accuracy. Techniques like proper train-test splitting and model tuning ensured the system generalizes well and can detect faults in real-world, unseen conditions.

## 11. FUTURE SCOPE
* Integration with IoT sensors for real-time monitoring.
* Using deep learning models for higher accuracy.
* Developing a mobile application for maintenance team alerts.
* Expanding the system to other infrastructure like traffic lights and power systems.

## 12. CONCLUSION
The Smart Streetlight Fault Detection System uses machine learning to automatically monitor streetlight data and detect faults quickly. This reduces maintenance time and improves the reliability of city lighting, contributing to more efficient urban infrastructure.
