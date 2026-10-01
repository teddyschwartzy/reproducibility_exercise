# Diabetes Risk Factor Analysis: A Study in Reproducibility

## Project Overview

This project examines several common clinical risk factors for diabetes, including glucose, BMI, blood pressure, age, and insulin levels. The goal is to identify differences between diabetic and non-diabetic patients while demonstrating a reproducible data science workflow.

This project was completed as part of **HSE 751: Programming for Health Data Science**. In addition to performing statistical and machine learning analyses, the notebook emphasizes reproducibility through standardized data cleaning, fixed random seeds, modular functions, and clear documentation.

---

## Software and Dependencies

The analysis can be run in **Google Colab**, **Jupyter Notebook**, or **VS Code**.

### Required Libraries

- pandas
- numpy
- matplotlib
- seaborn
- scipy
- scikit-learn

All package versions are listed in the included `requirements.txt` file to help ensure consistent results across environments.

### Installation

Install required packages using:

```bash
pip install -r requirements.txt
```

If running in Google Colab, the notebook will install any missing dependencies automatically.

---

## Running the Analysis

To reproduce the results:

1. Download or clone the repository.
2. Confirm that `Example Dataset_Diabetes.csv` is located in the project folder.
3. Open `Full_Diabetes_Reproducibility_Notebook.ipynb`.
4. Select **Runtime → Restart session and run all** in Colab (or restart the kernel and run all cells in Jupyter).
5. The notebook will automatically:
   - Load and validate the data
   - Clean missing clinical values
   - Generate descriptive statistics and visualizations
   - Perform hypothesis testing
   - Train and evaluate a logistic regression model
   - Verify reproducibility outputs

---

## Workflow Summary

Several steps were included to improve reproducibility and consistency.

### Data Cleaning

Some clinical variables contained values of zero that are not biologically realistic, such as glucose and BMI measurements. These values were treated as missing data and replaced using median imputation through a reusable cleaning function.

### Data Validation

The notebook validates column names, data types, and required variables before analysis begins to help prevent errors caused by unexpected changes in the dataset.

### Statistical Analysis

The analysis includes:

- Descriptive statistics
- Independent-samples t-tests
- Chi-square tests
- Correlation analysis

These methods were used to evaluate relationships between patient characteristics and diabetes status.

### Machine Learning

A logistic regression model was developed to predict diabetes outcomes. Model performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score

### Reproducibility Controls

A fixed random seed (`RANDOM_STATE = 42`) was applied throughout the notebook to ensure consistent train-test splits, model training, and bootstrap sampling across runs.

---

## Expected Outputs

Running the notebook will generate:

1. Summary statistics describing the patient population
2. Histograms and boxplots for key clinical variables
3. A correlation heatmap
4. Statistical test results and p-values
5. Logistic regression performance metrics
6. Bootstrap estimates and reproducibility checks

---

## Assumptions and Limitations

- This dataset is observational, so findings indicate associations rather than causation.
- Median imputation was used for biologically impossible values and assumes these observations represent missing data.
- Results are based on the provided dataset and may not generalize to other populations.
- Logistic regression was selected as a simple and interpretable predictive model; more advanced models may produce different performance results.

---

## Repository Structure
- Full_Diabetes_Reproducibility_Notebook.ipynb
- Example Dataset_Diabetes.csv
- Reproducibility Summary.txt
- requirements.txt
- README.md

### File Descriptions

- `Full_Diabetes_Reproducibility_Notebook.ipynb` - Complete analysis workflow and results
- `Example Dataset_Diabetes.csv` - Source dataset
- `Reproducibility Summary.txt` - Summary of reproducibility testing and validation
- `requirements.txt` - Required Python packages
- `README.md` - Project documentation
