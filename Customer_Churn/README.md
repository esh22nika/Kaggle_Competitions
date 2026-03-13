# Problem Statement 

A telecom firm wants a churn prediction model that is both accurate and explainable. You are required to build a Linear SVM model and explain how the decision boundary is formed using support vectors. You must show the impact of regularization (C) on margin width and misclassification. 

# Expected Input 

Telco-Customer-Churn.csv 
Program arguments (example): 
python task1_linear_svm_churn.py --data Telco-Customer-Churn.csv --target Churn --test_size 0.2 --C 0.1 1 10 

# Expected Output 

For each C value: 
Confusion Matrix 
Accuracy, Precision, Recall, F1 
ROC-AUC 
Number of support vectors 
Summary table comparing C values (at least 3) 
Files: 
svm_linear_results.csv (C, metrics, #support_vectors) 
test_predictions.csv (CustomerID, Actual, Predicted, Score/Probability) 
Mandatory Tasks / Deliverables 

Preprocess categorical features (encoding) + scaling of numeric features 
Use Stratified train/test split with fixed random seed 
Show interpretation: how C affects margin and overfitting/underfitting 
Short conclusion: which C generalizes best and why 




# Interpretation

C is the regularization parameter that controls the trade-off between margin width and misclassification in a Support Vector Machine.

C = 0.1 (strong regularization)

Wider margin, allows more misclassification.

Slightly lower recall and F1.

Highest number of support vectors (2610).

C = 1 (moderate regularization)

Balanced margin and misclassification penalty.

Slight improvement in recall and F1 compared to C=0.1.

Slightly fewer support vectors (2600).

C = 10 (weak regularization)

Narrower margin, stronger penalty for misclassification.

Small improvement in F1 score.

Fewest support vectors (2597).

Overall observation
Accuracy and ROC-AUC remain almost the same across C values.

Increasing C slightly reduces support vectors but does not significantly improve performance.

Best generalizing model
C = 1, because it balances margin size and classification performance without overfitting.

Basically, when C is small, the model allows more misclassification but produces a wider margin. This improves generalization but may reduce training accuracy. As C increases, the classifier penalizes misclassification more strongly, resulting in a narrower margin and potentially overfitting the training data

C Value Effect Small C (0.1)-->wider margin, more misclassification

Medium C (1)-->balanced

Large C (10)-->narrow margin, risk of overfitting
