# Machine_Learning_Project

## Overview of the Analysis
The purpose of the analysis was to create a regression model that can predict poverty based on Demographic, Economic, Education, and Housing data. The meta data was based on the American Community Survey (5 year estimate data profiles) from data.census.gov. We gathered data from the following tables: DP02, DP03, DP04, DP05 for years 2018- 2022.

## Results

* Data Preprocessing
    * Target Variable:
      * `Poverty` - Percentage of poverty based on county/state
    * Feature Variables:
      * `GEO_ID`, `State`, `County`— Identification columns
      * `Below_9th_grade`, `9_12th_grade`, `High_School_Grad`, `Some_College`, `Associate's_degree`, `Bachelor's_degree`, `Graduate_degree` - Education Level Data
      * `Population (16+)`, `Employed`, `Median Household Income`, `Per capita Income`, `Unemployment Rate`, `Professional (Occupation)`, `Service (Occupation)`, `Sales (Occupation)`, `Construction (Occupation)`, `Production (Occupation)`, `Salary, (Class)`, `Gov't (Class)`, `Self-employed (Class)`, `Fam-unpaid (Class)`, `Child-poverty` - Economic Data
      * `Median Home value`, `Median Mortgage`, `Median Rent` - Housing Data
      * `Total Population`, `White`, `Black`, `American Indian`, `Asian`, `Pacific Islander`, `Hispanic/Latino` - Demographic Data
      * `Year` - Year of Census

    * Removed Variables:
      * `GEO_ID`, `County`, and `Year` were removed because they were Identification columns which did not aid with predictive information.
      * `Child -Poverty`,`Median Mortgage`, `Median Rent`, `Per Capita Income`, `Employed`/`Popultion 16+`/ `Total Population` (Chose one) removed due to high correlation to avoid redundancy or multicollinearity.
      *![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/635ca989-0f0d-447c-bc31-2c86eba2347e)


* Compiling, Training, and Evaluating the Model

   * Gustavo Models
      * Random Forest
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/86f988aa-c887-4961-b89f-1e75a7c00ad2)
      * Neural Network Model 
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/50ea3957-0391-4f1f-a117-7f60b122c73d)
       
   * Joshua Models
      * Linear Regression
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/2734d6b5-551f-4a9c-8b42-7b6e55512cb0)

         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/3effcb06-87ea-4da0-8c26-f7867212dd08)

      * Decision Tree
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/1d1e44db-8476-42e5-9b85-5f9cc7d916db)

         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/3bd74f60-3cb9-4d8f-a764-fa1d447807c0)

      * Random Forest
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/4ed766b8-d32b-49d9-9a37-042f576fe835)

         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/9768e333-d087-4d25-b386-53b13b1cfdff)

           
## Optimizing the Random Forest Model
We ultimately decided to go with the random forest models as it provided us with the highest R-squared value and smallest MSE and RMSE values. To further optimize our random forest model, we utilized the `GridSearchCV` module from the `SKLearn` Python library. Our code to run this is below.

![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/b18afee1-4e27-46a9-954c-cbcad88e5623)

![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/75a91fc0-1274-4f55-b061-188bb775b719)

With the results that we received from the grid search, we ran the random forest based on those parameters and the following values got slightly better.

Optimized Random Forest:
![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/e8ba6653-7ca6-41d3-8dbe-d02604725e25)

![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/e5dbc116-6871-4a3f-b53a-64964c7f5a09)


## Feature Importance
![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/151583321/820e4b29-f67b-424c-b59d-a5f07ed70bfc)


## Summary
The machine learning model developed with the highest accuracy from our optimization attempts was the Random Forest Model, achieving an R² score of 0.8558, surpassing our target of 0.80. To enhance the model's performance, we omitted features of low importance and predictability, such as those that were subsets of one another, like child-poverty compared to poverty, and median household income compared to income per capita.

Our focus was on regression models due to our problem, which involved predicting continuous poverty rates rather than classification tasks. Improvements to our model can be achieved by gathering more data from the Census Survey that may provide better predictors for poverty rates.
