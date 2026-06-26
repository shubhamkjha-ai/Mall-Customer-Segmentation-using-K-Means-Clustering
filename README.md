# 🛍️ Mall Customer Segmentation using K-Means Clustering

A machine learning project that segments mall customers into distinct groups based on their **Annual Income** and **Spending Score**, enabling targeted marketing strategies.

---

## 📌 Project Overview

This project applies **unsupervised machine learning** (K-Means Clustering) on the Mall Customers dataset to identify meaningful customer segments. By understanding different customer types, businesses can personalize offers, optimize campaigns, and improve customer retention.

---

## 📂 Dataset

- **File:** `Mall_Customers.csv`
- **Records:** 200 customers
- **Features Used:**
  | Feature | Description |
  |---|---|
  | `Annual Income (k$)` | Customer's annual income in thousands |
  | `Spending Score (1-100)` | Score assigned by the mall based on spending behavior |

---

## 🔧 Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Scikit-learn | KMeans clustering, StandardScaler |
| Matplotlib | Data visualization |
| Google Colab | Development environment |

---

## 🚀 Workflow

### 1. Data Loading & Exploration
- Loaded `Mall_Customers.csv` using Pandas
- Inspected shape, column names, and descriptive statistics
- Dataset: 200 rows × 5 columns

### 2. Feature Selection & Preprocessing
- Selected `Annual Income (k$)` and `Spending Score (1-100)` as features
- Applied **StandardScaler** to normalize features before clustering

### 3. Finding Optimal K — Elbow Method
- Ran KMeans for K = 1 to 10
- Plotted **Inertia vs. K** to identify the "elbow"
- **Optimal K = 5** chosen from the elbow curve

```
K Values:  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Inertia:   [400.0, 269.69, 157.7, 108.92, 65.57, 55.06, 44.86, 37.23, 32.39, 29.98]
```

### 4. Model Training
- Trained final KMeans model with **K=5**, `random_state=42`, `n_init=10`
- Assigned cluster labels to all 200 customers

### 5. Visualization
- Scatter plot of all clusters with distinct colors
- Cluster centers marked with black `X` markers

### 6. Customer Analysis & Prediction
- Characterized each cluster with meaningful business labels
- Built a prediction pipeline for new/unseen customers

---

## 📊 Customer Segments Identified

| Cluster | Customer Type | Count | Avg Income (k$) | Avg Spending Score |
|---|---|---|---|---|
| 0 | Average Customers (Moderate Income + Moderate Spending) | 81 | 55.3 | 49.5 |
| 1 | VIP Customers (High Income + High Spending) | 39 | 86.5 | 82.1 |
| 2 | Impulsive Buyers (Low Income + High Spending) | 22 | 25.7 | 79.4 |
| 3 | Careful Customers (High Income + Low Spending) | 35 | 88.2 | 17.1 |
| 4 | Budget Shoppers (Low Income + Low Spending) | 23 | 26.3 | 20.9 |

---

## 🎯 Sample Predictions

| Annual Income (k$) | Spending Score | Predicted Cluster | Customer Type |
|---|---|---|---|
| 80 | 85 | 1 | VIP Customer |
| 90 | 90 | 1 | VIP Customer |
| 50 | 50 | 0 | Average Customer |
| 80 | 10 | 3 | Careful Customer |
| 20 | 80 | 2 | Impulsive Buyer |
| 15 | 20 | 4 | Budget Shopper |

---

## 📁 Project Structure

```
mall-customer-segmentation/
│
├── Mall_Customers.csv          # Dataset
├── customer_segmentation.ipynb # Main Colab notebook
├── elbow.png                   # Elbow method plot
├── clusters.png                # Customer cluster visualization
└── README.md                   # Project documentation
```

---

## ▶️ How to Run

1. **Clone or download** this repository
2. Upload `Mall_Customers.csv` when prompted in Google Colab
3. Run all cells sequentially in `customer_segmentation.ipynb`
4. View generated plots: `elbow.png` and `clusters.png`

**Or run locally:**
```bash
pip install numpy pandas matplotlib scikit-learn
jupyter notebook customer_segmentation.ipynb
```

---

## 💡 Business Insights

- **VIP Customers (Cluster 1):** High priority — reward with loyalty programs and premium offers
- **Impulsive Buyers (Cluster 2):** Target with flash sales and limited-time deals
- **Careful Customers (Cluster 3):** Engage with value-proposition messaging and discounts
- **Budget Shoppers (Cluster 4):** Attract with budget-friendly deals and clearance sales
- **Average Customers (Cluster 0):** Largest segment — nurture with general promotions

---

## 👨‍💻 Author

**Shubham Kumar Jha**  
B.Tech CSE (2025-29) | BIT Sindri

Machine Learning Intern at SkillCraft Technology

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
