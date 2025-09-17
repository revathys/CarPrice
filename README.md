# CarPrice

**Business Understanding**
The objective of this project is to create an analytic model that predicts the resale value of cars based on various features. 
The questions that will be answered as part of this model is:
  * What are the features affecting the sale price of a used car?
  * What is the predicted sales price for the car?

**Data Understanding**

* The data shared has 426880 rows and 18 features
* Of these features, 14 are categorical and only 8 are numeric 
* The price seems to have outliers and the top 1% needs to be filtered out.
* The percentage of missing data for the below fields make them unusable.
  * cylinders:	41.622470
  * VIN:	37.725356
  * drive:	30.586347
  * paint_color:	30.501078
  * type:	21.752717
* The percentage of missing data for the below fields make them unusable. Since they affect the price, fill the missing values with 'Missing'
  * size:	71.767476
  * condition:	40.785232
* The below categorical features have too many unique values and need to be removed.
  * VIN	118246
  * region	404
  * state	51
* The below categorical features have too many unique values and so the top 20 needs to be maintaind and rest will be put under 'Other'
  *   model	29649
  *   manufacturer	42
* From the correlation matrix, the odometer reading does not seem to have much of an affect on the price

**Data Preparation**
  * Remove price outliers and select the data in the 99th percentile.
  * Drop all the columns mentioned above
  * Drop all rows with null values
    
**Data Modeling**
 * Scale the numerical features
 * Encode the categorical features
 * Split the data to test and train
 * Cross validate with  Ridge Regression, using GridSearchCV to find best alpha
 * Analyse the coefficients

**Evaluation**


**Findings**

 * Newer cars are priced higher(~6200 more per year)
 * Diesel with manual transmission can be priced highest
 * Gas with other transmission can be priced higher than gas with manual transmission
 * Diesel with other transmission significantly reduces value
 * Electric transmission manual also lowers cost, but not as much as Diesel with other transmission

   
  


