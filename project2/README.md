# Frequent Pattern Mining & Association Rule Analysis

## 📌 Project Overview
This project focuses on discovering recurring patterns and extracting meaningful association rules from transaction data. The core objective is to compare the performance and accuracy of a **Manually Implemented Algorithm (Apriori)** against a **Library-Optimized Algorithm (FP-Growth)**.

[cite_start]The project is divided into two phases, covering data preparation, frequent itemset mining, and advanced rule evaluation using statistical metrics[cite: 2, 4, 10].

---

## 🚀 Key Features & Methodology

### Phase 1: Frequent Itemset Mining (Apriori vs. FP-Growth)
In this phase, raw transaction data was processed to identify itemsets that appear together frequently (Support > 20%).

* **Data Preprocessing**:
    * Dataset consists of **999 transactions** and **16 unique items** (e.g., Apple, Bread, Chocolate).
    * Converted raw boolean data into a transaction list format suitable for mining algorithms.
* **Implementation Details**:
    * [cite_start]**Manual Apriori**: Implemented from scratch with **candidate generation** and **pruning** strategies to optimize search space[cite: 3, 7].
    * [cite_start]**Library FP-Growth**: Implemented using the `mlxtend` library to construct an FP-Tree for efficient mining[cite: 8].
* **Comparison Results**:
    * **Accuracy**: Both algorithms identified exactly **22 frequent itemsets**, proving the correctness of the manual implementation.
    * **Performance**: Execution times were comparable (~0.009s), with `Chocolate`, `Butter`, and `Yogurt` identified as the most frequent items.

### Phase 2: Association Rule Extraction & Evaluation
[cite_start]This phase focused on generating rules from the frequent itemsets and validating their strength using multiple metrics beyond just Confidence[cite: 11].

* **Rule Generation**: Applied a **Minimum Confidence of 50%**.
* **Advanced Evaluation Metrics**:
    * **Lift**: To measure the strength of the rule compared to random chance.
    * **Chi-Square ($\chi^2$)**: To test the statistical significance of the correlations.
    * **Kulczynski**: To calculate the average conditional probability of the rules.

---

## 📊 Key Findings & Results

Upon analyzing the generated rules, the following insights were derived:

| Metric | Result | Insight |
| :--- | :--- | :--- |
| **Total Rules Found** | **3** | Only 3 rules met the strict confidence threshold (>0.5). |
| **Top Association** | **Milk $\leftrightarrow$ Chocolate** | **Lift: 1.24** | Indicates a positive correlation; customers buying milk are 24% more likely to buy chocolate. |
| **Statistical Validity** | **$\chi^2 \approx 27.7$** | The high Chi-Square value confirms this relationship is **statistically significant** and not due to chance. |
| **Other Strong Rules** | **Ice Cream $\rightarrow$ Butter** | **Lift: 1.20** | A strong dependency was also found between Ice Cream and Butter purchases. |

---

## 🛠️ Technologies & Libraries Used
The project is implemented in Python using a Jupyter Notebook environment.

* **Python 3.x**
* **Pandas**: Data manipulation and DataFrame management.
* **Mlxtend**: Used for the FP-Growth algorithm implementation.
* **NumPy & Math**: Used for manual calculation of evaluation metrics (Chi-Square, Lift).
* **IPython Display**: Used for generating HTML-based rich reports within the notebook.

---

## 📂 Project Structure
├── dataset.csv
├── project2.ipynb
├── pattern recognition.pdf
└── README.md

---

## 📊 How to Run
1.  Ensure you have Python installed with the required libraries:
    ```bash
    pip install pandas numpy mlxtend
    ```
2.  Place the `dataset.csv` file in the same directory as the notebook.
3.  Open `project2.ipynb` in Jupyter Notebook or VS Code.
4.  Run all cells sequentially. The notebook will:
    * Clean the data.
    * Run both Apriori and FP-Growth.
    * Display a comparison table.
    * Generate and evaluate association rules with a final HTML report.

---

## 📝 Conclusion
The project successfully demonstrated that manual implementation of **Apriori** yields identical results to the optimized **FP-Growth** library, validating the logic of candidate pruning. The advanced analysis in Phase 2 revealed that high-frequency items like **Milk and Chocolate** share a strong, non-random purchasing relationship, supported by a high **Chi-Square** score of 27.69.

---

**Author:** Sasan Nikjoo
**Course:** Data Mining Project-phase 2