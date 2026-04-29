# COMPAS Bias Audit in Python

## Purpose of the Analysis
This notebook audits fairness and disparate impact in the COMPAS analysis in Python by adding group disparity, intersectional analysis, and error-rate testing to the prediction models.

The goal of the analysis is to:

load and prepare the cleaned COMPAS dataset  
train and evaluate the Logistic Regression and Gradient-Boosted Tree models  
compute AIR, ME, and SMD for race  
compare disparity results across groups and confirm consistency of the calculations  
build an intersectional analysis for race × sex  
identify the worst-group AIR and interpret it  
compute false positive rate (FPR) and false negative rate (FNR) disparities by race  
test FPR and FNR disparities for statistical significance using two-proportion z-tests  
produce a publication-quality grouped bar chart of FPR and FNR by race with Caucasian as the reference group  
write a short compliance memo summarizing findings, metrics used, and limitations  

This analysis helps examine not only predictive performance, but also fairness, subgroup harm, and compliance concerns in a high-stakes setting.

## Python Libraries Used
The notebook uses the following Python libraries:

pandas  
numpy  
matplotlib  
scikit-learn  
statsmodels  
solas-ai / solas_disparity  
warnings  

## What Each Library Is Used For
pandas: loading the dataset, cleaning variables, grouping records, and managing tables  
numpy: numerical operations and metric calculations  
matplotlib: generating the final publication-quality figure  
scikit-learn: preprocessing, train-test split, and model training for Logistic Regression and Gradient-Boosted Tree  
statsmodels: running two-proportion z-tests for FPR and FNR disparities  
solas-ai / solas_disparity: computing legal disparity metrics such as AIR and ME  
warnings: suppressing unnecessary warning messages  

## Instructions for Reproducing the Results
The Python code for this project is written in Jupyter Notebook / Google Colab format.

To reproduce the results:

Open the notebook file:

`Responsible_ML_Assignment_3_individual_hesham.ipynb`

Make sure the cleaned COMPAS dataset used in the analysis is available in the notebook environment.

Make sure the required libraries are installed. If needed, run:

```bash
pip install pandas numpy matplotlib scikit-learn statsmodels solas-ai



