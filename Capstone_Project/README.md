### TCP Traffic Classification

**Jarred Capellman**

#### Executive summary

#### Rationale
Given that nearly everyone on the planet browses the Internet, being able to quickly determine if the packets are malicious would help provide a safer browsing experience for all Internet users.

#### Research Question
Can TCP traffic data from Chrome determine if the traffic is malicious or benign? 

#### Data Sources
I found a great data source on Kaggle Links to an external site.that includes both benign and malicious labeled data. I can potentially use the Firefox data for an additional test set.

#### Methodology
I will likely use a Random Forest, Gradient Boost, and SVM for my analysis and propose the one with the highest accuracy.  In addition, I will try to reduce the feature space, if possible, by doing a feature importance analysis.

I expect to be able to correctly classify traffic as either benign or malicious with> 50% accuracy. Training and Inference times I will not focus on given the focus on accuracy - however, I will note all the metrics in my analysis.

#### Results
##### EDA Results
TBD

#### Next steps
TBD

#### Outline of project

- [Exploratory Data Analysis Notebook](https://www.kaggle.com/datasets/peterfriedrich1/dns-test-traffic-dohbrw2020?resource=download)


##### Contact and Further Information
- [Secure DNS Test Traffic DoHBrw-2020 Kaggle Dataset](https://www.kaggle.com/datasets/peterfriedrich1/dns-test-traffic-dohbrw2020?resource=download)