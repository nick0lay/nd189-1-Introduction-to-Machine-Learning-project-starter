# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Nikolay Nikifaorchuk

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Clean up predictions and attach result to submission file.

### What was the top ranked model that performed?
WeightedEnsemble

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Datetime property was a string, which is not good feature to ML models. Decided to convert it to datetime type and extract year, month and hours as a separate features.

### How much better did your model preform after adding additional features and why do you think that is?
Score increased from -114 to -32 which is really good improvement. Hour, month, day, day of week has quite good correlation with count, and this is how it should be. We usually book bikes better during the day houes rather then night hous. In case if we had only datetime we kind of try to predict count base on one feature rather than several more granual features which might has better correlation than one big reature.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After hyperparameter tunnign I didn't see quite significant inprovements. Hence feature engineering is more important, especially with auto ML solutions.

### If you were given more time with this dataset, where do you think you would spend more time?
1. Try to improve existing fetures and add new one.
2. Choose 1-2 best performing algorithms and try to spend more time on tunnig hyperparameters for of this algorithms.
3. Increase training time and try to find better model.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|5|5|5|0.52739|
|add_features|1|3|3|0.52605|
|hpo|1|1|3|0.52189|

### Create a line plot showing the top model score for the three (or more) training runs during the project.
![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.
![model_test_score.png](img/model_test_score.png)

## Summary
AutoML is really great concept which help to try different solutions with less time. And after trial iterrate on existing solution to improve it. But even with this we still have to pay attention to feature engeenering and hyperparameter tunning to get best result possible.
