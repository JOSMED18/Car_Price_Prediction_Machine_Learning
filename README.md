# Car_Price_Prediction_Machine_Learning
### Summary
Forecasting is one of the most important phases in supply chain managment and data driven decisions. That's why data is so important for businesses. This repository provides a simple way to predict prices when time series analysis is not available due to the lack of datetime information. The assumptions like normality tests and outliers detection are touched through the repository. Then, a correlation analysis is made to determine whether the independent variables can be used for regression. You will see that there is an issue in this data when correlation analysis is ran. 

### Cleaning 🧹
Since Python does not read string (text) but variables, a cleaning must be done to evaluate variables with qualitative values. A number has been assigned for each value within the variable (for example, number of doors, *two* is represented by 0, and *four* by 1) so correlation analysis could be done. Take a look at the notebook for insights. 

### Normality 
Then a normality test was ran. The dataset contains 200 rows, which is enough for this test. Using Shapiro statistical test for normality the p-value was found. If the p-value is less than 0.05 it means the values of that variable are normally distributed. You will see that almost all the variables are. 

### Outliers
Using Inter Quartile Rule, the outliers were detected and the top 5 of outliers were as shown below: 

![image](https://user-images.githubusercontent.com/101015892/213349289-350ff44a-a643-47dd-a7d5-6449550b1805.png)

As you see, 10 outliers were detected in enginesize variable, and were replaced for a central tendency measure. In this case, the mean. 

### Correlation Analysis
Now assumptions had been fulfilled, correlation analysis was ran, where a correlation matrix was built. So, 

![image](https://user-images.githubusercontent.com/101015892/213349733-896f2a61-00ab-4a56-b5df-9df2386e9b9f.png)

We see positive coefficients and muticolinearity problems with horsepower since it has almost the same relationships as price do. So, in order to not overfit the model and provide real insights the variables used in the model were: horsepower and compression ratio.

![image](https://user-images.githubusercontent.com/101015892/213349943-d092c800-8693-4b76-bc07-31b54a2c2855.png)
_Scatterplot for horsepower and price: positive correlation, it means proportional_

![image](https://user-images.githubusercontent.com/101015892/213349967-146a3b19-51cc-459b-85b5-17090772ca17.png)
_Scatterplot for compression ratio and price: negative correlation, it means inversely proportional_

### Conclusion and result
As a result, after training and runing the model, it has got a R2 error of 67% which is actually a good percentage. In this case our model predicts 67% of the data.   
