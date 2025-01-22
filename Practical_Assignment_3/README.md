# Practical Application 3
This notebook analyzes the results from the UCI Machine Learning document on marketing. The analysis started with data exploration and cleaning since many columns needed cleaning (unknown values, categorical, etc.). Model building was then performed across Logistic Regression, KNN, Decision Tree, and SVM algorithms. These models were then evaluated for time, training, and test accuracy.

The notebook linked below shows the analysis in detail.

## Notebook
https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Practical_Assignment_3/practical_assignment_3.ipynb

## Results
Below are the table results after training the four different models:

                     Model  Train Time  Train Accuracy  Test Accuracy
    0  Logistic Regression    0.159100        0.848134       0.848992
    1                  KNN    0.010530        0.846586       0.832362
    2        Decision Tree    0.379105        0.871775       0.820102
    3                  SVM  104.263143        0.848194       0.848992

As you can see, the SVM training time was the longest and did not provide better accuracy. Decision Tree showed the best train accuracy and the worst test accuracy. KNN and Logistic Regression offer the best time and accuracy trade offs.
