# INTRODUCTION

**OBJECTIVE**: The goal of this project was to determine the appropriate model that could be used predict the income based on work experience for women living in townhouses in an urban area.

**DATASET**: This dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/stealthtechnologies/regression-dataset-for-household-income-analysis). It had 14 columns and 10001 observations in the dataset. 

# METHODOLOGY

**MODEL SELECTION**: Three models were tested: *Polynomial Regression, Random Forest and Huber Regression*. Based on the performance analysis done using mean absolute error, Huber Regression performed the best on the dataset both with and without outliers.

**DATA PREPROCESSING**:
* The data was subsetted to only including observations where the gender was female, the participant owned a townhouse and the location of the townhouse was in an Urban area. The remaining data had 397 observations.

* The models were only trained with one feature which was work experience. The target was Income.

* The data was split into both the training and test sets with 20% randomly selected to test the 3 models.


# RESULTS

**MODEL PERFORMANCE**: 
The mean income was: `547480.53`

The baseline mae was:`810373.13`

The training with outliers for Polynomial Regression resulted `682265.20`

The training with outliers for Random Forest resulted `748880.06`

The training with outliers for Huber Regressor resulted `313004.78`

Further analysis to examine why Huber Regression did better than Random Forest resulted in hyperparameter tuning for the random forest model. The mae after hyper parameter tuning resulted in an mae: `745611.24`

Residual Analysis also performed on the Huber Regressor model to determine the outliers. There were 3 ouliers in the dataset.

Standardization was then performed on the dataset and then outliers were removed from the dataset. The Huber Regression and Random Forest models were then trained without the outliers.

The Huber Regression without Outliers resulted in an mae `312998.84`
The Random Forest without Outliers resulted in an mae `443849.07`

# CONCLUSION

**PERFORMANCE**: The Huber Regression model had the best MAE before and after removing outliers. 

**ROBUSTNESS**: Huber Regression is robust towards outliers which made it an ideal choice for this dataset. 

**FUTURE WORK**: 
* More features can be added to train the model.
* The model can be deployed. 