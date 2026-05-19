# Data-Preprocessing-Correlation-Analysis-Pipeline
Managed heterogeneous and incomplete macroeconomic datasets revealing several correlations
This project implements a reproducible Python pipeline for preprocessing macroeconomic and ICT-related panel data and performing statistical correlation analysis with significance testing.
The workflow is designed for data-constrained environments typical in development economics, emphasizing robustness, transparency, and analytical clarity.

🔍 Overview
The script performs the following key steps:

Data ingestion from Excel
Missing value handling
Outlier detection and removal (IQR method)
Data normalization (standardization)
Descriptive statistics (before & after cleaning)
Correlation analysis
Statistical significance testing (p-values)


📁 Input & Output
Input

Excel file:

Dynamic_Table_m.xlsx

Output

Cleaned and normalized dataset:

processed_datam.xlsx


⚙️ Methodology
1. Data Cleaning

Numeric columns are automatically detected
Missing values are handled using mean imputation
Outliers are removed using the Interquartile Range (IQR) method:

Lower bound: Q1 − 1.5 × IQR
Upper bound: Q3 + 1.5 × IQR



👉 This ensures robustness in noisy macroeconomic datasets

2. Descriptive Statistics
The pipeline computes summary statistics:

Before outlier removal
After outlier removal

This allows comparison of:

Mean shifts
Variance reduction
Distribution changes


3. Data Normalization

Standardization using StandardScaler
Mean = 0, Standard deviation = 1

👉 Ensures comparability across variables such as:

FDI
Broadband indicators
Macro variables


4. Correlation Analysis
The script computes:
✅ Pearson correlation matrix
✅ P-values for statistical significance
Variables included:

FDI
Mobile broadband
Fixed broadband
4G deployment
Inflation rate
Unemployment
ICT index


5. Statistical Significance

P-values are calculated using Pearson correlation tests
Results are formatted as:

correlation (p-value) ***

Where:

*** indicates statistical significance at 1% level (p < 0.01)


📈 Example Output
0.75 (p=0.002) ***
0.45 (p=0.120)

👉 Combines effect size + statistical confidence

🧠 Key Features

✔ Fully reproducible workflow
✔ Robust handling of missing data and outliers
✔ Designed for small, heterogeneous panel datasets
✔ Integrates data cleaning + statistical inference
✔ Clear, interpretable output for policy analysis


🛠️ Technologies Used

Python
pandas
NumPy
scikit-learn
SciPy


🚀 Use Cases
This pipeline is suitable for:

Development economics research
Digital infrastructure analysis
Policy-oriented data analysis
ICT and macroeconomic studies
Academic or institutional research workflows


⚠️ Notes

Ensure column names match expected variables:

FDI, Mobile_BB, Fixed_BB, 4G deployment, inflation rate, unemployment, ICT index


The dataset should contain sufficient observations for reliable correlation estimates


📌 Future Improvements

Add visualization (heatmaps, pairplots)
Extend to panel econometric models
Integrate causal inference methods
Add automated reporting


👤 Author
Elias Aravantinos
PhD Researcher – Digital Infrastructure Economics, AI & Policy Analysis

🔗 Related Work
This pipeline supports broader research on:

Economic growth forecasting
Digital competitiveness and trade
ICT diffusion in developing economies
