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
  * size:	71.767476
  * cylinders:	41.622470
  * condition:	40.785232
  * VIN:	37.725356
  * drive:	30.586347
  * paint_color:	30.501078
  * type:	21.752717
* The below categorical features have too many unique values and need to be removed.
  * VIN	118246
  * model	29649
  * region	404
  * state	51
  * manufacturer	42
* From the correlation matrix, the odometer rearing does not seem to have much of an affect on the price

  **Data Preparation**
  Remove price outliers and select the data in the 99th percentile.
  Drop all the columns mentioned above
  Drop all rows with null values
  
  


