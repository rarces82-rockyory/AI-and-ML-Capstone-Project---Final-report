# Supply Chain SLA Predictability Analysis

##  Author  
Roy Arce

---

##  Executive Summary  
This project analyzes supply chain shipment performance using S/4HANA data to evaluate Service Level Agreement (SLA) adherence and predict shipment risks.  

Using Python-based tools such as pandas and scikit-learn, the dataset was cleaned, explored, and engineered to uncover the key drivers of SLA performance. A classification model was developed to predict whether shipments will meet SLA, enabling proactive risk identification and improved operational decision-making.

---

##  Rationale  
Supply chain delays impact customer satisfaction, revenue, and operational efficiency. Organizations often operate reactively, addressing delays after they occur. This project aims to shift toward a predictive approach, allowing teams to identify at-risk shipments early and take corrective action.

---

##  Research Question  
Can we accurately predict whether a shipment will meet SLA based on historical supply chain data, and what factors drive delays?

---

## Data Sources  
- S/4HANA shipment and order data, which includes the shipment report (orders shipped) and current backlog (active/open orders) within SAP ERP 
- Key fields include:
  - Sales Order Number (masked)  
  - Customer Requested Delivery Date (CRD)  
  - Actual Shipment Date  
  - Material Availability Date  
  - Factory Plant  
  - Product Line / Division  
  - Order Priority  

 Sensitive data (order numbers, customer names, IDs, and other sensitive information) has been masked for public use.

---

##  Data Preparation & Preprocessing  
- Removed duplicates and irrelevant records  
- Excluded non-SLA impacting items (e.g., intangible indicator = X)  
- Created SLA target variable:
  - SLA Met = Actual Shipment Date ≤ CRD  
- Engineered features:
  - Delay days  
  - Lead times  
  - Date-based features  
- Handled missing values  
- Encoded categorical variables  
- Split data into training and testing sets  

---

##  Methodology  

### Model Type:
- Supervised Learning (Classification)  

### Model Used:
- Logistic Regression  

### Approach:
- Feature engineering based on supply chain logic  
- Removed potential data leakage  
- Applied hyperparameter tuning  
- Used cross-validation to ensure model stability  

---

##  Model Selection & Tuning  

Multiple modeling approaches were evaluated to determine the most effective method for predicting SLA adherence. After validating feature integrity and removing potential data leakage, the final approach focused on Logistic Regression due to its strong performance and interpretability.

### Tuning Approach:
- Grid Search and Randomized Search for hyperparameter optimization  
- Cross-validation to ensure model robustness  
- Evaluation using ROC-AUC and Precision-Recall metrics  

### Why Logistic Regression:
- Strong balance of performance and interpretability  
- Performs well under class imbalance  
- Easy to explain to business stakeholders  
- Stable and scalable for real-world use  

---

## 📈 Results  

The final model achieved:

- ROC-AUC ≈ 0.95  
- PR-AUC ≈ 0.997  
- Accuracy ≈ 0.89  

Due to class imbalance (~95% SLA met), the evaluation focused on ROC-AUC and PR-AUC rather than accuracy alone.

---

##  Model Evaluation  

### Metrics Used:
- ROC-AUC  
- Precision-Recall AUC  
- Accuracy  

### Evaluation Approach:
- Cross-validation for consistency  
- Focus on recall and AUC for risk detection  
- Model selected based on performance and interpretability  

---

## 🔍 Findings  

- Material availability is a key driver of delays  
- Factory performance variability impacts SLA  
- High-priority orders are not always delivered faster  
- Predictive modeling can identify high-risk shipments early  

---

## 🚀 Business Impact  

- SLA risk prediction for open orders  
- Revenue-at-risk visibility  
- Risk segmentation (Low / Medium / High)  
- Improved prioritization of operations  

---

## 🧾 Conclusion  

This project demonstrates how structured data science can transform operational shipment data into actionable business insights. By combining data cleaning, feature engineering, and predictive modeling, the analysis identified key drivers of SLA performance and enabled accurate prediction of shipment risks.

The Logistic Regression model achieved strong performance while maintaining interpretability, making it suitable for business adoption.  

This solution enables a shift from reactive issue management to proactive risk mitigation, helping prioritize high-impact orders before SLA failures occur.

---

## 📂 Project Structure  

- notebook.ipynb → Full analysis  
- README.md → Summary  
- Final report PDF

---

## 🔗 Notebook Links  
- [Main Notebook](#)  

---

## 📞 Contact  
For questions or collaboration, please reach out to Roy Arce via email at rarces82@gmail.com
