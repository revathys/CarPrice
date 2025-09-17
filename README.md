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

Mean Squared Error: 83478959.60
Root Mean Squared Error: 9136.68
Mean Price for cars: 12589.87

Top 20 feature coefficients
cat__condition_fair       -5497.379166
cat__type_truck            5415.876353
cat__fuel_electric         5069.398747
cat__condition_new         4998.183533
cat__condition_like new    4912.634974
cat__title_status_lien     4714.199370
cat__fuel_diesel           4640.581748
cat__model_1500           -4547.079730
cat__condition_salvage    -4446.299192
cat__type_wagon           -4361.225029
cat__type_sedan           -4075.244912
cat__fuel_gas             -3870.455070
cat__fuel_hybrid          -3805.436674
cat__model_2500           -3802.856788
cat__manufacturer_ram      3767.905419
cat__type_convertible      3722.337835
cat__type_hatchback       -3565.491566
cat__model_wrangler        3286.683674
cat__type_mini-van        -3198.031480
cat__type_offroad          3169.981082

**Findings**

**Features associated with higher prices**

1. Vehicle Type

  - Trucks (+$5,416), convertibles (+$3,722), and offroad vehicles (+$3,170) are valued higher.

2. Fuel Type

  - Electric cars (+$5,069) and diesel cars (+$4,641) command premiums over gas.

3. Condition

  - Cars in new (+$4,998) or like new (+$4,913) condition are priced much higher.

4. Title Status

  - Cars with a lien (+$4,714) appear slightly more expensive (may reflect newer or financed cars).

5. Brand and model

  - RAM (+$3,768) and Wrangler (+$3,287) have strong resale value.



**Features associated with lower prices**


1.   Condition

    - Cars in fair (-$5,497) or salvage (-$4,446) condition lose significant value.


2.   Car Type

    - Wagons (-$4,361), sedans (-$4,075), hatchbacks (-$3,565), and minivans (-$3,198) are less desirable.

3.   Fuel

    - Gas (-$3,870) and hybrid (-$3,805) cars are priced lower compared to electric/diesel.

4.   Model

    - 500 (-$4,547) and 2500 (-$3,803) models 
