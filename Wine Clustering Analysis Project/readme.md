Wine Clustering Analysis Project
Overview
This project performs an unsupervised clustering analysis on the Wine dataset from scikit-learn. Using K-Means clustering with hyperparameter tuning, we identify natural groupings in the wine samples based on their chemical properties. The analysis includes data preprocessing, model optimization, visualization, and cluster interpretation.

Key Features
Data Preparation: Standard scaling of 13 chemical feature measurements

Model Pipeline: Integrated preprocessing and clustering in a scikit-learn Pipeline

Hyperparameter Tuning: GridSearchCV to optimize:

Number of clusters (2-5)

Initialization method (k-means++ or random)

Number of initializations (10 or 20)

Evaluation: Silhouette scoring with checks for degenerate clustering

Visualization:

2D PCA projection of clusters

Feature distribution analysis by cluster

Pairplots of most significant features

Technical Details
Python Libraries: scikit-learn, pandas, numpy, matplotlib, seaborn

Machine Learning Techniques:

K-Means clustering

Principal Component Analysis (PCA) for visualization

Silhouette analysis for cluster validation

Results
The optimal clustering configuration achieved a silhouette score of .217 and Adjusted Rand Index of 0.716 with 5 clusters

Cluster analysis reveals distinct patterns in chemical composition across the identified groups.