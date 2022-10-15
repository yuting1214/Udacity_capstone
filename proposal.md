# Domain background
In the pre-digital era, customer segmenting was done solely by salesmen, who approached the customers. By getting to know more about their customers, they could collect more than enough information about demographics, their requests and painstaking issues, and their overall mood based on non-verbal communication. This made it possible to immediately address any concerns about the products, matching the words and expressions used by the customer, being able to upsell them on the spot, and reinforcing their purchase intent. 

When the customer has to deal with an online experience, all of this has to be replaced and scaled. And based on what other customers in the store previously bought, in conjunction with this particular search, cross- and upsell offers could be made with great confidence. Part of the demographic information is readily available as soon as someone signs up – most times you will know their age, location, and whatever data you ask for. There is an incredible amount of data generated from all these interactions – and machine learning is what makes it possible to assess behaviors to ascertain patterns. These patterns help you make sense of data sets and make more effective marketing decisions. For example, you can create ultra-targeted campaigns with the most relevant messages, and increase your conversion rate by offering customers exactly what they are looking for.

In our project, we try to utilize the data to find the relationship between existing customers and potential customers to reduce the cost of customer acquisition. Since demographic information is usually high-dimensional and intractable, machine learning techniques provide handy and automatic solutions 
to detect the hidden patterns behind the data. These patterns could help stakeholders form feasible solutions to promote business.

# Problem Statement

Part 1. Customers Segmentation: related to dimensionality reduction, clustering, and segmentation.

* Quantifiable: Group the customers with similar demographic traits with algorithmic measurements provided by unsupervised learning. 
* Measurable: Once established the clusters, we could further compare the purchase behavior in each cluster to test the validity of the clustering
* Replicable: The trained model could be applied to future customers and keep monitoring the variations of the structure of previously constructed clusters.

Part 2. Predict potential customers: related to the problem of imbalanced label prediction.

* Quantifiable: Predict the probabilities of becoming new customers based on demographic information.
* Measurable: Compare the number of actual acquired customers and predicted potential customers.
* Replicable: The trained model could adapt to new incoming data and keep monitoring the model's performance once the model gets deployed.


# Solution statement

For Part 1.,
1. Use an unsupervised learning method(PCA) for dimensionality reduction to extract the transformed features while reducing the number of input variables 
2. Use an unsupervised learning method(K-means) to cluster the customers.
3. Use the Euclidean distance metric to measure the similarities between existing customers and the population.

For Part 2., 
1. Data Preprocessing to adjust the data format applicable to the models.
2. Over-sampling(SMOTE) technique to address the issues of imbalanced labels.
3. Supervised learning models(Logistic Regression & XGBoost) to predict the probabilities of becoming potential customers based on preprocessed information.

# Datasets

There are four data files associated with this project:

- `Udacity_AZDIAS_052018.csv`: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).
- `Udacity_CUSTOMERS_052018.csv`: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).
- `Udacity_MAILOUT_052018_TRAIN.csv`: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).
- `Udacity_MAILOUT_052018_TEST.csv`: Demographics data for individuals who were targets of a marketing campaign; 42 833 persons (rows) x 366 (columns).

Especially,

For Part 1., use
- `Udacity_AZDIAS_052018.csv`: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).
- `Udacity_CUSTOMERS_052018.csv`: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).

For Part 2., use
- `Udacity_MAILOUT_052018_TRAIN.csv`: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).
- `Udacity_MAILOUT_052018_TEST.csv`: Demographics data for individuals who were targets of a marketing campaign; 42 833 persons (rows) x 366 (columns).

# Benchmark model

For Part 1., use the subset of columns from the original data to segment the customers. And compare the benchmark model with the following unsupervised learning methods.

For Part 2., start with a logistic regression model without any treatment on the issue of imbalanced labels. And compare the benchmark model with the following learning supervised methods with adds-on treatments.

# Evaluation metrics

For Part 1.,

1. PCA: proportion of explained variance as a metric
2. K-Mean: Inertia(sum of the square of between centers distances)

For Part 2. 
1. Binary classification: AUC(Area Under the ROC Curve) and ROC curve (receiver operating characteristic curve).

# Outline:

Part 1. Customers Segmentation:

1. Data preprocessing: 
    * Filter out some columns(too many missing values, erroneous recording
    * Impute missing values(Mean for numerical, Mode for categorical
    * Transform data(Standardization, One-hot encoding
2. Dimensionality reduction
    * PCA: reduce dimension while keeping the accounted variance
    * Scree plot: Select the number of Principle Components
3. Clustering:
    * K-mean: Cluster the existing customers. (K=3)
    * Centers: Construct representative centers from the clusters
4. Categorize population:
    * Distance: Calculate the distance between the characteristics of each person and centers
    * Segment: If the closed distance between the centers meets the threshold, assign the cluster to each observation.

Part 2. Predict potential customers

Here we provide four types of methods to address the issues of imbalanced data.
These solutions related to the concepts of AutoML(Autogluon), Anomaly Detection, Over-sampling, and Ensemble Different Resampled Datasets.

1. Data preprocessing: 
    * Filter out some columns(too many missing values, erroneous recording
    * Impute missing values(Mean for numerical, Mode for categorical
    * Transform data(Standardization, One-hot encoding
2. Modeling:
    * AutoGluon: automatic machine learning to train models
    * Scikit-learn: use off-the-shelf tree-based models from scikit-learn
    * Over-sampling: use SMOTE to create synthetic samples from the minority group to deal with imbalanced labels.
    * Ensemble of samplers: use the models with the mechanism to adjust the imbalanced labels during training
    * Anomaly Detection: transform the original problem, imbalanced classification, as an anomaly detection problem.

# Reference:
https://www.prefixbox.com/blog/machine-learning-for-ecommerce/#ee8af4c53d02
