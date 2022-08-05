# Lead Scoring Case Study Summary

<u><b>Problem Statement:</b></u>

An education company names X Education sells online courses to 
industrial professionals. The company wants to identify the potential
customers, also known as “Hot Leads” who have a high conversion chance. The 
company wants us to build a model where we assign a lead score to each lead 
between 0 and 100 such that the customers with a higher lead score have a 
high conversion chance and the customer with a lower lead score have a lower 
conversion chance. 

<u><b>Approach:</b></u>

Data Cleaning:

1. The dataset had some values as ‘select’ the categorical columns. We replaced the ‘select’ values with Nan values because as per the dictionary they are equivalent to null values.
2. Then we checked for the percentage of null values present in each column and dropped the columns having more than 45% of nulls.
3. For the remaining columns nulls to impute the null values we have created new categories for the nulls.
4. Then we checked for the outliers in numerical columns in and, removed the outliers using the capping method.

Exploratory Data Analysis:

1. We have done Univariate and Bivariate analyses on the both numerical and categorical columns. The bivariate analysis was done concerning the target variable.
2. We found that some of the categorical columns are irrelevant for the 
model, as some were sales generated and some were highly skewed. 
Hence, we dropped such columns.

Data Preparations:
1. We have dropped all the identified irrelevant columns.
2. The dummy variables were created for the remaining categorical columns. Then we dropped the highly correlated columns.
3. We have split the dataset into train and test datasets with a ratio of 7:3 respectively.
4. Then we have scaled the continuous variables of the train data set using Standard Scaler.

Model Building:

1. RFE was used to select the top 15 variables for the build model. Then rest of the variables were eliminated manually on basis of 
their p-values and VIF. The variables with p-values less than 0.05 and VIF less than 5 were kept. 
2. At last we got the model with the top 7 significant features.

Model Evaluation:
1. We have used specificity and sensitivity metrics.
2. We have found the optimal cut-off to be 0.3 using the sensitivity, specificity, and accuracy curve. The sensitivity, specificity, and accuracy were around 80 %.
3. The area under the ROC curve was around 83%.
4. The final conversion rate on train data was around 85%.
5. We have also checked the precision and recall with accuracy, sensitivity, and specificity for our final model on the train set.

Prediction on test dataset:
1. Then we implemented the learnings to the test model and calculated the conversion probability based on the Sensitivity and Specificity metrics.
2. Found the accuracy value to be 70.4%; Sensitivity= 84.4%; Specificity= 62.39%.
3. The final conversion rate on test data was around 84%.

Conclusion:

1. The features that contribute the most towards the probability of leads getting converted are :
a. Lead Source_Welingak Website.
b. Current_Occupation_Working Professional
c. Current_Occupation_Other
2. The lead score calculated for the test dataset and train dataset shows the conversion rate of 84% and 85%, which meets the expectation of the CEO has given a ballpark of the target lead conversion rate to be around 80%
3. The sensitivity of the model is around 84%, which will help us to select the leads that have more chances of getting converted.
