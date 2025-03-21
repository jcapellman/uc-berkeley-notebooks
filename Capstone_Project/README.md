### TCP Traffic Classification: Capstone Project

**Jarred Capellman**

---

#### Table of Contents
1. [Project Overview](#project-overview)
2. [Project Goals](#project-goals)
3. [Findings](#findings)
4. [Results and Conclusion](#results-and-conclusion)
5. [Future Research and Development](#future-research-and-development)
6. [Rationale](#rationale)
7. [Research Question](#research-question)
8. [Data Sources](#data-sources)
9. [Methodology](#methodology)
10. [Project Links](#project-links)
11. [Contact and Further Information](#contact-and-further-information)

#### Executive summary

### Project Overview
---
The accurate classification of TCP traffic is crucial for enhancing cybersecurity measures. By identifying malicious traffic, businesses can prevent potential security breaches, protect sensitive data, and maintain the integrity of their network infrastructure. This project aims to develop a reliable model that can aid real-time traffic monitoring and threat detection, thereby contributing to a safer internet environment for all users.

### Project Goals
---

* Classification Accuracy: Develop a machine learning model to classify TCP traffic with minimal false positives and negatives accurately.

* Model Generalization: Ensure that the model generalizes well to unseen data beyond the specific dataset used in this research.

* Data Analysis: Thoroughly investigate the dataset to prevent data leakage and ensure balanced performance across all classes.

* Computational Efficiency: Optimize the model’s computational efficiency in terms of training and inference time.

* Model Explainability: Enhance the interpretability of the model to understand its decision-making process.
* Continuous Evaluation: Plan for constant monitoring and re-evaluation of the model to account for data drifts over time.

This project leverages a dataset titled "Secure DNS Test Traffic DoHBrw-2020" sourced from Kaggle. The dataset is large and diverse and requires extensive preprocessing, including outlier detection and handling of missing values, to ensure optimal performance. The final model aims to provide a robust solution for distinguishing between benign and malicious TCP traffic, contributing to safer internet usage.

### Findings
---

The [Model Training and Evaluation Notebook](https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Capstone_Project/CapstoneProject_Modeling_and_Evaluation.ipynb) analyzed the three modeling techniques.

The summary of these findings:

#### Logistic Regression
- **Accuracy:** Achieved a good overall accuracy.
- **Actionable Item:** Consider using Logistic Regression for quick and efficient initial classification.

#### Random Forest
- **Accuracy:** Outperformed Logistic Regression.
- **Feature Importance:** Identified key features contributing to classification.
- **Actionable Item:** Use Random Forest for more robust classification and feature insights.

#### Support Vector Machine (SVM)
- **Accuracy:** Achieved the highest accuracy with no false positives or negatives.
- **Training Time:** Required more training time.
- **Actionable Item:** Use SVM for the most accurate results, especially when training time is not a constraint.

A more detailed analysis looking at the Confusion Matrix shows how well each model performed for the summary findings can be found in the [Model Training and Evaluation Notebook](https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Capstone_Project/CapstoneProject_Modeling_and_Evaluation.ipynb), however a brief visual breakdown can be found below.

## Detailed Analysis
---
A brief description of the confusion matrix is as follows:

- Top Left: True Positive (TP)
- Top Right: False Negative (FN)
- Bottom Left: False Positive (FP)
- Bottom Right: True Negative (TN)

Descriptions:
- True Positive (TP): The number of correct predictions where the model predicted the positive class, and the actual class was also positive.
- False Negative (FN): The number of incorrect predictions where the model predicted the negative class, but the actual class was positive.
- False Positive (FP): The number of incorrect predictions where the model predicted the positive class, but the actual class was negative.
- True Negative (TN): The number of correct predictions where the model predicted the negative class, and the actual class was also negative.

Ideally, with model training, you would want 0 False Negatives and 0 False Negatives.

#### Logistic Regression
Logistic Regression is a simple yet effective model for binary classification tasks. The confusion matrix for Logistic Regression is shown below:

![Logistic Regression Confusion Matrix](https://raw.githubusercontent.com/jcapellman/uc-berkeley-notebooks/main/Capstone_Project/images/confusion_matrix_logistic_regression.png)

- **Accuracy:** The Logistic Regression model achieved a good overall accuracy, correctly classifying a substantial portion of the TCP traffic data.
- **Precision and Recall:** The precision and recall values indicate how well the model can identify both benign and malicious traffic. The model performed reasonably well but had some false positives and false negatives.
- **F1 Score:** The F1 score balances precision and recall, providing a single metric to evaluate the model's performance. The cross-validated and mean F1 scores are depicted in the graphs below.

#### Random Forest
Random Forest is an ensemble learning method known for its robustness and ability to handle imbalanced datasets. The confusion matrix for Random Forest is shown below:

![Random Forest Confusion Matrix](https://raw.githubusercontent.com/jcapellman/uc-berkeley-notebooks/main/Capstone_Project/images/confusion_matrix_random_forest.png)

- **Accuracy:** The Random Forest model outperformed Logistic Regression in terms of accuracy, correctly classifying a higher percentage of the TCP traffic data.
- **Feature Importance:** One of the key strengths of Random Forest is its ability to provide insights into feature importance. The model identified the most significant features contributing to the classification.
- **F1 Score:** The F1 scores for Random Forest were higher than those of Logistic Regression, indicating better overall performance. The cross-validated and mean F1 scores are depicted in the graphs below.

#### Support Vector Machine (SVM)
SVMs are powerful models for binary classification, particularly effective in high-dimensional spaces. The confusion matrix for SVM is shown below:

![SVM Confusion Matrix](https://raw.githubusercontent.com/jcapellman/uc-berkeley-notebooks/main/Capstone_Project/images/confusion_matrix_svm.png)

- **Accuracy:** The SVM model achieved the highest accuracy among the three models, correctly classifying the holdout test set with 0 false positives and 0 false negatives.
- **Training Time:** While the SVM model provided excellent classification results, it required significantly more training time than Logistic Regression and Random Forest.
- **F1 Score:** The F1 scores for SVM were the highest, indicating superior performance in terms of both precision and recall. The cross-validated and mean F1 scores are depicted in the graphs below.

In addition to the confusion matrices, F1 Scores were chosen as the primary metric for evaluation. Below are the cross-validated and mean F1 scores for all three models:

![Cross-Validated](https://raw.githubusercontent.com/jcapellman/uc-berkeley-notebooks/main/Capstone_Project/images/cross-validation-f1-scores.png)

![Mean F1 Scores](https://raw.githubusercontent.com/jcapellman/uc-berkeley-notebooks/main/Capstone_Project/images/mean-f1-scores.png)

These findings highlight the strengths and weaknesses of each model, providing a comprehensive comparison to guide future research and development efforts. In addition to showing SVM having a perfect score.

### Results and conclusion
---

As shown above, in the Confusion Matrix graphics, the SVM model correctly classified the holdout test set with 0 false positives and 0 false negatives. The model training time was about 2X the time, however the model performance which was the highest priority, SVM was the clear modelling choice.


### Future research and development
---
1. **Validate Generalization:**
   - Test the model on additional datasets to ensure its generalizability.

2. **Analyze the Data:**
   - Investigate the dataset for potential data leakage and ensure balanced class performance.

3. **Measure Computational Efficiency:**
   - Optimize the model to reduce training and inference times.

4. **Improve Explainability:**
   - Enhance the interpretability of the SVM model.

5. **Continuous Evaluation:**
   - Implement a pipeline for periodic retraining to account for data drifts.
---

### Rationale

Nearly everyone uses the internet daily. Identifying if the packets being transferred from their laptops are malicious can help ensure a safer browsing experience for all Internet users.

---

### Research Question

Can TCP traffic data collected from Google Chrome determine if the traffic is malicious or benign?

---

### Data Sources

The dataset used in this project was sourced from Kaggle and is titled **Secure DNS Test Traffic DoHBrw-2020**. It is a comprehensive dataset containing labeled data for both benign and malicious TCP traffic, making it a critical resource for this analysis.

As noted below, the size of the data source was large, therefore it is not included in this repository.

#### Data Sources Structure
![Datasets](https://raw.githubusercontent.com/jcapellman/uc-berkeley-notebooks/main/Capstone_Project/images/datasets.png)

After downloading the datasets from Kaggle, I renamed the two files to **raw_benign.csv** and **raw_malicious.csv** to make my notebook clearer.

Afterwards, as noted above and in the notebook the datasets were labeled and then combined into one csv, **combined_traffic.csv**.

Lastly, after data cleaning was performed the DataFrame was exported to a csv, **cleaned_data.csv** to avoid having to re-run the numerous steps repeatedly.

#### Key Features of the Dataset:

1. **Size and Scope:**
   - The dataset is approximately 300MB, offering a significant volume of data to ensure robust analysis and model training.
   - It includes a wide range of TCP traffic samples, ensuring data diversity and enabling the differentiation of benign and malicious traffic patterns.

2. **Structure:**
   - The dataset is organized into labeled categories for easy identification.
   - Each row represents a single instance of TCP traffic, accompanied by key features such as packet size, duration, protocols, and other relevant attributes.

3. **Quality:**
   - The dataset has been curated to minimize noise and maximize the relevance of the features provided.
   - However, like many real-world datasets, it presents challenges such as outliers and missing values, which require careful preprocessing and handling.

4. **Potential for Expansion:**
   - Additional datasets, such as traffic data from Firefox browsers, can be incorporated for testing and validation. This would add variability and improve the generalizability of the models developed.

5. **Accessibility:**
   - Due to its size, the dataset has not been committed to this repository. Instead, it is accessible via Kaggle through the following link:  
     [Secure DNS Test Traffic DoHBrw-2020 Kaggle Dataset](https://www.kaggle.com/datasets/peterfriedrich1/dns-test-traffic-dohbrw2020?resource=download).

#### Benefits of the Dataset:
- **Diversity and Realism:** This dataset mimics real-world TCP traffic scenarios, including a variety of benign and malicious behavior patterns.
- **Applicability:** It provides an excellent foundation for exploring the research question and developing a machine-learning model for TCP traffic classification.
- **Educational Value:** Offers a valuable opportunity to experiment with data preprocessing, feature engineering, and model evaluation techniques.

#### Limitations:
- The dataset includes many outliers, as identified during Exploratory Data Analysis (EDA). These outliers add complexity to the task of training machine learning models.
- Preprocessing steps are necessary to ensure optimal performance, including outlier detection and handling of missing values.

#### Final Data Source
Some transformations were required as noted in the Exploratory Data Analysis Notebook, namely labeling the data since they are in two files, combine them, save to disk and then split the train and test set. Using the included Notebook this process is described in detail.

---

### Methodology

The project follows these steps:

1. **Data Preprocessing:** Includes outlier detection (e.g., Isolation Forest) and imputing missing values.
2. **Feature Engineering:** Creation of interaction and polynomial features, along with scaling and normalization.
3. **Model Selection:** Evaluating Random Forest, Gradient Boost, and SVM to determine the best model based on accuracy.
4. **Feature Importance Analysis:** Reducing the feature space by identifying and prioritizing the most significant features.
5. **Hyperparameter Tuning:** Using tools like Ray or Optuna to refine model performance.
6. **Model Evaluation:** Emphasis on classification accuracy, while also noting training and inference times.

### Project Links
---

[Link to Exploratory Data Analysis Notebook](https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Capstone_Project/CapstoneProject_eda.ipynb)

[Link to Model Training and Evaluation Notebook](https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Capstone_Project/CapstoneProject_Modeling_and_Evaluation.ipynb)

[Link to Kaggle Dataset](https://www.kaggle.com/datasets/peterfriedrich1/dns-test-traffic-dohbrw2020?resource=download)

### Contact and Further Information
---

Research by Jarred Capellman

Email: jcapellman@hotmail.com 

[LinkedIn](linkedin.com/in/jcapellman)
