# Football Player Clustering & Classification Analysis

## 📌 Project Overview
This project represents **Phase 3** of the Data Mining course, focusing on **Unsupervised Learning (Clustering)** and **Supervised Learning (Classification)**. 

The objective is to analyze the football player dataset to:
1.  **Cluster players** into meaningful groups based on their attributes (Age, Market Value, Transfer Fee) using various algorithms.
2.  **Classify players** into price brackets (Low, Medium, High, Elite) by predicting their transfer fees using multiclass classification models.

---

## 🚀 Phase 1: Clustering Analysis

In this phase, we grouped players into clusters to identify underlying patterns without predefined labels. We implemented and compared the entire **K-Means Family** and other major clustering techniques.

### 1. Data Preparation
* **Features Selected**: `Age`, `Market_value`, `Transfer_fee`.
* **Preprocessing**: Data was cleaned and normalized using **StandardScaler** to ensure distance-based algorithms function correctly.

### 2. Algorithms Implemented
The following algorithms were implemented from scratch or using `scikit-learn`/`skfuzzy`:

| Algorithm Family | Specific Algorithms Used |
| :--- | :--- |
| **Centroid-Based** | **Standard K-Means**, **Bisecting K-Means** |
| **Medoid/Median** | **K-Medians** (Manhattan Dist.), **K-Medoids** (PAM-like) |
| **Soft Clustering** | **Fuzzy C-Means** (Probabilistic membership) |
| **Non-Linear** | **Kernel K-Means** (via Spectral Clustering) |
| **Density-Based** | **DBSCAN**, **OPTICS** (Handling noise/outliers) |
| **Hierarchical** | **Agglomerative Clustering** (Ward linkage with Dendrograms) |

### 3. Hyperparameter Tuning & Results
* **Optimal K**: Determined using the **Elbow Method** (Inertia) and **Silhouette Analysis**.
    * *Result*: **K=3** was often found to be the most stable configuration.
* **Evaluation**:
    * **Silhouette Score**: Used to measure cluster separation.
    * **Davies-Bouldin Index**: Used to measure cluster compactness.
* **Key Findings**:
    * Standard **K-Means** provided the most balanced results for general grouping.
    * **DBSCAN** successfully identified outliers (unique/anomalous transfer records).
    * **Hierarchical Clustering** provided visual insights into how subgroups of players merge.

---

## 🧠 Phase 2: Multiclass Classification

In this phase, the continuous target variable `Transfer_fee` was **discretized** into categorical buckets to turn the problem into a classification task.

### 1. Target Engineering (Discretization)
The `Transfer_fee` column was binned into **4 Classes**:
* **Low**: Inexpensive transfers.
* **Medium**: Average market transfers.
* **High**: Expensive transfers.
* **Elite**: Top-tier, record-breaking transfers.

### 2. Models Trained
We trained and tuned the following classifiers to predict which price bucket a player belongs to:
* **Decision Tree Classifier** (interpretable rules).
* **K-Nearest Neighbors (KNN)**.
* **Naive Bayes (Gaussian)**.
* **Support Vector Machines (SVM)**.

### 3. Model Evaluation
Models were evaluated using **Accuracy**, **Precision**, **Recall**, and **F1-Score**, along with **Confusion Matrices**.

| Model | Performance Note |
| :--- | :--- |
| **Decision Tree** | High interpretability; captures non-linear splits well. |
| **SVM** | Robust for higher-dimensional separation but computationally heavier. |
| **KNN** | Good for finding similar player profiles but sensitive to outliers. |

* **Champion Model**: The model with the highest F1-score on the test set was selected as the final predictor.

---

## 🛠️ Technologies & Libraries Used
The project is implemented in Python using a Jupyter Notebook environment.

* **Python 3.x**
* **Scikit-Learn**: Main library for Clustering (KMeans, DBSCAN, Spectral) and Classification (SVM, Trees).
* **Scikit-Fuzzy (skfuzzy)**: Used for Fuzzy C-Means clustering.
* **Pandas & NumPy**: Data manipulation and vector calculations.
* **Matplotlib & Seaborn**: Visualization (Scatter plots, Heatmaps, Dendrograms).

---

## 📂 Project Structure
├── football_clear.csv
├── project3.ipynb
├── ClusteringClassification.pdf
└── README.md

---

## 📊 How to Run
1.  Ensure you have Python installed with the required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn scikit-fuzzy
    ```
2.  Place the `football_clear.csv` file in the same directory as the notebook.
3.  Open `project3.ipynb` in Jupyter Notebook or VS Code.
4.  Run all cells. The notebook will:
    * Load and scale the data.
    * Perform clustering (K-Means family, DBSCAN, Hierarchical) and plot results.
    * Discretize the transfer fee.
    * Train classifiers and output the confusion matrix and accuracy scores.

---

**Author:** Sasan Nikjoo
**Course:** Data Mining Project-phase 3