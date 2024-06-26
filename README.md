# Capstone
Capstone project to predict a student's drop out in a college using ML classification techniques

The link to the Jupiter notebook is https://github.com/praloysinha/Capstone/blob/main/Capstone_Praloy.ipynb

Data Source : https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention

**Objective:**

The Business Objective is to evaluate the different classifers like KNN,Logistic Regression, Decision Tree and Support Vector Machines on the college dropout dataset in predicting the right classification whether the persons are enrolled, graduate or dropout.

**Approach**

The approach will be to model using these classifiers on the different demographic and education and data of the persons and a few macroeconomic data. In this business problem, we should ideally be able to predict as many people who are likely to dropout of the college and take corrective action. We will try to optimize the accuracy of the model

**Data Exploration and Preparation**

A dataset comprising of 4,424 rows was selected for ML computation wioth 36 features and 1 target variable

No missing values were found in the dataset

The "Graduate" class is 3 times the "enrolled" class and hence is greatly imbalanced. We need to balance the data with SMOTE for better modelling

"Nacionality", "Educational special needs", "International", "Curricular units 1st sem (credited)", "Curricular units 1st sem (without evaluations)", 'Curricular units 2nd sem (credited)', 'Curricular units 2nd sem (without evaluations)' columns were removed due to it mostly belonging to a single class 

Data Visualization using seaborn and plotly charts

Balanced the target class using SMOTE

Created the train - test split for modelling


Created the baseline model using the Dummy Classifier

We have to beat a baseline of accuracy of 32.2% of the Dummy Classifier by the other models

**Modelling with default hyperparameters**

The Decision Tree is reaching the accuracy of almost 73% in accuracy and taking relatively less time as well. SVM has a very low 34% accuracy.

KNN and Logistic regression has accuracy in the 60s

**Model Improvement**

Grid Search was used to optimise the model which regularized the model for feature selection, reduced complexity for easy comprehension. This was done with hyperparameter tuning

Confusuion Matrix, Trees and tree text were plotted

Logistic Regression coefficients were observed

**Observations:**

We can see that KNN has vastly increased its precision from 67% to 78%

The Logistic Regression has a slight betterment from 65% to 68% accuracy but halved its inference time which means lesser complexity

Decision Tree has an accuracy of 75% in comparison to the initial one and the inference time is similar

SVM has fared poorly in the original and Grid Search with low accucary of 32% and very high inference time

**Optimized model:**

The best model of KNN has a n of 1 which means it is a highly complex model and prone to outliers influence.

The Decision Tree best model has a max depth of 7 which is relatively easy to comprehend and moderately complex

The Logistic Regression best model is a highly regularized one wwith C = 0.2 and ovr as multi_class and hence will have lesser complexity. Feature selection was automatically done with this highly regularized model

The SVC best model is at polynomial degree 6 and is at medium complexity 

Curriculum credits, tuition fee upto date, course, age, parents' qualification are few of the important features which affect the dropout

**Initial Inferences with Standalone Models:**

The data had highly imbalanced classes which had to be balanced

The classifiers provide a much higher performance scores than the base dummy model to predict drop out rates

Decision Tree and KNN are the best performing classifiers with 75-78% % accuracy scores

Logistic Regression provides clarity on the top features which can be actioned upon; however has a lower accuracy score of 67%

KNN has the highest 78 % precision but uses a complex model

Decision Tree provided clarity through its 7 level tree; however SVM is a litte bit of a black box with only indices information and low accuracy

**Intermediate Findings and next steps:**

Ideally, we should be able to **predict as many dropouts as possible** and take corrective action to prevent it.

From the Decision Tree and Logistic Regression model, we can see that the following

curriculum credits

tuition fee upto date

course

age

parents' qualification

are **important features to predict** drop outs **and work on them to prevent.

The **Decision tree** is easy to comprehend and action on the feature values, has good accuracy of 75% and has low inference time. Hence this is recommended as a standalone model. 

**Ensemble Techniques**

After the standalone models were run, the ensemble techniqus were used and a Grid Search also performed on them.

1. The techniques were Adaboost, Gradient boosted trees, Random Forest, Random forest with OOB, XG Boost, Extra Trees Classifier, Voting and Stacking Classifier
   
2. The best model was the Random Forest one at 84.4% test accuracy
   
3. After the Grid Search, the best model was Gradient boosted trees with 85.7% test accuracy
   
4. Hence the **Gradient Boosted trees is the final recommended model** to predict the dropouts. The feature importance is also generated and the top ones are:

Curriculum credits

Tuition fees

Admission Grade

Course

Previous Qualification

F**inal Recommendation**

Consider the Gradient Boosted Trees model with {'max_depth': 10, 'max_features': 8, 'n_estimators': 200} parameters for predicting dropouts 

