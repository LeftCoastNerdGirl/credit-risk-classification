# Credit Risk Classification using scikit-learn

## Overview of the Analysis

The purpose of this analysis is to use historical lending data to build a machine learning model that predicts risk of loan default, grouping potential borrowers into groups predicted to be 'Healthy Loans' or 'High-Risk Loans'.  
The data includes details of load size and total debt, interest rate, borrower's income and debt to income ratio, as well as number of accounts and any derogatory marks on the accounts.  
The target for the prediction is the 'loan_status'. The model will be trained using the remaining variables, then tested to see if it has learned how to use those variables to predict a healthy or high risk loan.  


## Overview of the Analysis
 
* Imported the csv data file using Pandas and formatted as a data frame.  
* Separated the loan status as the y variable and the remainder of the data points as the X variable.  
* Used the sklearn train_test_split function to divide the data set into one group of train data to train the model and a second set of data to test the accuracy of the model's ability to predict.  
* Imported LogisticRegression from sklearn to create the model.  
* Trained the model.  
* Used the confusion matrix and classification report tools imported from sklearn to validate the accuracy of the model.  

 
## Results

* Confusion matrix  

<img width="502" alt="Screenshot 2024-03-16 at 6 47 02 PM" src="https://github.com/LeftCoastNerdGirl/credit-risk-classification/assets/145019579/0b3fdac4-6e31-47a5-a14f-41dfaa2514c0">



* Out of 18,765 loan statuses classified as healthy, the model predicted 18,663 as healthy and 102 as high risk, which is a very good accuracy rate. For the 619 loans that were actualy high risk, the model predicted 563 correctly and 56 in error. While the rate of false positives for the high risk loans was lower, it should be noted that the sample was extremely biased toward heathly loans - 18,765 healthy loans vs 563 high risk loans, so the model trained with this bias, as shown by the significantly higher accuracy for the healthy loans.

* Classification report

  <img width="486" alt="Screenshot 2024-03-16 at 6 47 14 PM" src="https://github.com/LeftCoastNerdGirl/credit-risk-classification/assets/145019579/147b4f2d-3a57-4f59-86b0-850a1f2d7514">


* Accuracy score
The accuracy score compares the sum of the true negatives plus the true positives to the sum of the entire test sample. It an answer the question - of all of the predictions made, how many were true. The accuracy rate for the model is 99%, a very high degree of accuracy.

* Precision score
The precision score for the healthy loans is 100%. As noted in the confusion matrix, there were only 102 false negatives out of 18765 loans tested. The model trained to predict healthy loans with accuracy.
The precision score for the high risk loans is 85%. Though less accurate than the healthy loan precitions, 85% is a decent score.

* Recall score
The recall score for healthy loans is 99%. Again, a high accuracy rate. This score indicates how many of the truly healthy loans the model actually predicted correctly, highlighting the likelihood of false negatives.
The recall score for high risk loans is lower at 91%, but is still a good result. The model is trained to capture 91% of the high risk loans accurately, leavin 0% chance of false negatives.


## Summary

The classification report indicates a high accuracy rate, precision, and recall for identifying healthy loans. The model performs well in correctly predicting both true positives and true negatives for healthy loans, while also effectively minimizing false positives, indicating its proficiency in distinguishing healthy loans from the rest.  
The precision score for high-risk loans is 85%, indicating that when the model predicts a loan as high risk, it is accurate 85% of the time. This suggests that the model performs well in minimizing false positives, where healthy loans are incorrectly labeled as high risk. The recall score for high-risk loans is 91%, indicating that the model correctly identifies 91% of actual high-risk loans. This implies the model's effectiveness in capturing most high-risk loans, though it may still miss some (false negatives).

# Recommendation

The model demonstrates remarkable success in predicting healthy loans. This is evidenced by the fact that nearly 97% of the loans within the dataset are classified as healthy. This abundance of healthy instances in the dataset contributes to the model's robust accuracy in identifying them. The model's proficiency in recognizing healthy loans aligns with the dataset's composition, reflecting its strong performance in this specific classification task.  
The model's performance in identifying high-risk loans is hindered by the scarcity of such instances in the training dataset. With a precision score of 85%, it means that 15% of borrowers are incorrectly labeled as healthy, posing a potential risk for lenders. This misclassification could lead to unintended consequences, including financial losses or increased default rates. Additionally, the model's recall score of 91% indicates that it accurately identifies 91% of actual high-risk loans. However, the 9% of loans falsely classified as high risk may lead to missed opportunities for growth, as deserving borrowers could be unfairly denied loans. Balancing the need to mitigate risks with the potential for missed opportunities is crucial for optimizing lending decisions and ensuring responsible financial practices.  
Considering the risks associated with lower accuracy rates in predicting high-risk loans, I propose leveraging the model to evaluate a dataset featuring a more balanced ratio between healthy loans and high-risk loans. By exposing the model to a diverse range of loan types, we can enhance its ability to accurately identify high-risk borrowers. This approach not only fosters a more comprehensive understanding of the lending landscape but also strengthens the model's predictive capabilities, thereby enabling more informed decision-making and risk mitigation strategies for lenders.  
