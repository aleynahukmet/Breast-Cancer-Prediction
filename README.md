# Breast-Cancer-Prediction

<p align="center"> 
   <p align="center"> 
   <img width="1000" height="400" alt="breast-cancer" src="https://user-images.githubusercontent.com/87663976/143589879-c6f2aa4a-833d-4fca-bada-92dab6fd3ce6.jpg">
</p>

In this project, we focus on breast cancer prediction. There are several important parameters for breast cancer in the dataset we have. We will make predictions by looking at the relationship between them and breast cancer.


# Exploratory Data Analysis

I have a clean dataset with few features so I started to have visualization to see the relation of features and diagnosis. First I checked the barplot of different features with diagnosis(target label) to see the relationship between features and diagnosis. Then I checked for correlation. Finally, I plotted a scatter plot of features with diagnosis.

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143591271-92e92feb-c0ee-402c-9c94-2030084b6f24.png">
</p>
-![indir (3)](https://user-images.githubusercontent.com/87663976/143591271-92e92feb-c0ee-402c-9c94-2030084b6f24.png)


# Correlation 

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143219223-4451b45d-d5ab-4aaa-86a4-37caf145171a.png">
</p>

As it can be seen on the correlation matrix some features had a high correlation between them. When independent features are highly correlated i.e. have the same nature, then they introduce the element of variance in the model which is called Multi-Collinearity. Multi-Collinearity is not good for our models so I dropped some of the columns to avoid that.

# Label Encoding
We had only two categorical columns. When it comes to the "status" column, the ordinal column is encoded with the label encoding method. The "country" column is nominal and it is encoded with the one-hot encoding method. And I encoded "country" column with one-hot encoding method I dropped one column to avoid Multi-Collinearity.

# Feature Scaling
Robust Scaler is one of the best scaler methods to use when a dataset contains outliers. As seen previously, our dataset had outliers and we did not remove or replace them. Outliers can skew a probability distribution and make data scaling using standardization difficult as the calculated mean and standard deviation will be skewed by the presence of the outliers. Therefore, we choose RobustScaler for our Feature scaling.

# Models 
We trained eight different models (Lasso, Ridge, Random Forest, KNN, Decision Tree, SVR, Gradient Boosting Regressor and Ada Boosting Regregssor) to see which one is the giving best results. Then I checked results after cross validation too and plotted the results.

# R2 Scores


   | Model                | CV R2 Mean   |      Std     |
   | :------------------: | :----------: | :-----------:|
   |  Lasso               | 0.9481       | 0.0143       |
   |  Ridge               | 0.9481       | 0.0143       |
   |  Random Forest       | 0.9611       | 0.0078       |
   |  KNN                 | 0.839148	  | 0.0123       |
   |  Decision Tree       | 0.8926       | 0.0149       |
   |  SVR                 | 0.8328       | 0.0224       |
   |  Gradient Boosting   | 0.9497       | 0.0074       |
   |  Ada Boosting        | 0.8921       | 0.0126       |

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143229476-dfa19181-73d5-4a0b-8919-763ec6d82cc6.png">
</p>
