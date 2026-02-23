# Football Data Mining & Analysis Portfolio
**Author:** Sasan Nikjoo  
**Course:** Data Mining Project (Phases 1-3)  
**Stack:** Python (Pandas, Scikit-Learn, Seaborn, Mlxtend)

---

## 📌 Project Overview
This comprehensive project explores the entire lifecycle of data mining, applied specifically to the global football transfer market. Across three distinct phases, the project transitions from raw data rehabilitation to advanced pattern discovery and predictive modeling. The core dataset (`football.csv`) contains approximately 4,700 transfer records, featuring attributes such as player age, market value, position, and transfer fees.

---

## 📂 Phase 1: Data Exploration & Preprocessing
The foundation of the project focused on transforming "unreliable" raw data into a "modeling-ready" state through rigorous **Data Quality Analysis (DQA)**.

### 🔍 Data Quality Transformation
Initial analysis revealed significant issues, including 28% incompleteness and logical errors (e.g., players aged 0 or 288).

| Metric | Initial Score | Final Score | Action Taken |
| :--- | :--- | :--- | :--- |
| **Completeness** | 71.9% | **100%** | Imputed 1,321 `Market_value` records using **Median-by-Position**. |
| **Accuracy** | 98.0% | **100%** | Filtered biological impossibilities in `Age` and corrected types. |
| **Validity** | 92.8% | **100%** | Standardized `Season` formats and removed invalid league entries. |



### 📈 Exploratory Data Analysis (EDA)
* **Key Drivers**: `Market_value` and **Season (Inflation)** were identified as the primary determinants of transfer fees.
* **Age Dynamics**: Visualized a non-linear relationship where player value peaks in the mid-20s before a steady decline.
* **Correlation Strategy**: Heatmaps confirmed a high density of information between market value and final price, allowing for strategic dimensionality reduction.

---

## 🛒 Phase 2: Frequent Pattern Mining & Association Rules
This phase moved beyond individual player stats to discover hidden relationships in transaction data using **Market Basket Analysis** techniques.

### 🛠️ Algorithm Comparison: Apriori vs. FP-Growth
The project involved a head-to-head comparison between a **manually implemented Apriori algorithm** and the **library-optimized FP-Growth**.

* **Result**: Both algorithms identified the same **22 frequent itemsets**, validating the manual logic of candidate generation and pruning.
* **Performance**: Both achieved execution times near ~0.009s for the given 999-transaction dataset.



### 💡 Statistical Association Insights
Using a **Minimum Confidence of 50%**, we extracted rules and validated them with advanced metrics:
* **Top Rule**: `Milk ↔ Chocolate` (**Lift: 1.24**).
* **Statistical Significance**: A **Chi-Square ($\chi^2$)** value of **27.7** confirmed that these associations are statistically significant and not the result of random distribution.
* **Metric Balance**: Analyzed using the **Kulczynski measure** to ensure rules remained robust regardless of item frequency imbalances.

---

## 🤖 Phase 3: Clustering & Multiclass Classification
The final phase utilized Unsupervised and Supervised learning to segment the market and predict transfer price brackets.

### 1. The Clustering "Family"
Players were grouped using various distance and density-based strategies to identify underlying patterns:
* **Centroid/Medoid**: Standard K-Means, Bisecting K-Means, and K-Medoids.
* **Soft/Non-Linear**: **Fuzzy C-Means** (probabilistic membership) and **Kernel K-Means** (Spectral Clustering).
* **Density & Hierarchy**: **DBSCAN** was used to isolate anomalous "record-breaking" transfers, while **Agglomerative Clustering** provided dendrograms to visualize market merging.
* **Optimization**: The **Elbow Method** and **Silhouette Analysis** identified **K=3** as the most stable configuration.



### 2. Predictive Classification
The continuous `Transfer_fee` was discretized into four categories: **Low, Medium, High,** and **Elite**. We trained multiple classifiers to predict these price brackets.

| Model | Performance Note |
| :--- | :--- |
| **Decision Tree** | High interpretability; captures non-linear splits in transfer fees. |
| **SVM** | Robust for higher-dimensional separation between "High" and "Elite" players. |
| **KNN** | Effectively identified "Price Peers" based on similar player profiles. |
| **Naive Bayes** | Served as a baseline probabilistic model for classification. |

---

## 🛠️ Technologies & Structure
* **Core**: Python 3.x, Jupyter Notebook.
* **Libraries**: Pandas, NumPy, Scikit-Learn, Mlxtend, Scikit-Fuzzy, Matplotlib, Seaborn.
* **Files**: 
    * `football_clear.csv` (Cleaned data)
    * `project1/2/3.ipynb` (Analysis phases)
    * `README.md` (Project documentation)

---

## 📝 Final Conclusion
By applying rigorous data mining techniques, the dataset was successfully transformed from an **"Unreliable"** state to a **"Clean and Ready for Modeling"** state. The analysis highlighted that while intrinsic player quality (Market Value) drives price, external economic factors (Season/Inflation) and player age play massive roles, necessitating careful feature engineering for accurate predictive modeling.