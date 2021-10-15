# Abstract
The goal of this project was to propose a classification model to predict whether or not an employee would churn, use those predictions to target employees based on how “at-risk” they were for attriting, and suggest recommendations on how to reduce the chances of losing the employee. I used a dataset found on Kaggle.com of fictional “IBM HR Employee Analytics”. After refining the model, I built an interactive dashboard to visualize and communicate my results using Tableau.

# Data
The dataset obtained from Kaggle contained 1470 employees with 35 features for each employee; 9 of these features are categorical. The target variable was Attrition (Yes/No), which marked whether or not an employee had churned. Some important features included age, job level, monthly income, department, job role, level of stock options, total working years, years at current role, years with current manager, and job involvement. While many features were highly correlated with one another, due to the nature of employee analytics, I believe that is to be expected- no one feature is indicative of why an employee might leave an organization, just as no one feature describes how an employee is compensated salary-wise.

# Tools 
* Microsoft Excel
* Python
* Numpy
* Scikit-learn
* Seaborn
* Matplotlib
* Tableau

# Algorithm
Logistic regression modeling and evaluation.
 
Logistic regression fitting was performed by SciKit-Learn. Model was evaluated with a confusion matrix and performance metrics (accuracy, f1 score, precision, recall). An ROC/AUC curve was plotted and visualized.

* Accuracy 0.897
* F1 0.596
* precision 0.8
* recall 0.475

# Results/Design:
I began with the IBM HR Employee dataset that I obtained from Kaggle. I imported it into python in order to quickly clean the data (fill nulls if any, remove duplicates). I then exported that my data into excel in order to do the remainder of my EDA. I was interested in examining each feature’s relationship with the target (attrition), which I did by creating Pivot Tables. I created preliminary visuals in excel in order to guide my advanced visuals in Tableau. Once I had a general idea of important features from my EDA in excel, I went back to python to view correlations using Seaborn's heatmap and to create my logistic model using scikit learn. I tuned hyperparameters using GridSearch, got my accuracy score as well as other supplementary metrics such as f1-score, precision, recall and a confusion matrix, since my original dataset was imbalanced due to having a very small churned:not churned employee ratio. Above all, the purpose of this model was to understand contributing factors in employee attrition more so than mitigating employee churn. For that reason, I did not balance the dataset ahead of time, although I did include a solution path to mitigate churn for anyone interested in the impact of such an investigation. For the puposes of this model I simply included recall in order to minimize false negatives in which we would've falsely predicted an employee as not churning when they actually were. Losing an employee is costly (roughly 50-60% of that employees salary at minimum is needed to find a replacement for the churned employee), therefore it may be worthwhile for the business to prioritize minimizing false negatives by way of recall, than prioritizing false positives because whatever solution path is utilized to keep an employee would ultimately cost less than losing an employee altogether. See below for my discussion of a solution path that prioritizes highest impact and lowest financial setback in the case of employee churn.    

## Scope:
### Nontechnical: 
Employee churn has become a larger problem in the post-Covid era. Replacing an employee can cost as low as 50-60% of the attrited employee’s salary to as high as 100-200%. 

### Impact hypothesis: 
If we were able to predict the likelihood of an employee leaving the organization ahead of time (using a classification model), we could prevent attrition by providing incentives or promotions to "at-risk" employees.
** A constraint would be the number of incentives available/ their cost per employee. 

### Scoping Trade-offs: 
Using a model to gauge the likelihood of an employee attriting is tricky matter because for every false positive, you allocate expensive incentives to someone who wasn’t churning to begin with, and for every false negative, you deal with the cost of losing an employee (50-60% of that employee’s salary, which is on the lower end of some projections). In order to mitigate some of these trade-offs, my solution path proposes flagging an employee who is likely to churn, note/highlight that employee's name in an excel file, send to HR, then have HR speak to their manager who can then either send anonymous surveys to “at-risk” employees, or have one-on-one meetings with those employees to get a better understanding of their job satisfaction.

# Communication
Verbal presentation, accompanying powerpoint slide , and a tableau dashboard
