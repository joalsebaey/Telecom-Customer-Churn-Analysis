# 📊 Telecom Customer Churn Dashboard (Power BI)

This project provides a comprehensive analysis of customer churn in a telecom company. It uses Power BI to visualize churn trends, customer behavior, and key factors influencing churn. The dashboard helps business stakeholders identify areas of improvement and make data-driven retention strategies.

---

## 📁 Repository Structure
telecom-churn-dashboard/ │ ├── dataset/ │ └── telecom_customer_churn.csv # The dataset used in Power BI │ ├── visuals/ │ └── screenshots/ # Screenshots of dashboard visuals │ ├── dax-measures/ │ └── churn_dax_measures.txt # All DAX measures used in the report │ ├── pbix/ │ └── Telecom_Churn_Analysis.pbix # Power BI dashboard file  │ └── README.md \


---

## 📌 Dashboard Overview

The Power BI dashboard includes:

- **Churn KPIs**: Total Customers, Churned Customers, Churn Rate, Avg Monthly Charges
- **Churn by Demographics**: Gender, Senior Citizen, Partner, Dependents
- **Service Usage Impact**: Internet Service, Online Security, Tech Support, Streaming
- **Contract Analysis**: Month-to-month, One year, Two year
- **Tenure Trends**: Churn across customer lifetime
- **Charges vs Churn**: Distribution of Monthly Charges and Total Charges

---
# Customer Churn Analysis Dashboard  

This repository contains interactive dashboards analyzing customer behavior, service usage, and churn drivers to improve retention and revenue.  

## 📊 **Key Insights**  

### **1. Churn Analysis**  
- **27% churn rate**, driven by:  
  - Competitor offers (better pricing/higher speeds).  
  - Poor service/support experiences.  
  - Month-to-month contract customers.  
- **Highest churn** among low-tenure users (0-20 months).  

### **2. Service Optimization**  
- **Fiber Optic users** generate the highest revenue.  
- Only **49.3%** adopt device protection plans.  

### **3. Customer Demographics**  
- Near-even gender split (49.5% Female, 50.5% Male).  
- Married customers (51.7%) use more services.  

---

## 🎯 **Recommendations**  

### **Retention Strategies**  
- Offer **loyalty discounts** for annual contracts.  
- Launch **win-back campaigns** for 0-20 month tenure users.  

### **Upsell Opportunities**  
- Promote **Fiber Optic upgrades** to DSL/Cable users.  
- Bundle **device protection + unlimited data** at a discount.  

### **Process Improvements**  
- **Auto-pay incentives** (e.g., "$5/month discount").  
- **Streamline refunds** to reduce disputes.  

---

## 📂 **Dashboard Features**  
- **Interactive filters** (contract type, region).  
- **Churn reason breakdowns**.  
- **Revenue by payment method**.  

---

## 📈 Key DAX Measures

```dax
Total Customers = COUNTROWS('CustomerData')

Churned Customers = CALCULATE(COUNTROWS('CustomerData'), 'CustomerData'[Churn] = "Yes")

Churn Rate = DIVIDE([Churned Customers], [Total Customers])

Avg Monthly Charges = AVERAGE('CustomerData'[MonthlyCharges])

Tenure Group = 
SWITCH(
    TRUE(),
    'CustomerData'[tenure] <= 12, "0-12 months",
    'CustomerData'[tenure] <= 24, "13-24 months",
    'CustomerData'[tenure] <= 48, "25-48 months",
    'CustomerData'[tenure] <= 60, "49-60 months",
    "60+ months"
)
```

## 🧪 How to Use
Download or clone this repository.

Open Telecom_Churn_Analysis.pbix in Power BI Desktop.

Load the telecom_customer_churn.csv dataset.

Use filters and slicers to explore churn behavior by demographic and service attributes.

## 💡 Insights You Can Extract
Which customer segments have the highest churn?

How do services like internet, security, or streaming impact churn?

Are short-term contract users more likely to churn?

What is the optimal tenure or billing strategy to retain customers?

## 📝 License
MIT License


