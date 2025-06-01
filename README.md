# Customer Segmentation using RFM Analysis

## 📌 Overview
This project performs customer segmentation using RFM (Recency, Frequency, Monetary) analysis combined with K-Means clustering. It analyzes transactional data to identify distinct customer groups for targeted marketing strategies.

## 🛠️ Technologies Used
- Python 3
- Pandas (Data manipulation)
- NumPy (Numerical operations)
- Scikit-learn (K-Means clustering)
- Matplotlib/Seaborn (Visualization)
- Jupyter Notebook (Optional)

## 📂 Dataset
- **Source**: Synthetic transaction data generated for 500 customers (2022-2023)
- **Fields**:
  - `TransactionID`, `CustomerID`, `TransactionDate`
  - `ProductID`, `Quantity`, `UnitPrice`, `TotalPrice`

## 🔍 Key Steps

### 1. Data Preparation
- Generated mock transaction data with realistic customer profiles
- Checked for missing values and outliers
- Calculated RFM metrics:
  - **Recency**: Days since last purchase
  - **Frequency**: Transaction count per customer
  - **Monetary**: Total spend per customer

### 2. Feature Engineering
- Applied log transformation to Monetary values to handle skewness
- Standardized features using `StandardScaler`
- Created RFM scores (1-5 scale) using quintile-based binning

### 3. Clustering
- Used Elbow Method to determine optimal clusters (k=4)
- Performed K-Means clustering (random_state=42)
- Identified customer segments:

| Cluster | Segment Name               | Characteristics                     |
|---------|----------------------------|-------------------------------------|
| 0       | Old but loyal customers    | High frequency but inactive recently|
| 1       | Loyal high spenders        | Recent, frequent, high-value        |
| 2       | At-Risk Low spenders       | Low recency and monetary value      |
| 3       | New or occasional customers| Moderate recency, low frequency     |

## 📊 Results
- **Cluster Distribution**:
  ```python
  print(df['Cluster'].value_counts())
