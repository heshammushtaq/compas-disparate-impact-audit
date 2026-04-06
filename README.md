# COMPAS Bias Audit in Python

## Purpose of the Analysis
This notebook audits fairness and disparate impact in the COMPAS analysis in Python by adding group disparity, intersectional analysis, and error-rate testing to the prediction models.

The goal of the analysis is to:

load and prepare the cleaned COMPAS dataset  
train and evaluate the Logistic Regression and Gradient-Boosted Tree models  
compute AIR, ME, and SMD for race  
compute AIR, ME, and SMD for sex  
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


## Results
The analysis produced fairness and disparate impact results for both the Logistic Regression and Gradient-Boosted Tree models on the cleaned COMPAS dataset.

AIR, ME, and SMD were computed separately for race and sex. The results showed meaningful disparities in selection rates and score distributions across groups. By sex, female defendants had lower selection rates than male defendants, with AIR values below the 0.80 threshold. By race, African-American defendants showed meaningful score disparities, with large SMD values in both models.

The intersectional analysis showed that the worst-group AIR in both models was for **Caucasian / Female**. In the Logistic Regression model, the worst-group AIR was **0.207**. In the Gradient-Boosted model, the worst-group AIR was **0.775**. This shows that harms can become clearer when race and sex are examined together rather than separately.

FPR and FNR disparities were also computed by race. African-American defendants had higher false positive rates than Caucasian defendants in both models, and these differences were statistically significant. This means African-American defendants were more likely to be classified as high risk when the observed outcome was negative. Caucasian defendants had higher false negative rates, meaning they were more likely to be classified as low risk when the observed outcome was positive.

Overall, the results show that the models raise meaningful fairness concerns and that subgroup and intersectional analysis are important for identifying disparity patterns in high-stakes settings.
