# Domain background

Nowadays, numerous e-commerce or sales companies have data about their customers and the access to demographic information for the general population. They're eager to utilize the data to find the relationship between the existing customers and potential customers to reduce the cost of customer acquisition. Since demographic information is usually high-dimensional and intractable, machine learning techniques provide handy and automatic solutions 
to detect the hidden patterns behind the data. These patterns could help them form feasible solutions to promote business.

# Problem Statement

Part 1. Customers Segmentation: related to dimensionality reduction, clustering, and segmentation.

Part 2. Predict potential customers: related to the problem of imbalanced label prediction.

# Solution statement

For Part 1.,
1. Use unsupervised learning methods for dimensionality reduction to extract the transformed features while reduce the numbers of input variables 
2. Use unsupervised learning methods to cluster the customers.
3. Use distance metric to measure the similarities between existing customers and the population.

For Part 2., 
1. Data Preprocessing to adjust the data format applicable for the models.
2. Over-sampling technique to address the issues of imbalanced lables.
3. Supervised learning models to predict the probabilities of becoming potential customers based on preprocessed information.

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

For Part 1., PCA for dimensionality reduction; K-mean for clustering.

For Part 2., Supervised learning models with some adjustments to deal with the issue of imbalanced labels.

# Evaluation metrics

For Part 1.,

a valid evaluation metric could be any reasonable decisions from the processing of data, so there is no clear metric to measure the success.

For Part 2. Since it's a binary classification problem, use AUC as a measurement of models' performance/

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

Here we provide five types of methods to address the issues of imbalanced data.
These solutions related to the concepts of AutoML(Autogluon), Anomaly Detection, Over-sampling, and Ensemble Different Resampled Datasets.

1. Data preprocessing: 
    * Filter out some columns(too many missing values, erroneous recording
    * Impute missing values(Mean for numerical, Mode for categorical
    * Transform data(Standardization, One-hot encoding
2. Modeling:
    * 

