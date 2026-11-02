# Patient Health Records Data Cleaning Project

## Project Overview
This project demonstrates data cleaning and preprocessing techniques using a synthetic Patient Health Records dataset. The goal is to identify and handle missing values and outliers, compare different techniques, and prepare a clean dataset suitable for machine learning practice.

> **Disclaimer:** This is synthetic educational data. It does not represent real patients and must not be used for clinical decisions.

## Dataset
File: `patient_health_records.csv`

- **Rows:** 1,000 patient records
- **Columns:** 9

| Column | Data Type | Description |
|---|---|---|
| `patient_id` | String | Unique identifier for each patient |
| `age` | Numeric | Patient age in years |
| `gender` | Categorical | Male or Female |
| `region` | Categorical | North, South, East, or West |
| `bmi` | Numeric | Body Mass Index |
| `blood_pressure` | Numeric | Systolic blood pressure (mmHg) |
| `cholesterol` | Numeric | Cholesterol level (mg/dL) |
| `glucose` | Numeric | Fasting glucose level (mg/dL) |
| `disease_risk` | Binary | `0` = Low Risk, `1` = High Risk |

The dataset intentionally contains missing values in `age`, `gender`, `region`, `bmi`, `cholesterol`, and `glucose`, along with synthetic extreme values in selected numerical health columns.

## Project Objectives
- Identify missing values and report their count and percentage by column.
- Apply and compare multiple missing-value imputation techniques.
- Detect and treat outliers using Z-score, IQR, percentile capping, and Winsorization.
- Compare dataset statistics before and after outlier treatment.
- Export a cleaned, machine-learning-ready dataset.
- Generate a data profiling report.

## Techniques Covered

### Missing Value Handling
1. **Mean / Median Imputation** — replace missing numerical values with the mean or median.
2. **Most Frequent Imputation** — replace missing categorical values with the most common category.
3. **Missing Indicator + Random Sample Imputation** — add indicator columns to identify originally missing entries, then fill them using random observed values.
4. **KNN Imputer** — estimate missing numerical values using nearby records.
5. **MICE / Iterative Imputer** — iteratively estimate missing numerical values using other variables.

### Outlier Handling
1. **Z-score** — identify extreme observations using standard deviations from the mean.
2. **IQR** — identify observations outside the interquartile-range boundaries.
3. **Percentile Capping** — cap values at selected percentile boundaries.
4. **Winsorization** — cap extreme values rather than removing entire rows.

## Requirements
Install the required Python libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy ydata-profiling
```

For Jupyter Notebook, you can run:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn scipy ydata-profiling
```

## How to Run
1. Download or place `patient_health_records.csv` in your Jupyter Notebook project folder.
2. Open Jupyter Notebook or VS Code.
3. Import the required libraries.
4. Run the notebook cells in order:
   - Load and inspect the dataset.
   - Generate the missing-value summary.
   - Apply each imputation method separately.
   - Apply and compare outlier-handling methods.
   - Create the final cleaned dataset.
   - Export the cleaned CSV and profiling report.

Example to load the dataset:

```python
import pandas as pd

df = pd.read_csv("patient_health_records.csv")
print(df.shape)
display(df.head())
```

## Expected Outputs
- Missing-value count and percentage report.
- Imputation comparison table.
- Outlier treatment comparison.
- Before-vs-after summary statistics and boxplots.
- `patient_health_records_cleaned.csv`
- `patient_health_profiling_report.html`

## Notes
- Keep `patient_id` as an identifier; it should not be used as a numeric feature.
- Keep `disease_risk` as the target variable and do not impute or outlier-treat it.
- The final imputation and outlier methods should be justified using the comparison results.
- For machine learning, fit preprocessing steps on the training data only to avoid data leakage.

## Author
Add your name, course, institution, and submission date here.
