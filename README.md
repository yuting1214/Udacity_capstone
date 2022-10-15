# Udacity_capstone

## Problem

How can mail-order company acquire new clients more efficiently?

## Steps to Complete This Project
The project has three major steps: the customer segmentation report, the supervised learning model, and the Kaggle Competition.

1. Customer Segmentation Report
You'll begin the project by using unsupervised learning methods to analyze attributes of established customers and the general population in order to create customer segments.

2. Supervised Learning Model
You'll have access to a third dataset with attributes from targets of a mail order campaign. You'll use the previous analysis to build a machine learning model that predicts whether or not each individual will respond to the campaign.

3. Kaggle Competition
Once you've chosen a model, you'll use it to make predictions on the campaign data as part of a Kaggle Competition. You'll rank the individuals by how likely they are to convert to being a customer, and see how your modeling skills measure up against your fellow students.

## Details in each step

### 1. Customer Segmentation Report

1. Data preprocessing: 
    * Filter out some columns(too many missing values, erroneous recording
    * Impute missing values(Mean for numerical, Mode for categorical
    * Transform data(Standardization, One-hot encoding
2. Dimensionality reduction
    * PCA: reduce dimension while keeping the accounted variance
    * Scree plot: Select number of Principle Components
3. Clustering:
    * K-mean: Cluster the existing customers.(K=3)
    * Centers: Construct representative centers from the clusters
4. Categorize population:
    * Distance: Calculate the distance between the characteristics of each person and centers
    * Segment: If the closed distance between the centers meet the threshold, assign the cluster to each observation.

Finding:
1. Most of existing and potential customers are belong to cluster 1. Therefore, to promote the business, the stakeholders should focus on the customers in this segment. 
2. Around 30% of population are not assigned to any clusters. We could further check which cluster is the most closed one. And if there are some variables controlable, we could adjust these factors to make these people similar to the customers thereby increasing the chance of acquring these potential customers.

# Modeling(Imbalanced classification)

Here we provid five type of solutions to address the issues of imbalanced data.
These solutions related to the concepts of AutoML(Autogluon), Anomaly Detection, Over-sampling, and Ensemble Different Resampled Datasets.

## 
