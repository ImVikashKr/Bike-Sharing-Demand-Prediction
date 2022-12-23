# Bike-Sharing-Demand-Prediction
Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.

# Abstract: 
The attached dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per hour, and date information. Use the Regression to predict the count of bike count required at each hour for the stable supply of rental bikes.

I'm going to use this dataset for some EDA. And I'll delete the unnecessary columns and create some new ones. After all of this, I'll make future predictions using linear regression, decision trees, and random forests.

# Problem Statement
Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.

The main objective is to build a predictive model, which could help them in predicting the rented bike count proactively. This would in turn help them in prediction of bike count required at each hour for the stable supply of rental bikes quickly and efficiently. 

# Number of rental bikes overall in relation to various characteristic values
I.	During the summer, a lot of bikes are rented as compared to other seasons.

II.	The average number of rental bikes is high outside of holidays. That suggests a large proportion of people ride rental bikes to work.

III.	The number of rented bikes grows as the temperature rises, as seen by the line graph. However, the number of rental bikes starts to decline beyond 30 degrees Celsius.

IV.	People travel to or from work primarily around morning 9 AM and evening 7 PM. The increased rental bike count during those hours may therefore be due to this. Additionally, more people prefer to hire bikes when they are leaving work than when they are going.

V.	The most bikes are rented in the month of June. Additionally, the lowest number of bikes are rented in January and February.

VI.	The most bikes are rented in the month of June. Additionally, the lowest number of bikes are rented in January and February.

VII.	For Sundays the rented bikes are used less as compared to other days.

# Dropping of columns 
From correlation heatmap it is clear that only Temperature, Hour, Dew point Temperature and solar radiation are highly correlated with Rented bike. All other features are less correlated. Temperature has a very high correlation with dew point temperature and hence both has the same variation so dew point temperature can be eliminated.
High correlation between:
1.	Temperature and Seasons
2.	Temperature and Dew Temperature
3.	Dewpoint Temperature and seasons
4.	Humidity and dew point temperature
Dropped the columns from data frame with high correlation

# Steps involved:
●	Exploratory Data Analysis 
After loading the dataset we performed this method by comparing our target variable that is Surge_Pricing_Type with other independent variables. This process helped us figuring out various aspects and relationships among the target and the independent variables. It gave us a better idea of which feature behaves in which manner compared to the target variable.

●	Null values Treatment
Our dataset contains a large number of null values which might tend to disturb our accuracy hence we dropped them at the beginning of our project inorder to get a better result.

●	Encoding of categorical columns 
We used One Hot Encoding to produce binary integers of 0 and 1 to encode our categorical features because categorical features that are in string format cannot be understood by the machine and needs to be converted to numerical format.

●	Fitting different models
For modelling we tried various classification algorithms like:
1.	Linear Regression
2.	Decision Tree 
3.	Random Forest 

# Algorithms:
1.	Linear Regression:
Linear Regression is a machine learning algorithm based on supervised learning. It performs a regression task. Regression models a target prediction value based on independent variables. It is mostly used for finding out the relationship between variables and forecasting. Different regression models differ based on – the kind of relationship between dependent and independent variables they are considering, and the number of independent variables getting used.	

![image](https://user-images.githubusercontent.com/33064867/209319603-d45c7d73-0ef8-466b-bbb8-bfee9d867c40.png)

Linear regression performs the task to predict a dependent variable value (y) based on a given independent variable (x). So, this regression technique finds out a linear relationship between x (input) and y(output). Hence, the name is Linear Regression.
In the figure above, X (input) is the work experience and Y (output) is the salary of a person. The regression line is the best fit line for our model.

2.	Decision Tree:
Decision Tree is the most powerful and popular tool for classification and prediction. A Decision tree is a flowchart-like tree structure, where each internal node denotes a test on an attribute, each branch represents an outcome of the test, and each leaf node (terminal node) holds a class label.
![image](https://user-images.githubusercontent.com/33064867/209319749-c890707a-dfdb-4164-ad6f-51cfcbc9876e.png)

3.	Random Forest Regression:
Random Forest Regression is a supervised learning algorithm that uses ensemble learning method for regression. Ensemble learning method is a technique that combines predictions from multiple machine learning algorithms to make a more accurate prediction than a single model. 
![image](https://user-images.githubusercontent.com/33064867/209319850-1fbf19a6-1d82-4853-baf8-896834dbc073.png)

# Model performance:
Model can be evaluated by various metrics such as:

1. Mean Absolute Error(MAE)
MAE is a very simple metric which calculates the absolute difference between actual and predicted values.
![image](https://user-images.githubusercontent.com/33064867/209319939-5f415de1-cf5e-45ec-894c-52ca34df5578.png)

2. Mean Squared Error(MSE)
Mean squared error states that finding the squared difference between actual and predicted value.
 ![image](https://user-images.githubusercontent.com/33064867/209320131-3ccb85c9-e45a-4d4b-98c7-987a8dadee1a.png)
 
3. Root Mean Squared Error(RMSE)
As RMSE is clear by the name itself, that it is a simple square root of mean squared error.
![image](https://user-images.githubusercontent.com/33064867/209320175-32f182e0-764b-4dc7-bce0-d2498cbf8027.png)
 
4. R Squared (R2) 
R2 score is a metric that tells the performance of your model, not the loss in an absolute sense that how many wells did your model perform.

So, with help of R squared we have a baseline model to compare a model which none of the other metrics provides. The same we have in classification problems which we call a threshold which is fixed at 0.5. So basically, R2 squared calculates how must regression line is better than a mean line.
![image](https://user-images.githubusercontent.com/33064867/209320227-f39c9c96-a2a6-4901-a07d-dfdbab32d17a.png)

5.  Adjusted R Squared
The disadvantage of the R2 score is while adding new features in data the R2 score starts increasing or remains constant but it never decreases because It assumes that while adding more data variance of data increases.
But the problem is when we add an irrelevant feature in the dataset then at that time R2 sometimes starts increasing which is incorrect.
Hence, To control this situation Adjusted R Squared came into existence.
![image](https://user-images.githubusercontent.com/33064867/209320280-eba07379-2d50-4a3d-9719-b475a5ed27d4.png)

# Conclusion:
We have analysed Seoul city bike sharing dataset. Through analysis, we saw that in general the number of bike rents in 2018 was more than in 2017. The highest number of bike rents occur in summer while the least bike rents occur in winter. In daily basis, the trend of bike rents is almost similar with slight peaking demands on Thursday while drops on Sunday. In hourly basis, the bike counts peak in the afternoon (from 15.00 to 20.00). There are two peak occurrences, at 7.00 and at 17.00, which is most likely to be caused by workers going to office in the morning and going back home in the afternoon.
The hourly movement of bike counts seems to correlate with temperature, visibility, windspeed, and humidity. The bike counts peak in the afternoon (from 15.00 to 20.00) where temperature is the highest, with the most visibility, windspeed, and least humidity. There were days in a weekday when the bike sharing facility was not functioning. However, during public holidays, the facility was still operating.
Based on this analysis, 
Future events can be predicted with 49.73% accuracy using linear regression. 
With an accuracy rate of 85.69%, decision trees can forecast the future. 
Random Forest has a 92.18% accuracy rate for future prediction.









