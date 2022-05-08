
# Modelling Earthquake Damage On Buildings 

The goal of this project is to build a machine learning model which can accurately predict the damage done to the building during Gorkha Earthquake - 2015 using different machine learning model. Predicting earthquake is still one of the most difficult task out there. The best we can do right now is be prepared for it all the time. The data is collected from DrivenData which is shorter version of actual data published by Kathmandu Living Labs and Central Bureau of statistics. The data is also currently in competition organized by DrivenData. Using existing and popular machine learning model along with application of various feature engineering technique a model has been made which can predict the damage to the building during the Gorkha Earthquake -2015. 

- Data is taken from DrivenData which is the truncated version of actual data published by Central Bureau of statistics. 
- The data has 39 features and damage grade as target variable.
- There are total 21213 records. 
- Performed Data exploration to explore hidden pattern in the data
- Performed Feature engineering using Kendall Tau correlation coefficient and Robust scaler and other technique. 
- Applied Label Encoder 
- Prevented Data Leakage 
- Splitting the data 
- Applied various machine learning models and checked their performance 
- For evaluation, accuracy score is used.


### Steps involved in project: 
- Data Exploration 
- Feature Engineering and Feature Selection 
- Model Selections and optimizations 
- Result and conclusion 

### Data Exploration:
 Download the dataset from the https://www.drivendata.org/competitions/57/nepalearthquake/page/136/. Checked for the null values. Explored the data to find the pattern and insight through visual representation of the data.Many pattern and insight were drawn through data visualization.
 Used only  a small subset of the actual data in this project due to limited computing capabilities.

### Feature Engineering and Selection: 
Various technique are used during feature engineering. 
- Kendall Tau Correlation coefficient: The reason for choosing Kendall Tau Correlation Coefficient over Pearson coefficient is because with Pearson Correlation Coefficient we can only observe the linear relation between the features but with Kendall Tau and Spearman correlation coefficient, we can observe the monotonic relationship between the features. The reason for choosing Kendall Tau over Spearman correlation coefficient is that Kendall Tau works better when there is an outlier in the data compared to Spearman correlation coefficient. Because of this I chose Kendall Tau Correlation coefficient for my analysis and feature selection.
- Robust Scaler: There are various scaling technique out there but I chose Robust scaler over other because Robust Scaler is better at scaling when there are outlier present in the data. 
- Label Encoder: All the data generally obtained during during data collection phase cannot be as integer. Many times data are categorical with text or string. So, we use Label Encoder to convert these categorical text or string data to numerical data so, that we can perform analysis.
- Handling Data Leakage: Most of the time we tend to split the data before preprocessing the data. For example, if we apply Robust Scaler before splitting the data, the test and train data are exposed to each other to some degree. This will definitely produce better model but it is not a good practice. So, to handle the problem of data leakage, I applied scaling technique to both test data and train data set after splitting the data set.
- Splitting the data: It is important to split the data in train and test set, because it helps us to prevent the case of overfitting and it is also helpful in checking the accuracy of our model. So, it is the final step before model selection.

### Model Selection and Optimization: 
I considered following features before selecting models. 

- Interpretability: It is very important to that you can interpret you model and tell why the model is behaving in such a way. If interpretability is one of the primary goal, then Neural Networks should be avoided because it generally very difficult to interpret Deep Learning Models.
- Size of Data: It is another important thing to be considered before selecting the model. If the data set is small, SVM can perform better while with large dataset there are not very good. Similarly, with Neural Network they perform better when the data set is very large.
- Format of Data: If the target variable is categorical variable, it is advised to use Classifier Model while if the target variable is continuous or discrete it suggested to use Regressor Model
- Training time: Training time is very important feature while making model selection. Training time cannot be neglected when selecting a model.
- Accuracy: It is often the most dominating factor during the model selection. Almost, all the time, a model with higher accuracy is preferred unless there is a significant impact created by above discussed factors. 

I tried almost all the model but I got the best perform with only few models. 
Based on the above criteria, the model selected by me are as follows: 
- Random Forest 
- Bagging Classifier
- Gradient Boosting 

After that I optimized these model using grid search CV. 
To enhance the performance of my model I made ensemble model using above three machine learning models.

### Result: 
Random Forest: 
- Accuracy without optimization: 67.51% 
- Accuracy after optimization of hyper-parameters= 68.79%  Accuracy increase after hyper-parameter tuning = 1.28%  

Bagging Classifier: 
- Accuracy without optimization: 66.38% 
- Accuracy after optimization of hyper-parameters= 67.68%  Accuracy increase after hyper-parameter tuning = 1.3%  

Gradient Boosting: 
- Accuracy without optimization: 66.85%  
- Accuracy after optimization of hyper-parameters=68.08 %  Accuracy increase after hyper-parameter tuning = 1.23%  

Ensemble (Random Forest, Bagging, Gradient Boosting): 
- Accuracy obtained = 69.19%  

The best accuracy was obtained using ensemble method which is 69.19%. 

### Conclusion:
Damage Grade to the building can only be predicted with the accuracy of 69.19% with given features in the data. This satisfactory model but not a very good model.

## Authors

- [@Nihal-Singh1996](https://github.com/Nihal-Singh1996)

