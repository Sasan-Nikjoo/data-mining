# Football Player Data Mining & Analysis Project

## 📌 Project Overview
This project involves the comprehensive exploration, preprocessing, and analysis of a football player transfer dataset (`football.csv`). The primary goal is to transform raw, unreliable data into a clean, high-quality dataset suitable for modeling, and to identify key factors influencing player market values and transfer fees.

The project is structured according to standard Data Mining phases, focusing on **Data Quality Analysis**, **Preprocessing**, and **Exploratory Data Analysis (EDA)**.

---

## 🚀 Key Features & Methodology

### Phase 1: Data Exploration & Initial Analysis
- **Data Loading & Structure Review**: Analysis of 4,700 rows and 10 columns including `Name`, `Position`, `Age`, `Team_from`, `League_from`, `Team_to`, `League_to`, `Season`, `Market_value`, and `Transfer_fee`.
- **Descriptive Statistics**: Identification of data distribution, mean, standard deviation, and extreme values.
- **Data Visualization**:
  - **Histograms** to analyze the distribution of numerical features (Age, Market Value, Fees).
  - **Box Plots** to identify outliers.
  - **Scatter Plots & Heatmaps** to analyze correlations between variables.

### Phase 2 & 3: Data Preprocessing & Cleaning
The raw data initially had significant quality issues (approx. 28% incompleteness and severe outliers). The following cleaning steps were implemented:

| Metric | Initial Score | Final Score | Action Taken |
| :--- | :--- | :--- | :--- |
| **Completeness** | 71.9% | **100%** | Imputed 1,321 missing `Market_value` records using the **Median** value grouped by player position. |
| **Accuracy** | 98.0% | **100%** | Removed logical errors and outliers in `Age` (e.g., Age=288, Age=0) and converted data types to integers. |
| **Validity** | 92.8% | **100%** | Removed 336 records with non-standard `Season` formats or invalid/unknown `League` names. |

### Phase 4: Final Analysis & Results
Following the cleaning process, a final analysis was conducted to answer key project questions:

* **Which features have the most impact?**
    * **Market Value** and **Season (Inflation)** were identified as the most critical determinants of a player's transfer fee.
* **Feature Relationships:**
    * **Age** exhibits a non-linear relationship with value (value increases until peak performance age and then declines).
* **Correlation Strategy:**
    * High correlation columns were prioritized to reduce dimensionality while maintaining information density.

---

## 🛠️ Technologies & Libraries Used
The project is implemented in Python using a Jupyter Notebook environment.

* **Python 3.x**
* **Pandas**: Data manipulation and aggregation.
* **NumPy**: Numerical operations.
* **Matplotlib & Seaborn**: Advanced data visualization (Heatmaps, Scatter plots, Distribution plots).
* **Scikit-Learn**: Used for encoding, scaling, and dimensionality reduction techniques (PCA, t-SNE).

---

## 📂 Project Structure
├── football.csv
├── project1.ipynb
├── Data Exploration and Initial Analysis.pdf
└── README.md

---

## 📊 How to Run
1.  Ensure you have Python installed with the required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
2.  Place the `football.csv` file in the same directory as the notebook.
3.  Open `project1.ipynb` in Jupyter Notebook or VS Code.
4.  Run all cells sequentially to reproduce the analysis and visualizations.

---

## 📝 Conclusion
By applying rigorous data mining techniques, the dataset was successfully transformed from an **"Unreliable"** state to a **"Clean and Ready for Modeling"** state. The analysis highlighted that while intrinsic player quality (Market Value) drives price, external economic factors (Season/Inflation) play a massive role, necessitating careful feature engineering for any future predictive modeling.

---

**Author:** Sasan Nikjoo
**Course:** Data Mining Project-phase 1