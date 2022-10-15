# Outline:

Part 1. Customers Segmentation

Part 2. Predict potential customers

# Domain background

Many e-commerce or sales companies have data about customers and the access to the demographics information for the general population. 
They want to find the relationship between the existing customers and potential customers to reduce the cost of customers acquisition.
Since demographics information are usually high dimensional and intractable, machine learning techniques provide handy and automatic solutions 
to detect the hidden patterns behind the data. These pattern could help us form feasible solutions to promote business. 

# Problem Statement

Part 1. Customers Segmentation related to dimensional reduction, clustering and segmentation.

Part 2. Predict potential customers related to the problem of imbalamced lable prediciton.

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

# Solution statement

For Part 1., use unsupervised learning methods to cluster the customers.

For Part 2., use supervised learning methods to predict the potential customers.

# Benchmark model

For Part 1., PCA for dimenionality reduction; K-mean for cluserting.

For Part 2., Supervised learning models with some adjustment to deal with the issue of imbalanced labels.

# Evaluation metrics

For Part 1. an valid evaluation metric could be any reasonable decisions from the processing of data, so there is no clear metric to measure the success.
For Part 2. Since it's a binary classification problem, use AUC as a measurement of models' performance/
