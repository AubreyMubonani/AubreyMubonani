Data Cleaning Process

1.Removed Duplicated Columns :number_of_defaults.1, age.1,sex
2.Normalised the Country Column,Job Column,Currency,Column
3.Remove Unnecessary Columns:Unamed Column,loan_id,location,currency,country
4.Ensure date columns are in datetime format,remaining term in correct numerical format
5.Checked if Data is In Correct Data Types
6.Handle Missing Values: In The Marital Status Column
7.Renamed the remaning term column

Explanatory Data Analysis

Exploratory Data Analysis Summary

1.Target Variable (Loan Default Status): They are more Non Loan Defaulters than Defaulters. Although the number is alarming interms of losses a firm can be subjected to
2.Gender: They are also likely equal gender distribution between gender varibles in the data which are males(35%),females(32.7%) and other(32.3%). Males have a slightly higher default rate followed by other and then females
3.Marital Status: Married people are more in my dataset (46.2%),Followed by Divorced(27.3%) and lastly singles (26.5%),Credit market share based on the data is mainly dominated by married people who tend to may have more responsabilities and financial needs that singles
4.Employment Status: The employed are more in the credit system that the enemployed. Although on average salary the employed have a slightly higher salary than the unemployed(8% above the enemplyed)
5.Loan:The distribution of loan amounts shows that most loans are clustered around lower amounts, with a long tail towards higher amounts
6.Salary:Salary distribution is fairly normal but skewed slightly towards higher salaries, indicating that while most salaries are around a central value, there are some higher values.
7.Age:The age distribution is relatively normal, indicating a diverse age range among the individuals in the dataset.
8.Correlation Analysis:
There is a strong positive correlation between loan_amount and outstanding_balance  which is expected since a larger loan amount likely leads to a larger outstanding balance
Other notable correlations include:
A strong correlation between loan_amount and salary, suggesting that higher salaries may be associated with higher loan amounts.
A strong correlation between salary and remaning term

Feature Selection Analysis
Categorical Features Analysis
1. Strongest Association: marital_status_single, marital_status_divorced, job_Lawyer, gender_female, job_Unemployed, job_Data Scientist, gender_other, gender_male, job_SoftwareDeveloper, and job_Accountant have the highest Chi2 Scores and the lowest P-values, indicating a very strong and statistically significant association with the target variable.
2.Moderate Association: job_Engineer, job_Nurse, and job_Data Analyst also show strong associations with the target variable.
Weak Association: is_employed and marital_status_married have weaker but statistically significant associations.
3.No Significant Association: job_Doctor and job_Teacher have low Chi2 Scores and high P-values, indicating no significant association with the target variable.
 A higher Chi2 Square Value and a p<0.05 Indicates a stronger association between Categorical Variables
 Because of the above statistical analysis l have moved forward with the following variables 
 gender and marital status as the categorical variables

Numerical Feature Analysis
I have selected the numerical Variable features based on Correlations and Domain Knowledge
Because of the strong correlation between oustanding balance and loan amount l have decided to drop oustanding balance from my nuemerical variables to avoid multi collineality.
I choose 'loan_amount', 'number_of_defaults', 'interest_rate', 'age', 'remaining_term', 'salary' as i know with certaninity that they influence the loan default status

Feature Scaling and Transformation
I transformed the loan amount and salary since they were skewed. Divided Age into bins for easy update of my machine learning model

Model Selection
Reasons and Choice of my models
1.Logistic Regression: Logistic Regression is a widely used algorithm for binary classification problems, such as predicting whether a loan will default or not. It models the probability of the binary outcome as a function of the input features.
2.Random Forest: Random Forest is an ensemble learning method that combines multiple decision trees to improve the overall accuracy and robustness of the model. It can handle both linear and non-linear relationships in the data, making it a versatile choice for loan default classification.
3.Gradient Boosting: Gradient Boosting is another ensemble learning method that iteratively builds a sequence of weak models (usually decision trees) and combines them to create a strong predictive model. It can capture complex patterns in the data and is often effective for classification tasks like loan default prediction.
4.Support Vector Machines (SVM): SVM is a powerful algorithm that can handle both linear and non-linear classification problems. It is particularly useful when the decision boundary between the classes is not easily separable, which can be the case in loan default classification.
5.K-Nearest Neighbors (KNN): KNN is a simple yet effective algorithm that classifies a data point based on the majority class of its k nearest neighbors. It can capture local patterns in the data and is suitable for loan default classification, especially when the decision boundaries are not well-defined.

Model Evaluation Summary

1.Best Performance: The Random Forest model has the highest accuracy (89.05%) and F1 score (87.17%), indicating it performs the best overall among the models.
2.Consistent Performance: Gradient Boosting also shows strong performance with an accuracy of 88.45% and an F1 score of 85.86%.
3.Balanced Performance: Logistic Regression achieves an accuracy of 87.15% and an F1 score of 83.26%, indicating balanced performance.
4.Lower Precision: The SVM model has a lower precision (72.35%) compared to its recall (85.06%), indicating more false positives.
5.Decent Performance: KNN shows decent performance with an accuracy of 85.76% and a balanced F1 score of 82.80%

Model Selection
Based on Overal PermonanceI choose the Random Forest model with higher accuracy of 89.05% saved and Deployed the model.
Thank you
