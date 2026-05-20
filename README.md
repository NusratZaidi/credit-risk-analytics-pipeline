# Enterprise Credit Risk Analytics & ML Pipeline

An end-to-end financial intelligence framework designed to assess, score, and visualize credit default risks. This project transitions from a raw cloud data warehouse to a high-performance machine learning classifier, culminating in an executive-ready operational dashboard.

---

## 🛠️ Technology Stack & Architecture

* **Cloud Data Warehouse:** Google Cloud Platform (GCP) & BigQuery Sandbox
* **Data Engineering & ML Engine:** Python (Pandas, Scikit-Learn, LightGBM)
* **Business Intelligence:** Power BI Desktop (Direct Cloud Storage Import Stream)
* **Core Algorithm:** Random Forest Classifier (Optimized for False-Negative reduction)

---

## 🚀 System Architecture Workflow

1. **Cloud Ingestion:** Raw historical loan application data (`32,581` records) ingested into **Google BigQuery**.
2. **Exploratory Data Analysis (SQL):** Executed advanced relational queries to isolate risk criteria (discovered **31.57% default rate among Renters** vs **7.47% for Homeowners**).
3. **Machine Learning Pipeline (Python):** * Handled missing data via median imputation.
   * Transformed non-numeric elements using One-Hot Categorical Encoding.
   * Split data into 80/20 train-test metrics with class stratification.
4. **BI Deployment:** Modeled enterprise-grade DAX measures in **Power BI** linked directly to the GCP cloud warehouse via custom native queries.

---

## 📊 Machine Learning Performance Metrics

The predictive engine was evaluated strictly against banking risk mitigation goals (minimizing financial exposure from missed defaults):

* **Overall Model Accuracy:** `93%`
* **Credit Default Precision (Class 1):** `0.95` (Low False-Positive alerts)
* **Credit Default Recall (Class 1):** `0.70` (Successfully captured high-risk outliers)

---

## 📉 Executive Dashboard Configuration

The interactive Power BI analytics application features dedicated risk management views with optimized semantic layers:

### 🧩 Core Business Metrics (DAX Measures)
* **Total Loan Applications:** `COUNT(loan_applications[person_age])`
* **Portfolio Default Rate (PAR %):** `DIVIDE(SUM(loan_applications[loan_status]), [Total_Applications], 0)`
* **Total Capital At Risk (Exposure):** `CALCULATE(SUM(loan_applications[loan_amnt]), loan_applications[loan_status] = 1)`

### 🎨 Visual Layout & Operational Control Layer
* **Risk Probability by Credit Intent (Clustered Column Chart):** Tracks default rates across loan motives (Isolates Debt Consolidation and Medical segments as highest vulnerability).
* **Applicant Demographic: Housing Status (Donut Chart):** Displays volume share across property profiles with in-chart relative percentage distributions.
* **Historical Delinquency Record & Credit Risk Tier Classification (Interactive Slicers):** Dynamic cross-filtering workspace layers mapped using optimized Tile/Dropdown filters.

---

## 🛠️ How to Run the Project

1. **SQL Initialization:** Execute the queries inside `/sql/bq_cleaning_eda.sql` within your Google BigQuery console.
2. **ML Execution:** Run the Jupyter Notebook `/notebooks/credit_risk_ml_pipeline.ipynb` in Google Colab to authenticate your GCP client and train the Random Forest model.
3. **Dashboard View:** Open the Power BI template file, select the Google BigQuery connection stream, input your `Project ID`, and refresh the data grid model.


<img width="1306" height="749" alt="image" src="https://github.com/user-attachments/assets/a29b2d68-7129-48c1-a0f2-ca5c8b3fee78" />
