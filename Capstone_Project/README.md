### TCP Traffic Classification: Capstone Project

**Jarred Capellman**

---
#### Executive summary
**Project overview and goals:**

**Findings:**

**Results and conclusion:**

**Future research and development:**

**Next steps and recommendations:**

#### Rationale

Nearly everyone uses the internet daily. Quickly identifying if the packets being transferred from their laptops are malicious can help ensure a safer browsing experience for all Internet users.

---

#### Research Question

Can TCP traffic data collected from Google Chrome determine if the traffic is malicious or benign?

---

#### Data Sources

The dataset used in this project was sourced from Kaggle and is titled **Secure DNS Test Traffic DoHBrw-2020**. It is a comprehensive dataset containing labeled data for both benign and malicious TCP traffic, making it a critical resource for this analysis.

As noted below, the size of the data source was large, therefore it is not included in this repository.

##### Key Features of the Dataset:

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

##### Benefits of the Dataset:
- **Diversity and Realism:** This dataset mimics real-world TCP traffic scenarios, including a variety of benign and malicious behavior patterns.
- **Applicability:** It provides an excellent foundation for exploring the research question and developing a machine learning model for TCP traffic classification.
- **Educational Value:** Offers a valuable opportunity to experiment with data preprocessing, feature engineering, and model evaluation techniques.

##### Limitations:
- The dataset includes a significant number of outliers, as identified during Exploratory Data Analysis (EDA). These outliers add complexity to the task of training machine learning models.
- Preprocessing steps, including outlier detection and handling of missing values, are necessary to ensure optimal performance.

##### Final Data Source
Some transformations were required as noted in the Exploratory Data Analysis Notebook, namely labeling the data since they are in two files, combine them, save to disk and then split the train and test set. Using the included Notebook this process is described in detail.

---

#### Methodology

The project follows these steps:

1. **Data Preprocessing:** Includes outlier detection (e.g., Isolation Forest) and imputing missing values.
2. **Feature Engineering:** Creation of interaction and polynomial features, along with scaling and normalization.
3. **Model Selection:** Evaluating Random Forest, Gradient Boost, and SVM to determine the best model based on accuracy.
4. **Feature Importance Analysis:** Reducing the feature space by identifying and prioritizing the most significant features.
5. **Hyperparameter Tuning:** Using tools like Ray or Optuna to refine model performance.
6. **Model Evaluation:** Emphasis on classification accuracy, while also noting training and inference times.

---

#### Results

##### Exploratory Data Analysis (EDA)

- Identified a high number of outliers (7076), reflecting diversity in the dataset. This diversity poses challenges for training models.
- Feature selection analysis indicates that not all features are crucial, underlining the need for dimensionality reduction.

##### Key Insights and Challenges

- Training models on the dataset requires addressing outliers more effectively, such as increasing the contamination parameter in the Isolation Forest algorithm (e.g., from 0.01 to 0.02).

---

#### Next Steps

1. Enhance data preprocessing, focusing on handling outliers and missing values.
2. Optimize feature selection by scaling, normalization, and feature engineering.
3. Explore ensemble methods and cross-validation for improved model selection.
4. Conduct hyperparameter tuning using tools like Optuna or grid/random search.
5. Analyze feature importance using SHAP values for improved interpretability.

---

#### Outline of Project

[Link to Exploratory Data Analysis Notebook](https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Capstone_Project/CapstoneProject_eda.ipynb)

[Link to Kaggle Dataset](https://www.kaggle.com/datasets/peterfriedrich1/dns-test-traffic-dohbrw2020?resource=download)

---

#### Contact and Further Information

Jarred Capellman

Email: jcapellman@hotmail.com 

[LinkedIn](linkedin.com/in/jcapellman)