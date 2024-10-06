---
layout: post
title: An overview of Traditional Machine Learning
---

<center><img width="600" alt="image" src="https://github.com/user-attachments/assets/886d2c41-c09b-4a21-b2a5-15e80111fad9"></center>

Machine learning (ML) is a subset of artificial intelligence (AI) focused on building systems that can learn from data and improve their performance over time. While deep learning has become popular, traditional machine learning techniques are still **highly relevant** due to their simplicity, interpretability, and efficiency, especially when working with smaller datasets. This post provides an overview of the fundamental concepts in traditional machine learning.

In this post, we will go through the main types of traditional machine learning and talk about them in brief:
<center><img width="953" alt="image" src="https://github.com/user-attachments/assets/83f35411-ded1-4040-a30f-d5e90cd84556"></center>



## 1. **Supervised Learning**
In supervised learning, the model learns from a labeled dataset, which **contains input-output pairs**. The goal is to predict the output for new inputs based on the learned relationships.

<center><img width="227" alt="image" src="https://github.com/user-attachments/assets/8faf0dcc-66ab-4e0d-a4f8-18dcc0749061"></center>

### Types of Supervised Learning:
Supervised Learning is sub-categorized as two differeent categories, namely:
- **Classification**: Predicts a categorical label (e.g. if an email is spam or not spam)
- **Regression**: Predicts a continuous value (e.g. house prices)

## 2. **Unsupervised Learning**:
It involves training a model on data without labeled responses.The goal is to infer the natural structure present in a dataset.

An example of unsupervised learning is clustering as presented in the diagram below:
<center><img width="592" alt="image" src="https://github.com/user-attachments/assets/3835ff69-3cf5-4edd-95a3-d6741e4403b3"></center>

### Types of Unsupervised Learning:
- **Clustering**: Groups data points based on similarity (e.g., k-Means, Hierarchical Clustering, DBSCAN).
- **Association**: Discovers rules that describe large portions of the dataset (e.g., Apriori algorithm for market basket analysis).
- **Dimensionality Reduction**: Reduces the number of input features (e.g., Principal Component Analysis (PCA), t-Distributed Stochastic Neighbor Embedding (t-SNE)).

## 3. **Semi-Supervised Learning**
Semi-supervised learning falls between supervised and unsupervised learning. It uses a small amount of labeled data along with a large amount of unlabeled data for training. This is useful when labeling data is expensive or time-consuming.

An example of this could be Google Photos, where it asks you clusters all the images of a person in your gallery, and then asks the name of the person once, and tags all the images of that person with the same name

## 4. **Reinforcement Learning**
Reinforcement learning is an area where an agent learns to make decisions by performing certain actions and receiving rewards or penalties. It's commonly used in robotics, gaming, and real-time decision-making.
<center><img width="629" alt="image" src="https://github.com/user-attachments/assets/3c74de35-daec-4812-8f9b-d01f050991c5"></center>


