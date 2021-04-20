# Project 2:  Ames Housing Data and Kaggle Challenge

Author: Artem Lukinov

### [](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#contents)Contents:

-   [Problem Statement](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#Problem-Statement)
-   [Executive Summary](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#Executive-Summary)
-   [Data Dictionary](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#Data-Dictionary)
-  [The Modeling Process](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#The-Modeling-Process)
-   [Conclusions and Recommendations](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#conclusions-and-recommendations)

## [](https://https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main)Problem Statement

There are many variables that can affect house prices. Using Ames Housing Data from Kaggle, let's determine the most influential variables and build the best model to predict house sale prices.

## [](https://https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main)Executive Summary

There is a vast variety of possible indicators that might drive house prices up or down. In the given data set for Ames, IA there are over 70 possible indicators that can influence house prices. This information can inform potential buyers of the effect particular features may have on a house price or even help real estate agents with their transactions. Identifying correct predictors of house prices can help both sides orient in the difficult market of real estate.
## [](https://https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main)Data Dictionary

| Column Name | Description |	Data type	|
|--|--|--|
| Garage_Area | Size of garage in square feet | float64 |
| TotRms_AbvGrd | Total rooms above grade (does not include bathrooms) | int64 |
| Liv_SF | Total living area (includes finished basement) | float64 |
| Home_Age | Age of the house (either from year built or year remodeled) | int64 |
| Full_Bath | Full bathrooms above grade | int64 |
| Garage_Cars | Size of garage in car capacity | float64 |
| Garage_Area | Size of garage in square feet | float64 |
| Overall_Qual | Rates the overall material and finish of the house | int64 |

Full data dictionary for the original Ames dataset  [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

## The Modeling Process

1.  The train dataset had all of the columns required to generate and refine the model. The test dataset had all of the same columns except for the target that the Regression model predicted.
2.  While generating the model the following processes were considered:
    -   train-test split was considered at first. However, as the data is split into two files, the entire train data set was ultimately used.
    -   cross-validation was performed on the test set
    -   exploratory data analysis was performed to identify the strongest variables to fit into the model
3.  After reading the data from the train set:
	- column names were renamed for consistency
	- columns with more than 60% missing data were dropped
	- all missing values were cleaned by replacing with np.nan
	- rows with data not containing residential transactions were dropped
4.  Some columns were engineered to combine and amplify values:
- Finished Basement Area columns was made by taking Unfinished Basement Area from Total Basement Area
- Livable Space was calculated by sum of Finished Basement Area and Ground Living Area
- **Price per square foot of living space was considered, but could not be replicated in the test set.**

5. Features were identified by looking at correlation with Sale Price and OLS regression was used, generating a score of 84.5% and cross validation score of 84%. 
## [](https://git.generalassemb.ly/krosaf4eg/dsir-125/tree/master/projects/project-02-main#conclusions-and-recommendations)Conclusions and Recommendations

The linear model created can accurately predict the sale price, but there may be further tweaks to both the data cleaning and the model to improve its effectiveness. The predictions were submitted to Kaggle with the result of RMSE = 37002.80.

There are definitely  ways to improve this metric through further feature engineering, regularization and trying different models.

As of now, the project helped to learn how to implement the basic functionality of linear regression. It was quick to train and produced great results.


