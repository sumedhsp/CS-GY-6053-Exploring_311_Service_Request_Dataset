 
# 📊 311 Service Requests: Resource Utilization & Resolution Time Prediction

## Foundations of Data Science - Final Project (CS-GY 6053)

## 🚀 Project Overview
This project aims to **maximize resource utilization and predict resolution times** for **NYC 311 service requests** using **machine learning models**. By analyzing complaint trends and seasonal variations, we develop predictive models to improve the efficiency of complaint resolution.

---

## 🔍 Problem Statement
The NYC **311-service request system** is crucial for resolving complaints reported by citizens. However, **delays** in response occur due to **unavailability of resources**. Our project aims to:
- **Analyze complaint trends** by type and location.
- **Assess seasonal variations** to detect unusual spikes.
- **Predict resolution time** using a **Regression Model**.
- **Predict additional resource requirements** using a **Classification Model**.

### **🎯 Target Variables**
1. **Resolution Time (Regression)** – Number of days taken to resolve a complaint.
2. **Additional Resources Needed (Classification)** – Binary variable indicating if extra resources are required.

---

## 📂 Datasets
We use multiple datasets to enhance our model's predictive capabilities:
- **📌 NYC 311 Service Requests** ([Dataset](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9))  
  - Contains **34 million records** from **2010 to the present**.
  - Features include **complaint type, location, timestamps, and resolution times**.
- **📌 Zip Code Data** ([Dataset](https://data.cityofnewyork.us/Business/Zip-Code-Boundaries/i8iw-xf4u))  
  - Provides **spatial data**, including population details.
- **📌 Holiday Data**  
  - 2010-2020: [Dataset](https://data.world/jennifer-v/us-holiday-dates-2010-2020)  
  - 2021-2023: [Dataset](https://www.generalblue.com/calendar/usa/us-holidays-2022)  

---

## 🔧 Data Processing & Feature Engineering
### **🔹 Data Cleaning**
- Removed irrelevant columns & records with missing values.
- Filtered out **rows without closure dates** (incomplete records).
- Merged **ZipCode & Holiday datasets** to enhance location-based & seasonal insights.

### **🔹 Feature Engineering**
- **Regression Target Variable**: Computed `resolution_time = closed_date - created_date`.  
- **Classification Target Variable**: `1` if resolution time exceeds department average, else `0`.  
- **Time-based Features**: Extracted **season, month, day, and hour** to analyze trends.  
- **Outlier Removal**: Removed top **10% resolution time values** to avoid extreme delays affecting the model.  

---

## 📊 Data Analysis & Insights
### **Complaint Trends**
- **Top Boroughs with Most Complaints**
  | Borough        | Complaints |
  |---------------|------------|
  | Brooklyn      | 73,604     |
  | Queens        | 53,083     |
  | Bronx         | 50,372     |
  | Manhattan     | 47,395     |
  | Staten Island | 10,861     |

- **Most Common Complaint Types**  
  - Noise
  - Street Conditions
  - Illegal Parking  
  - Blocked Driveways  

### **Seasonal Variations**
- **Autumn** has the **highest number of complaints**.
- **Summer** reports **fewer complaints**, likely due to vacations.

### **Department-wise Delays**
- Calculated **delay scores** for departments across boroughs.
- **NYPD had the highest delay scores**, indicating slow resolution times.

---

## 🏗 Model Development
We implemented **two modeling techniques**:

### **1️⃣ Regression Models (Predicting Resolution Time)**
- **🏆 Best Model:** **XGBoost** (Best R² Score)
- **Other Models Tested:**
  - ✅ Ridge Regression
  - ✅ ElasticNet
  - ✅ Random Forest Regressor
  - ✅ Gradient Boosting (GB) Regressor

### **2️⃣ Classification Models (Predicting Additional Resource Needs)**
- **🏆 Best Model:** **Gradient Boosting Classifier (GB)**
- **Other Models Tested:**
  - ✅ Decision Trees
  - ✅ Random Forest
  - ✅ k-NN Classifier

### **📏 Evaluation Metrics**
| Metric            | Regression | Classification |
|------------------|------------|--------------|
| R² Score        | ✅ Used   | ❌ Not Applicable |
| Accuracy        | ❌ Not Used | ✅ Used |
| Precision       | ❌ Not Used | ✅ Used |
| Recall          | ❌ Not Used | ✅ Used |
| F1-Score       | ❌ Not Used | ✅ Used |
| AUC-ROC Curve  | ❌ Not Used | ✅ Used |

---

## 📈 Results & Key Findings
- **XGBoost Regression** model had the **highest R² score**.
- **Gradient Boosting Classifier** was the most effective for predicting **resource requirements**.
- **Seasonal patterns and borough-wise trends** influence complaint resolution time.
- **Delays are common in NYPD-related complaints**, requiring more proactive resource allocation.

---

## 📂 Repository Structure

The repository contains the following notebooks:
```yaml
.
├── 311_preprocessing.ipynb         # Preprocessing logic for the 311 dataset and zip-code dataset
├── 311_dataAnalysis.ipynb          # Comprehensive data analysis for the 311 dataset and zipcode dataset. Additionally contains visualization of dataset analysis (graph + chart)
├── 311_modelling.ipynb             # Regression and Classification models used in our project
├── 311_holidaysDataAnalysis.ipynb  # Holiday dataset analysis with 311 dataset to understand their relationship 
├── 311_samplingValidation.ipynb    # Script used to vbalidate the agency distribution of 311 dataset

```

---

## 🔄 Reproducibility

The notebooks should be executed in the following order
1) 311_preprocessing
2) 311_dataAnalysis
3) 311_holidaysDataAnalysis
4) 311_modelling
5) 311_samplingValidation

---

## 🔮 Future Work
🔹 **Quantify exact resource needs** instead of binary classification.  
🔹 **Explore time-series forecasting** for service demand prediction.  
🔹 **Enhance model interpretability** using SHAP & feature importance.  

---

## 🤝 Contributors
👨‍💻 **Team Members**:
- **Nikhil Soni** (`ns6062@nyu.edu`)   
- **Sumedh Parvatikar** (`sp7479@nyu.edu`)   
- **Kaartikeya Panjwani** (`kp3291@nyu.edu`)   

---

## 📜 Assumptions & Limitations
✅ **Assumptions**:
- Complaints are **reported with equal probability**.
- **Population changes over 10 years are negligible**.
- Departments **accurately record resolution times**.

🚧 **Limitations**:
- Focused on **top 5 departments** only.
- Only **binary classification** for resource needs (not quantity).

---

🔥 **Want to contribute?** Fork this repo, open an issue, or submit a pull request!  
📢 **If you find this project useful, give it a ⭐!**  