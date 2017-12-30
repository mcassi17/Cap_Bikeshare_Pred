
# Casual Riders
Because the prediction of the ride time using both registered and casual riders did not do well, the data was split into registered and casual riders.

## Models Used and Evaluation Criteria
The regression models used to predict the ride time of a Capital Bikeshare rides were Random Forests, Logisitc Regression, Elastic Net Regression, LassoRegression, and Ridge Regression. 
<br><br>
In order to pick between the different model types and models, the data were split into training (75%) and test (25%) sets and 3 fold cross validation was used with a Grid Search. The loss function used to select the best model was the root mean squared error (RMSE), which will show the average difference between the actual ride time and the predicted ride time from the model.

# Final Model
The final model selected was a Random Forest Regressor using 50 minimum leaf samples. The RMSE was 14.9 minutes which is relatively high but still below the average ride time for a Casual Rider.

## Model Selection
Different variations of linear regressions, elastic net regressions, lasso regressions, and ridge regressions were all created to predict the ride time (these models can be found in the folder called "Models Not Used"). The variations were based on removing correlated data like months and seasons. Additional variations were from removing the temperature, humidity, and wind speed. Scaling was also done on the continuous variables (distances to a metro entrance, temperature, humidity, etc). For the lasso regression, the coefficients that were not zero were used in a regular regression model and a ridge regression model.
<br><br>
The RMSEs of the remaining models were between 15.8 and 16.5 minutes. These values were much worse than the random forest model used as the final model.


```python

```
