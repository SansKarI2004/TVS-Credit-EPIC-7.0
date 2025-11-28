

# **TVS Credit – EPIC 7 Challenge**

### **End-to-End Credit Risk Prediction, Recommendation Engine & AI Chatbot**

This repository contains my complete solution for the **TVS Credit EPIC 7 Challenge**, covering:

✅ Credit risk prediction
✅ Customer risk-based recommendation engine
✅ A production-ready NBFC customer-support AI Chatbot

The work spans data analysis, machine learning, recommendation systems, automation workflows, and chatbot deployment.

---

## ⭐ **Project Highlights**

* Built a **credit default prediction model** with strong performance on precision & recall
* Designed a **dynamic risk-based recommendation engine** using customer personas
* Developed **TVS Sahayak**, an AI-powered support chatbot with memory, data access, and workflow automation
* Added **scaling, cost-benefit, and ROI analysis** for real-world NBFC deployment
* Ensured **data privacy & compliance** following DPDP Act 2023 and RBI guidelines

---

# 📊 **1. Exploratory Data Analysis**

(Refer to page 2 for visuals & workflow) 

### **Steps Performed**

* Assessed dataset shape & validated zero missing values
* Generated descriptive statistics & distribution plots
* Performed categorical frequency analysis (Location, Loan Type, Income Groups etc.)
* Created correlation heatmaps
* Conducted target-vs-feature analysis

### **Key Insight**

As seen in the chart on page 2, **complaints, delay days, and missed payments** show a strong positive correlation with defaults, while **age and income** show strong negative correlation.
These signals were used for feature selection.

---

# 🤖 **2. Prediction Modeling**

(Refer to page 3 for modeling pipeline & metrics) 

### **Technique**

* One-hot encoded categorical data
* Created new engineered features:

  * Debt-to-Income Ratio
  * Delinquency Rate
* Used **IQR** for outlier detection (retained due to model robustness)
* Normalized features with **Min-Max Scaler**
* Split into train–validation–test sets

### **Modeling**

* Selected **Random Forest**, optimized using **GridSearchCV (5-fold CV)**
* Benchmarked vs **XGBoost + LightGBM**
* Improved interpretability with **SHAP values** (see page 11)

### **Chosen evaluation priority**

Business-case aligned:

* **High Precision**
* **Low False Negatives (High Recall)** — avoids misclassifying true defaulters

The confusion matrix & metrics on page 3 reflect this approach.

---

# 🎯 **3. Recommendation Engine**

(Refer to page 4–5 for architecture & strategy matrix) 

### **Pipeline**

* Assigned **risk scores** using model output
* Classified customers into:

  * Low Risk
  * Mid Risk
  * High Risk
* Built personas based on:

  * Interaction history
  * Complaints
  * Delinquencies
  * Engagement patterns

### **Dynamic Thresholding**

As explained on page 4:

* Initially thresholds were hardcoded
* Updated to **percentile-based thresholds** for adaptable, dataset-independent rules

### **Strategy Matrix**

Shown on page 5 — mapping:

* Risk Level × Behavior Type → Action Strategy
  E.g:
* High-risk aggressive → "Senior escalation + automated contact"
* Low-risk cooperative → "Gentle payment reminder / chatbot nudge"

---

# 💬 **4. TVS Sahayak – AI Chatbot**

(Full details & screenshots on pages 6–9) 

### **Goal**

A production-ready NBFC support bot that:

* Remembers users
* Fetches financial data
* Responds empathetically
* Reduces call center load

### **Tech Stack**

* **n8n** (workflow automation)
* **Supabase** (database)
* **Telegram** (chat UI)
* Secure backend integration

### **Database Design**

Page 6 shows:

* *Customer Data* table storing financial & account details
* *Conversation Memories* storing chat history

### **Features**

(Page 7)

1. Context-aware responses
2. Direct financial data lookup
3. Personalized assistance
4. Seamless onboarding
5. User identification via unique chat ID
6. Multi-case handling
7. Optimized workflow

### **Privacy & Security**

* TLS 1.3 encryption
* AES-256 at rest
* Tokenization of sensitive fields
* RBAC + audit logging
* DPDP Act & RBI compliance

### **Screenshots**

Page 9 shows variations of:

* Complaints
* Frustration
* Payment queries
* Loan queries
* Confusion
* Status requests

---

# 🧩 **5. Scaling, Deployment & ROI**

(Refer to page 8 for full cost-benefit visuals) 

### **Scalable Architecture**

* Deploy on AWS/GCP/Azure
* Use Docker + Kubernetes
* Switch to PostgreSQL
* Use Redis queue workers
* Add Prometheus + Grafana for monitoring

### **ROI**

Page 8 table shows impressive numbers for a ₹100 Cr portfolio:

* Worst case: **₹4.9 Cr** net benefit
* Base case: **₹9.7 Cr**
* Best case: **₹19.9 Cr**

Due to:

* Reduced defaults
* 24×7 automation
* Better customer experience

---

# 📂 **Repository Structure**

```
📁 analysis/
   ├── EDA notebooks
   ├── correlation studies
   └── SHAP interpretability

📁 modeling/
   ├── feature engineering
   ├── model training scripts
   ├── evaluation metrics
   └── model outputs

📁 recommendation_engine/
   ├── persona definitions
   ├── strategy matrices
   └── thresholding logic

📁 chatbot/
   ├── n8n workflows
   ├── database schema
   └── integration scripts

📁 docs/
   ├── project report
   ├── images
   └── appendices
```

---

# 🧠 **Future Improvements**

* Automated learning of thresholds for persona mapping
* Integrating WhatsApp + IVR channels
* Real-time streaming model for continuous risk estimation
* Fine-tuned domain-specific LLM for NBFC support

---

# 📜 **License**

This project is released under the **MIT License**.

---

# 🙌 **Acknowledgements**

Project built for **TVS Credit – EPIC 7 Challenge**.
All visuals and content come from the official submission document. 

