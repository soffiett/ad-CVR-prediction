# ad-CVR-prediction

The goal of this project the click conversation rate of the advertisements in a social media ap. App advertising plays a vital role in supporting smartphone apps. In order to maximize the expected revenue, the app must predict the probability of a click on an ad, more commonly known as click conversation rate (CVR) of an ad. The data set was a real world data sampled and organized from logs of clicks. The data includes detailed features related to ads, user, and context.

Models and Solutions:
1)	The feature data were transformed to a normal distribution before feeding them into the ML system
2)	The first eight days’ data were selected for training the classifier. The 9th  to 11th days’ data were used for validating the hyperparameters. The 12th and 13th day’s data were used for testing the trained classifier. Because the 14th day observed a low CVR, the data points collected were not used for training or test
3)	Twenty five features were selected to fit in a random forest classifier. The “balanced-subsample” parameter was used hoping to tackle the imbalanced data. The test prediction accuracy was 10% and the log loss was 0.117. 
4)	To tackle the imbalanced data set, synthetic minority oversampling technique (SMOTE) was applied to increase the sample size of the successful click conversation (label =1). The reworked data set was fit into a random forest classifier. The outcome showed improved accuracy (0.18) in prediction successful conversation and the log loss was 0.2
5)	The alternative machine learning algorithm, light gradient boosting machine with decision tree was applied. The model was trained and validated. The log loss was 0.1102
6)	Based on the output of random forest and light gradient boosting machine, fifteen features were selected and fed the xgboosting model. The log loss is 0.1063. 

