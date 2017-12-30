
# Registered Riders
The initial goal of the project was to predict the ride times using the registered riders and casual riders together. The model that was produced for that did not perform as well as hoped, so the data was split into casual and registered.

## Models Used and Evaluation Criteria
The regression models used to predict the ride time of a Capital Bikeshare rides were Random Forests, Logisitc Regression, Elastic Net Regression, LassoRegression, and Ridge Regression. 
<br><br>
In order to pick between the different model types and models, the data were split into training (75%) and test (25%) sets and 3 fold cross validation was used with a Grid Search. The loss function used to select the best model was the root mean squared error (RMSE), which will show the average difference between the actual ride time and the predicted ride time from the model.

# Final Model
The final model selected was a Random Forest Regressor. The RMSE was 5.4 minutes which is relatively high but still below the average ride time for all riders.

## Model Selection
Different variations of linear regressions, elastic net regressions, lasso regressions, and ridge regressions were all created to predict the ride time (these models can be found in the folder called "Models Not Used"). The variations were based on removing correlated data like months and seasons. Additional variations were from removing the temperature, humidity, and wind speed. Scaling was also done on the continuous variables (distances to a metro entrance, temperature, humidity, etc). For the lasso regression, the coefficients that were not zero were used in a regular regression model and a ridge regression model.
<br><br>
The RMSEs of the remaining models were between 8 and 10 minutes. These values were much worse than the random forest model used as the final model.
