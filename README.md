[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1K6XZ34QXj2pufO1jCqqPRTy21hOlnbAf?usp=sharing)

# Diabetes Risk Factor Analysis: A Study in Reproducibility

## Project Overview
This project evaluates clinical risk factors—specifically blood glucose, BMI, and blood pressure—to identify their association with diabetes outcomes. Developed as part of the **HSE 751 - Programming for Health Data Science** curriculum, the primary goal of this repository is to demonstrate a transparent, modular, and fully reproducible computational workflow.

Rather than a linear script, this project utilizes a **configuration-driven pipeline**. This ensures that the analysis can be replicated exactly across different environments and easily extended to include new clinical features without altering the underlying core logic.

## Software & Dependency Requirements
To ensure consistent results, the following Python environment is required. We recommend using **Google Colab**, **Jupyter Notebook**, or **VSCode**.

### Required Libraries:
*   `pandas` (v2.0.3+) — Data manipulation and schema validation.
*   `numpy` (v1.24.3+) — Numerical operations and stochastic control.
*   `matplotlib` (v3.7.1+) & `seaborn` (v0.12.2+) — Publication-quality clinical visualizations.
*   `scipy` (v1.10.1+) — Inferential statistical testing.
*   `scikit-learn` (v1.2.2+) — Predictive modeling and validation.

**Installation:**
All dependencies are handled within the notebook. To install specific versions, uncomment the `!pip install` line in the setup section of the notebook.

## Execution Guide
To reproduce the analysis and obtain the results presented in the final synthesis:

1.  **Clone the Repository:** Download all files into a single local directory or clone via Git.
2.  **Data Setup:** Ensure the dataset `Example Dataset_Diabetes.csv` is located in the root directory.
3.  **Run the Notebook:** 
    *   Open `Full_Diabetes_Reproducibility_Notebook.ipynb`.
    *   Navigate to **Runtime $\rightarrow$ Restart session and run all**.
    *   The notebook will automatically verify the environment, validate the data schema, and execute the full analytical pipeline.

## Workflow Architecture
This project implements several high-level data science best practices:

*   **Configuration-Driven Design:** A central `CONFIG` dictionary controls all variables, feature selections, and statistical thresholds.
*   **Modular Refactoring:** Logic is decoupled into specialized functions (e.g., `clean_clinical_data()`, `run_inferential_stats()`), preventing code duplication and improving auditability.
*   **Clinical Data Validation:** The pipeline identifies "biological impossibilities" (e.g., a Glucose level of 0) and implements **Median Imputation** to prevent biasing the results.
*   **Predictive Modeling:** Beyond descriptive statistics, the project implements a **Logistic Regression** model to predict diabetes outcomes, utilizing a train/test split for rigorous validation.

## Expected Outputs
Upon successful execution, the notebook produces:
1.  **Clinical Profiles:** A descriptive summary of the patient cohort.
2.  **Risk Visuals:** Distributions and boxplots showing the separation between diabetic and non-diabetic groups.
3.  **Correlation Matrix:** A Pearson heatmap identifying linear associations between risk factors.
4.  **Statistical Proof:** P-values from t-tests and Chi-Square tests indicating significance.
5.  **ML Metrics:** Model accuracy, precision, recall, and F1-score for diabetes prediction.
6.  **Reproducibility Evidence:** A fixed random sample and bootstrap mean of BMI.

## Assumptions & Limitations
*   **Observational Data:** This analysis identifies correlations and associations; it does not establish a causal link between risk factors and diabetes.
*   **Imputation Strategy:** Median imputation was used for missing biological values. While robust, this assumes the data is Missing At Random (MAR).
*   **Generalizability:** Results are based on the provided dataset and may not be generalizable to all global populations.

## Repository Structure
*   `Full_Diabetes_Reproducibility_Notebook.ipynb` — The complete analytical pipeline.
*   `Example Dataset_Diabetes.csv` — The source clinical data.
*   `Reproducibility_Summary.md` — A detailed validation report of the workflow.
*   `requirements.txt` — A list of pinned library versions for environment mirroring.
*   `README.md` — This project documentation.
