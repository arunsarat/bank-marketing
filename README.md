# Bank Marketing Campaign Effectiveness Analysis #
Business goal of this project is to find a model that can explain success of a direct marketing campaign , i.e. if the client subscribes to a Term Deposit after a (or multiple) contact(s). A good model can increase campaign efficiency by identifying the main attributes that affect success, and help in optimizing the resources (e.g. number people, phone calls, time) and also in identifying high probable potential customers.

## Stage-1: Understanding the Data 
Marketing Campaign data can be catergorized into three broad categories. First category has the attributes of the consumer the marketing campaign reaching out, Second category contains the attributes of the campaign itself and third category contains the current macro economic indicators like CPI, CCI & Interest Rates.

Here is the list of attributes in each category.

#### Personal Information
- Age
- Job
- Marital Status
- Education
- Default
- Housing
- Loan
#### Campaign Information
- Contact
- Month
- Day Of The Week
- Previous
- Number of Employees
#### Macro Economic Indicators
- Consumer Price Index
- Consumer Confidence Index
- Euro Interbank Offered Rate (3 months)

### Distribution of Campaigns
This provides distribution of campaigns with respect to a specific consumer like the number of consumers whom bank reached out either one time, couple of times, 3 times etc.. Each bin represents how many times bank marketing campaign reached out to a consumer.

<img width="711" alt="image" src="https://github.com/user-attachments/assets/c0fe5571-d00c-4950-b12f-bac945792330">

### Distribution of Target 
This section identifies the distribution of consumers with respect to their final acceptance to subscribe for term deposit. We use this distribution as an input while selecting training and test data set because training and test data distribution should represent target value distribution.

<img width="814" alt="image" src="https://github.com/user-attachments/assets/bdb9ebfc-0b4d-4d66-b40d-c56a85b507fa">

## Stage-2: Data Preparation
Data preparation phase involves cleaning the data as well as encoding non-numerical features, transforming them into numerical values. There multiple strategies to clean up the data, like forward/backward filling, fill with average/mode values, drop inconsequential or sparse values etc.

Data collected for this particular project is potent, and only data transformation was done to encode categorical type features.

### Training and Validation data split
After data transformation, we split the data into training and validation data. Since the target feature i.e. customer subscription for term-deposit is not equally distributed, we split the data with reference to target feature distribution.

## Stage-3: Modeling
This section uses the following classification models to train the data and identify the efficacy of each model with respect multiple scoring strategies, criteria. This section can be used to compare and contrast each model with respect to their efficacy and performance.

With respect to each model, we identify the confusion matrix which presnts True Positive, Fale Positive, False Negative and True Negative factors. We also compute the training duration for each model and compare.

We also provide a visual represention of ROC curve and ROC curve Area which effectively identify the Model effectiveness.

### Classification Models:
- K-Nearest Neighbor Classification
- Logistic Regression
- Decision Tree Classifier
- SVM Classifier

Note book contains the confusion matrix and different scores (accuracy, precision, recall, f1) as well as ROC curve for each model. Please refer note book for comprehensive data to compare and contrast the classfication models.

## Stage-4: Evaluation 
Evaluation stage includes compare performance and compute budget of each model and derive some conclusions. We also can optimize the data, models and iterate the process.

### Model Performance Conclusion
In this section, we compare each classification model with respect to training compute budget, training accuracy, validation accuracy and Model overall effectiveness (ROC AUC value).

We reprent the performance values as data frame down below. Here are the conclusions based on measured metrics.
- Kernel based classifier(SVC) consumes highest computational budget (100 times more)
- Logistic Regression has the best training and validation accuracy, followed by SVC.
- Logistic Regression has the best AUC value as well, followed by SVC.

<img width="970" alt="image" src="https://github.com/user-attachments/assets/9fcc8a8d-16a3-4a49-9490-5abf4aff183d">


### Optimization
This section talks about different observations on how some features impact the target. This in turn may answer questions about effectiveness of campaign with respect to campaign, consumer and macro economic factors.

First observation tries to answer if multiple campaigns to single consumer effective in convincing the consumer to subscribe to the term desposit.

### Number of compaigns Vs Subscription
This section visually reprents how repeated contact of bank representative to consumers affect the success rate of consumer subscription. As the visual representation presents, the success rate increases as the number of campaigns increase, but eventually it starts wane. This represents consume fatigue with respect to campaign. 

<img width="686" alt="image" src="https://github.com/user-attachments/assets/cc72d10d-a320-4dfe-955b-dc3be1242fb2">

### How married, employed and housed respond to campaigns
This section dvelves into a section of consumers who are settled i.e consumers who are employed (or retired). We divide this group into multiple sub groups like married, divorced, home ownership and see how these subgroups respond to campaigns.

Based on the visual analysis and sorted values, it seems the following groups have almost 50% of chance to accept the Term Deposit.

- Married, in Management, unknown home ownership
- Home owners, in administrative jobs, marital status unknown
- Retired, single and unkown home ownership

<img width="400" alt="image" src="https://github.com/user-attachments/assets/7b311df1-71ad-42c6-b73e-4a30ff6d7026">

## Stage-2: Data Preparation after Optimization
Optimization within Evaluation phase involves identifying the most prominent features or a combination of features so that we can eliminate least important features and train the models and then compare the efficacy of these models with respect to training with full set data.

Goal of optimizating the training process is to reduce the computational budget. Computational budget raises exponentional with respect to the number of features. Hence reducing the number of features is important step in feature engineering.

### Feature Selection and Minimization
There are multiple techniques and models in reducing feature complexity. We use Logistic Regression with regularization to idetify the features that are important. It returns coefficients for each feature and we remove the features that are least important and retrain the classification models and compare the effectiveness of each model with reduced feature data.

This section visually represents how the four most prominent features correlated to the target value (Term Deposit - Yes). This is a 2x2 tile plot visually represent how the following features are correlated to Term Deposit acceptence.
- Duration
- Consumer Price Index
- Consumer Confidence Index
- Number of Bank Employees

Duration field represent how long a bank representative contacted to an individual subscriber. As the visual representation suggests, the likelyhood a consumer subscribing to a term deposit increase as the number of minutes an representative talked that consumer increases. 

As for the other three attributes, visual representation doesn't give a clear trend.
<img width="798" alt="image" src="https://github.com/user-attachments/assets/7fb3a8e6-1ed6-4983-8113-5a4e9a25032a">

## Model Performance with reduced features -  Conclusion
We compare the compute complexity between full-feature data set training vs reduced feature data set.


We reprent the performance values as data frame down below. Here are the conclusions based on measured metrics.
- Kernel based classifier(SVC) consumes highest computational budget (100 times more)
- Logistic Regression has the best training and validation accuracy, followed by SVC.
- Logistic Regression has the best AUC value as well, followed by SVC.

<img width="735" alt="image" src="https://github.com/user-attachments/assets/c81a3ee8-3f5e-4b80-ae81-94e6c37fd037">

<img width="476" alt="image" src="https://github.com/user-attachments/assets/cc1c59cf-36b8-458f-a24f-20783bca473b">






