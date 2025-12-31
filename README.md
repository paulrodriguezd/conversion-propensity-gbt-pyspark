# Conversion Propensity Modeling with GBT (PySpark)

This repository presents an **end-to-end machine learning project** focused on **conversion propensity modeling** using **PySpark** and **Gradient Boosted Trees (GBTClassifier)**.

The project demonstrates how to build, evaluate, and operationalize a propensity model in a **scalable Spark environment**, following best practices in feature engineering, model validation, and experiment tracking with **MLflow**.

> ⚠️ **Privacy note**  
> All data used in this project is **synthetic**.  
> No real users, organizations, systems, or internal data sources are represented.

---

## 📌 Project Objective

The goal of this project is to estimate the **probability of conversion** for a given entity and event, producing a **propensity score** that can be used for:
- Prioritization
- Segmentation
- Decision support
- Downstream analytics

The focus is **methodological and technical**, not domain-specific.

---

## 🧱 Project Structure

conversion-propensity-gbt-pyspark/
│
├── notebooks/
│ └── conversion_propensity_gbt_pyspark.ipynb
│
├── README.md
└── .gitignore


---

## 🧪 Dataset

- Fully **synthetic dataset**
- Simulates historical events and outcomes over time
- Includes:
  - Demographic-style attributes
  - Event timing information
  - Aggregated historical behavior features
  - Binary conversion outcome

The dataset is generated within the notebook to ensure **reproducibility**.

---

## ⚙️ Feature Engineering

Features are grouped into:

### Categorical (Label Encoded)
- Region
- Service category
- Coverage type
- Converted service category

### Numerical
- Historical volumes and frequencies
- Conversion rates and dispersion statistics
- Time-to-conversion metrics
- Historical availability flags

Label encoding is intentionally used (instead of one-hot encoding) to remain efficient and compatible with tree-based models in Spark.

---

## 🤖 Model

- **Algorithm**: Gradient Boosted Trees (`GBTClassifier`)
- **Framework**: PySpark ML
- **Validation**:
  - Temporal train / test split
  - Cross-validation
  - Hyperparameter tuning
- **Class imbalance handling**:
  - Weighted loss via `weightCol`

---

## 📊 Evaluation

The model is evaluated using:
- Area Under ROC Curve (ROC-AUC)
- Area Under Precision-Recall Curve (PR-AUC)
- Precision, Recall, and F1-Score
- Confusion matrix

An **optimal decision threshold** is selected based on F1-Score optimization.

---

## 📐 Normalized Propensity Score

In addition to binary predictions, the model outputs a **normalized propensity score (0–1)**, derived from the optimized decision threshold.

This score is suitable for:
- Ranking
- Segmentation
- Downstream rule-based systems
- Dashboards and monitoring

---

## 🧪 Experiment Tracking

All experiments are tracked using **MLflow**, including:
- Hyperparameters
- Metrics
- Selected threshold
- Model artifacts
- Metadata for reproducibility

---

## 🚀 How to Run

### Requirements
- Python 3.9+
- PySpark
- MLflow
- Jupyter Notebook or VS Code

### Execution
1. Open the notebook:
2. Run all cells sequentially.
3. No external data sources are required.

---

## 🧠 Key Takeaways

- Demonstrates a **production-ready ML workflow** in Spark
- Emphasizes **temporal validation** and **propensity modeling**
- Fully **public-safe and reusable** as a portfolio project
- Easily adaptable to other domains or datasets

---

## 📄 License

This project is intended for **educational and portfolio purposes only**.


