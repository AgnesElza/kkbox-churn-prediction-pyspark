# Scalable Churn Prediction with PySpark (KKBox)

This project demonstrates how to build a **scalable churn prediction pipeline** using the KKBox dataset and **PySpark**.  
It highlights **big data processing, feature engineering with Spark window functions, MLlib modeling, and evaluation** to identify at-risk subscribers.  

The goal is to show how churn prediction can be scaled beyond pandas workflows and translated into actionable **customer retention strategies**.  

---

## Project Workflow
1. **Data Processing (PySpark)** – Load millions of log entries and aggregate user activity at scale.  
2. **Feature Engineering** – Derive features using **window functions**.  
3. **Modeling (Spark MLlib)** – Train Logistic Regression.  
4. **Evaluation** – Compare models with AUROC, AUPRC, and Lift@K (business-focused metric).  
5. **Insights** – Identify top churn drivers and interpret results for retention strategy.  

---

## Dataset
Source: **KKBox Churn Prediction Challenge (Kaggle)**  

Key tables used:
- `user_logs.csv` – daily listening activity (play counts, unique songs, session data).  
- `transactions.csv` – subscription payments, renewals, cancellations.  
- `train.csv` – churn labels (whether the user churned or not).
- `members.csv` – Demographics (gender, registration date, etc.).

---

## Key Features
- **Active Days** – number of days a user engaged with the platform.  
- **Play Counts** – total listens across track-length categories.  
- **Unique Songs** – measure of content diversity.  
- **Engagement Momentum** – change in average plays between recent weeks.  
- **Tenure & Payment Features** – subscription length, payment consistency.  

---

## Results
- **Best Model:** Gradient Boosted Trees (Spark MLlib)  
- **AUROC:** ~0.72  
- **AUPRC:** ~0.14  
- **Lift@5%:** ~3x → top 5% of predicted at-risk users were 3x more likely to churn than average.  

**Takeaway:** The model enables **targeted retention campaigns** by ranking high-risk users effectively.  

---

## Business Insights
- Long inactivity gaps are the strongest churn driver.  
- High diversity of music consumption (unique songs per day) reduces churn risk.  
- Engagement momentum (whether usage is rising or falling) is a leading indicator.  
- Models built on PySpark scale efficiently to millions of records, making them **production-ready for real-world churn prediction**.  

---

## Next Steps
- Add **session-level features** (time of day, session length).  
- Test **XGBoost on Spark** for potential accuracy gains.  
- Build a **real-time scoring pipeline** for churn risk prediction.  

---

**This project highlights scalable data science with PySpark, combining distributed feature engineering, ML modeling, and business insights for subscription retention.**
