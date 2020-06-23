# Car_Price_Prediction

**Still working on this by improving the result, insights and further deployment. Do read this file and check the conclusion to get an accurate idea on my project and what are its limitations.**

The solution is divided into the following sections:

1. Exploratory Data Analysis
2. Feature Engineering
3. Data Preprocessing
4. Model Building and Evaluation

## Problem Statement

## Data Description

* Car_ID - Unique id of each observation (Interger)
* Symboling - Its assigned insurance risk rating, A value of +3 indicates that the auto is risky, -3 that it is probably pretty safe.(Categorical)
* carCompany - Name of car company (Categorical)
* fueltype - Car fuel type i.e gas or diesel (Categorical)
* aspiration - Aspiration used in a car (Categorical)
* doornumber - Number of doors in a car (Categorical)
* carbody - body of car (Categorical)
* drivewheel - type of drive wheel (Categorical)
* enginelocation- Location of car engine (Categorical)
* wheelbase - Weelbase of car (Numeric)
* carlength - Length of car (Numeric)
* carwidth - Width of car (Numeric)
* carheight - height of car (Numeric)
* curbweight - The weight of a car without occupants or baggage. (Numeric)
* enginetype - Type of engine. (Categorical)
* cylindernumber- cylinder placed in the car (Categorical)
* enginesize - Size of car (Numeric)
* fuelsystem - Fuel system of car (Categorical)
* boreratio - Boreratio of car (Numeric)
* stroke - Stroke or volume inside the engine (Numeric)
* compressionratio - compression ratio of car (Numeric)
* horsepower - Horsepower (Numeric)
* peakrpm - car peak rpm (Numeric)
* citympg - Mileage in city (Numeric)
* highwaympg - Mileage on highway (Numeric)
* price(Dependent variable) - Price of car (Numeric)

## EDA

* From the info we can see that it is a very small dataset.
* We can infer that the distribution of the plot is skewed.

### Some Insights

From the plot we can infer the following:

* Gas vehicles are found to be more highly priced compared to diesel.
* mpfi fuelsystem is found more in high end vehicles, so we can assume the quality of this system to be good.
* sedan and convertibles are more costly than other car bodies.
* rwd drivewheel is found more in costly vehicles.
* Only a few rear engined vehicles are seen. We would need to check on the reason.
* Greater the number of cylinders, higher the price of the car.

### Plot Distribution:

* Almost all of the features are positively correlated to the price variable except for highwaympg, citympg, compressionratio as these variables are negatively correlated.

* It is nice to see a gaussian distribution in most of the features as normal distribution can fit the algorithm easily.

### Correlation:

* Correlation of price with independent variables: Price is highly (positively) correlated with wheelbase, carlength, carwidth, curbweight, enginesize, horsepower (note that all of these variables represent the size/weight/engine power of the car).

* Price is negatively correlated to citympg and highwaympg (-0.70 approximately). This suggest that cars having high mileage may fall in the 'economy' cars category, and are priced lower (think Maruti Alto/Swift type of cars, which are designed to be affordable by the middle class, who value mileage more than horsepower/size of car etc)

* Correlation among independent variables: Many independent variables are highly correlated (look at the top-left part of matrix): wheelbase, carlength, curbweight, enginesize etc. are all measures of 'size/weight', and are positively correlated
Therfore, while building the model, we'll have to pay attention to multicollinearity (especially linear models, such as linear and logistic regression, as they suffer more from multicollinearity).

## Feature Engineering

* Correction of the brand names and consolidation of the samples based on their brand name.

## Data Preprocessing

* Converting categorical variables into dummy variables.
* Here Feature Scaling is necessary as some continuous features are higher in magnitude and this can cause a problem while model building especially in linear models and KNN.

## Model Building

We are going to use the following linear models for model building:

1. Linear Regression
2. Random Forest Regresser
3. K Nearest Neighbours
4. Decision Tree Regressor
5. Ridge Regression
6. Lasso Regression

### Hyperparameter Tuning

* We can see that after tuning also, there is a huge change in all the algorithm. So, we can proceed with the Random Forest Regressor which gives the least error. We can see that by doing cross validation and cross validation predict, we can get the average performance of the model when subjected to different data.

### Feature Selection using RFE

* We can see that taking 45 features gives us a better score. There is a need to work on feature selection and have a statistical approach towards it.


# Conclusion

* Our built model is not able to give a good and accurate prediction at predicting the car price and shows high variance as it gives different accuracy with different set of data.

* This may also be due to the low amount of data that is provided for training.

* At this stage the model will be of no use in production as it is unable to give accuract predictions. Further study and training is required.

