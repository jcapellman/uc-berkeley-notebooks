### TCP Traffic Classification

**Jarred Capellman**

#### Executive summary

#### Rationale
Given that nearly everyone on the planet browses the Internet, being able to quickly determine if the packets are malicious would help provide a safer browsing experience for all Internet users.

#### Research Question
Can TCP traffic data from Chrome determine if the traffic is malicious or benign? 

#### Data Sources
I found a great data source on Kaggle Links to an external site.that includes both benign and malicious labeled data. I can potentially use the Firefox data for an additional test set. These data sets are 300mb each so I did not commit them to this repository.

#### Methodology
I will likely use a Random Forest, Gradient Boost, and SVM for my analysis and propose the one with the highest accuracy.  In addition, I will try to reduce the feature space, if possible, by doing a feature importance analysis.

I expect to be able to correctly classify traffic as either benign or malicious with> 50% accuracy. Training and Inference times I will not focus on given the focus on accuracy - however, I will note all the metrics in my analysis.

#### Results
##### EDA Results
Given the number of outliers was quite high at 7076, the data has a lot of diversity, making training a model challenging.

Subsequent steps should include using Ray or another hyper-parameter tuning technique to lower the count, such as increasing the contamination parameter to 0.02 from 0.01. The feature selection, as shown in the plots, indicates not all features are important, so reducing the feature space is also a necessary step.

#### Next steps
1. Data Preprocessing: Use outlier detection (e.g., Isolation Forest), impute missing values.
2. Feature Engineering: Create interaction and polynomial features, scale, and normalize.
3. Model Selection: Implement cross-validation, try ensemble methods.
4. Hyperparameter Tuning: Utilize tools like Optuna, conduct grid/random search.
5. Model Evaluation: Use multiple metrics, plot learning curves, conduct error analysis.
6. Model Interpretability: Analyze feature importance, use SHAP values.

#### Outline of project

- [Exploratory Data Analysis Notebook](https://github.com/jcapellman/uc-berkeley-notebooks/blob/main/Capstone_Project/CapstoneProject_eda.ipynb)


##### Contact and Further Information
- [Secure DNS Test Traffic DoHBrw-2020 Kaggle Dataset](https://www.kaggle.com/datasets/peterfriedrich1/dns-test-traffic-dohbrw2020?resource=download)
