
# Rider Type Prediction
Capital Bikeshare riders can be one of two types: Casual or Registered. Based on the intial analysis done, there seems to be a big difference in ride times and distances traveled for the two types. The data used in this analysis had 300k casual riders and 900k registered riders, which is an important piece of information for modeling this classification problem.

## Models Used and Evaluation Criteria
The classification models used to predict the rider type of a Capital Bikeshare rider were Random Forests, Logisitc Regression, and Linear Support Vector Machines. 
<br><br>
In order to pick between the different model types and models, the data were split into training (75%) and test (25%) sets and 3 fold cross validation was used with a Randomized Grid Search. The Grid Search parameters were class weight (penalty value for each class), number of features included in the model, and minimum leaf samples (number of samples required to make a branch). The receiver operating characteristic, training accuracy, testing accuracy, precision, and recall were all used to pick the best models. 

# Final Model
The final model selected was a Random Forest Classifier using the class weights (penalty) of 0.7 for casual riders and 0.3 for registered riders, number of features equal to 40, and 50 minimum leaf samples. All variables were included in the model including ride time, weather, start/end stations, distance to a metro entrance, distance to a landmark, and rush hour. 
<br><br>
The training accuracy of the model (predicting the rider type of the training data) was .88 and the testing accuracy of the model is .86. The model is a little overfit as the training accuracy is higher than the testing accuracy but the difference between the two is not much. The receiver operating characteristic score was .746, which shows how well the model can distinguish between the two groups. The optimal value for the ROC score is 1 so .746 is fairly high meaning that the model can distinguish fairly well.
<br><br>
The precision (the proportion of riders that were classified as being registered when they were actually registered) for the model was .87 and the recall (the proportion of actual registered riders that were classified as registered by us) was .88. The optimal values are 1 so both of these values are high.
<br><br>
Like the rest of the models used for predicting the rider types, there is an issue with classifying the casual riders. From the test set, there are 50k casual riders and the model only predicts 27k as casual riders. When you look at the incorrect predictions, the ride times are fairly low, which could be the reason for the incorrect classification.

## Model Selection
Different variations of random forests, logistic regressions, and linear support vector machines were all created to predict the ride types (these models can be found in the folder called "Models Not Used"). The Logistic Regression Models did not perform very well as the model could not predict the casual riders. The ROC scores were much lower (~.67) compared to the Random Forests and Linear Support Vector Machines. The accuracy scores (~85%) and precision/recall (.86/.87) scores were fairly consistent with the other types.
<br><br>
The Linear Support Vector Machines performed slightly better than the Logistic Regression when it comes to ROC scores (.69 to .73). The SVM models did do well when it came to accuracy (~84%) but it was lower than the Logistic Regression models and the Random Forests. The models also had issues with classifying casual riders like the Logistic Regression and Random Forest models. 
<br><br>
The Random Forests did fairly well when it came to accuracy (~87%) and one model had a training accuracy of 99%. This model had the highest ROC score at .75 but it was overfit as the test accuracy was only 86%. The remaining models had ROC scores between .69 and .73. The precision and recall values were similar to the precision and recall values for the final model but these models did not predict casual riders as well as the final model.
<br><br>
In addition to these models, an Ensemble of Logistic Regression models was used too. To build the ensemble, the data was split into X and y datasets and then split into train and test sets. The train sets were then randomly sampled 11 times so that the number of casual riders was equal to the number of registered riders (125k). 11 models were trained and used to generate 11 different sets of predictions. These predictions were then used to generate the final predictions by using a majority vote. This model did not perform well compared to the other models. The accuracy was only 81%, the precision was .86, and the recall was .82, which are lower than the other models.


```python

```
