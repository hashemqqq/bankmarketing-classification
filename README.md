Introduction=
This project investigates a supervised classification problem of the case study of a bank telemarketing campaign dataset to determine which of the customer’s attributes play a role in predicting subscription to a term-deposit. 
It is hypothesized that the non-linear ensemble models to outperform the linear models due to the independence of the features relationships relative to customer behavior. 
Such a work model is critical component for any effective marketing campaign, allowing available data to be analyzed through the utilization of machine learning to then be able to priorities higher probability customers and thus reduce costs and time consumption, creating a more efficient marketing campaign. 

Focused Analysis=
Data Understanding: 
The Bank Marketing Dataset from Portuguese Bank telemarketing campaigns was sourced from Kaggle. The dataset contains no missing values or duplicates, and includes both numerical and categorical variables. The target variable, “y”, was converted into numerical binary, thus making this a binary classification problem.  
The features describe the customer’s demographics, financial status, and the status of their relationship with the campaign, such as whether they participated in the previous campaign, and how often they interact with the marketing team.
Notably, the dataset is highly imbalanced, where customers which did not subscribe highly exceed those who did in a ratio of near 90% to 10%. This imbalance will have implications on model performance and must have multiple evaluation metrics. Before proceeding to the next steps, the “duration” variable, which represents the duration of each marketing calls, was removed to avoid data leakage and ensure realistic performance applicable to a real world scenario.

Data Analysis: 
Conducting EDA identified patterns and relationships between the variables through visualizations, which lead to the identification of potential predictors for customer subscription. The project used the libraries Pandas, Seaborn, Matplotlib for this section of the project. 
The distribution of the target variable with the other features was visualized. A barplot was created to confirm the scale of imbalance within the dataset.
Other visualizations included a countplot to view the distribution of age, their balance, occupation, relationships, housing and the outcome of previous campaigns alongside the frequency of calling, relative to the outcome of the current campaign. 
Findings suggest that subscribers are generally older on average. Moreover, customers with a higher account balance could have a slight tendency to subscribe more, this finding is supported by the fact that housing loan status demonstrated visible differences indicating willingness to subscribe without financial obligations. 
A scatterplot comparing the number of contacts within the previous vs current campaigns displayed a negative correlation, indicating that repeated contact results in lower chances of customer subscription. 
Furthermore, customers that were previous subscribers are more likely to subscribe again, as indicated by a barplot. 

Modelling: 
The data was then preprocessed and one-hot encoded, then four classification supervised models, linear and non-linear, were implemented and compared.
The target variable “y” was separated, and the dataset was split into 80-20 training and testing subsets. Logistic Regression, which assumes a linear relationship between the features and the outcome, was used with the hyper-parameter “class_weight=’balanced’” to tackle the highly imbalanced dataset, as previously identified, and thus improve recall.
Naïve Bayes was another linear model implemented. Ensemble Non-linear models. being Decision Tree also included the “class_weight=’balanced’ hyper-parameter. Moreover, Random Forest was trained using 300 trees, chosen for its stable performance. 
Due to the imbalance of the dataset and the insufficiency of simply using the accuracy metric, which measures the overall ability of the models to predict accurately, the models were assessed with multiple other metrics, being precision; to display the proportions of subscribers, recall; to measure the ability identify subscribers, confusion matrix; to have an overview of the results, and ROC-AUC; to compare the models overall performances. 
The Random Forest model performed the highest, with an accuracy score of ≈0.90, and further confirmed an ROC-AUC score of ≈0.78, the highest out of the rest. 
Logistic Regression however scored an accuracy of ≈0.65, precision of ≈0.21, recall of ≈0.67 and an ROC-AUC ≈0.72.
 
Insight summary: 
The Random Forest model achieving the highest accuracy and ROC-AUC score indicates predictive ability in this data-set due to its non-linearity. However, despite its high accuracy performance, and Logistic Regression’s scoring the lowest in accuracy, the Confusion matrix’s reveal that LR achieves the highest amount of TP predictions, and in turn substantially increases in FP. 
On the other hand, RF achieves the highest amounts of TN, meanwhile the lowest amount of TP.
This uncovers the fact that LR is a high-risk model which favors maximizing potential subscribers creating a resource intensive yet rewarding model. meanwhile RF is the complete opposite, a balanced model that prioritizes cost-efficiency.
EDA has uncovered several factors that associate the likelihood of customer’s subscribing; such as financial capacity, and the outcome of previous campaigns, indicating the importance of long-term engagement with the customer. The model’s reinforced these findings, indicated by the scores of all implemented models, exceeding the 0.5 threshold figure of ROC-AUC, displaying patterns. The findings imply that the bank must prioritize customers with a positive history with the campaigns and a more stable financial status. 

Conclusion=
This project demonstrated the ability to conduct analysis through visualization, and the evaluating of a number of classification models within a business marketing context. A major challenge was the acute class imbalance within the dataset, which skews visualizations in exploratory data analysis, thus needed thorough understanding and was handled through the use of precision, recall and ROC-AUC evaluation metrics for reliable assessments of performance, class weighting to stabilize performance, and data preprocessing.
