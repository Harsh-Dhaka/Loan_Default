# Loan_Default
* A personal loan is an unsecured credit provided by financial institutions based on criteria like employment history, repayment capacity, income level, profession, and credit history. This is also known as a consumer loan or a multi-purpose loan, and it helps the borrower meet any of their immediate needs.
* One of the leading bankers in US has approached you to predict on the defaulters with the help of the recent data on the personal loans availed by various customers.
You are now asked to build a robust machine learning model that would distinguish the future applicants who might default and help the bank to take proactive measures.

# Attribute Information:
The train dataset contains 87500 rows and 30 columns and test data contains 37500 rows and 29 columns.

# Data Preprocessing and EDA:
* In the dataset there are some of the variables which contains missing values around min 1% to max 6%.
* We deal with missing values by putting mean value for numerical variables and mode value for categorical variables.Applied same for both train and test data.
* Encoded some of the variables and also bin some valiables by using user defined functions(e.g. Experience variable bin to 4 buckets Fresher,Amateur,Pro)
* In some variables there were special characters present, also removed them.
* Variable like Postal_Code were totally redundant, dropped them.
* We also used group by function and crosstab for some variables(e.g. Count of Loan/No Loan according to each state,Based on Yearly_Income variable shows up Loan/No Loan).

# Statistical Analysis:
* We performed some statistical tests to check the significance of varibles for the further modelling.
* After using tests like Anova we find out some variables were showing dependecy with target variable(e.g. GGGrade is pretty much dependent on the income of the applicant.)

# Model:
* We separated numerical,Un-encoded categorical and Encoded categorical variables.
* Then we done dummy encoding for the required variables and powertransformed and then scaled requisite numerical variables.
* After scaling we concat the dummy and encoded train data, applied same on test data also.
* We considered Logistic Regression as our base model, after that we used decision tree for better performance and also done hyperparameter tuning of decision tree.
* Than we also used some other algorithms like Random forest Classifier, some feature selection techniques(e.g. SFS,RFE),tried a hand with Probabilistic model(GaussianNB) also,and used stacking classifier.From decision tree we were also able to see features importance.
* After all this we used Bossting techniques like XGBoost, but boosting techniques didn't show up any performance here.
* By considering all the results we were able to see that stacking classifier model comes out to be the best one with an F1 Score of 0.56 across all other attempted models.
