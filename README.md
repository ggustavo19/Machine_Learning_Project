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
      * Random Forst best Result
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/86f988aa-c887-4961-b89f-1e75a7c00ad2)
      * Neural Network Model 
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/50ea3957-0391-4f1f-a117-7f60b122c73d)
       
   * Joshua Models
      * Linear Regression
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/567468a5-dfdc-4989-9f6f-cc0184155866)
      * Decision Tree
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/6e4cdc8f-d608-4c66-8200-6e0b3fcd0494)
      * Random Forest
         * ![image](https://github.com/ggustavo19/Machine_Learning_Project/assets/152371383/d579cdc6-5c4f-4c85-aef1-f228f23fbade)

   

## Summary
The machine learning model developed with the highest accuracy out of our seperate optimizing attempts was the Random Forest Model with an R^2 score of 0.8558% which met the .80 target. 
