# ad-CVR-prediction

Objective: This project aims to predict the click conversation rate of advertisements in a social media app. App advertising plays a vital role in supporting smartphone apps. To maximize the expected revenue, the app must predict the probability of a click on an ad, more commonly known as the click conversation rate (CVR) of an ad. The data set was real-world data sampled and organized from logs of clicks. The data includes detailed features related to ads, users, and context. The detailed information can be found on the project page.

Challenges:
1) The user profiles are high dimensional and sparse, ranging from user demographics to search queries and page browsing. Dealing with such different activities with limited conversion information is non-trivial.
2) Some efforts need on feature engineering and dimension reduction.
3) The conversation rate was 2.5% with the given data set. The imbalanced data is challenging to work with. The evaluation matrix needs to be chosen carefully.
4) The dataset was collected in the frame of two weeks. When training the classifier, it should be noted that the newer data points were not supposed to predict the older data.

Models and Solutions:
1.	The feature data were transformed to a normal distribution before feeding them into the ML system.
2.	The first eight days’ data were selected for training the classifier. The 9th to 11th days’ data were used for validating the hyperparameters. The 12th and 13th day’s data were used for testing the trained classifier. Because the 14th day observed a low CVR, the data points collected were not used for training or test
3.	Twenty-five features were selected to fit in a random forest classifier. The “balanced-subsample” parameter was used hoping to tackle the imbalanced data. The test prediction accuracy was 10%, and the log loss was 0.117.
4.	To tackle the imbalanced data set, the synthetic minority oversampling technique (SMOTE) was applied to increase the successful click conversation sample size (label =1). The reworked data set was fit into a random forest classifier. The outcome showed improved accuracy (0.18) in prediction conversation, and the log loss was 0.2
5.	The alternative machine learning algorithm, light gradient boosting machine with decision tree was applied. The model was trained and validated. The log loss was 0.1102
6.	Based on the output of the random forest and light gradient boosting machine, fifteen features were selected and fed the xgboosting model. The log loss is 0.1063.
