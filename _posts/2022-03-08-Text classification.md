---
layout: post
title: Text Classification
summary: Basic Knowledge of NLP。
featured-img: deep learning
language: chinese
category: NLP
---



# Text Classification

## Tasks

- Topic classification
- Sentiment analysis
- Native-language identification
- Natural language inference
- Automatic fact-checking
- Paraphrase

## 流程

- Identify a task of interest
- Collect an appropriate corpus
- Carry out annotation
- Select features
- Choose a machine learning algorithm
- Train mdel and tune hyperparameters using held-out development data
- Repeat earlier steps as needed
- Train final model
- Evaluate model on held-out test data

## Algorithms

### Naive Bayes

- Finds the class with the highest likelihood under Bayes lay

#### pros

- Fast to train and classify
- robust, low-variance → good for low data situations
- optimal classifier if independence assumption is correct
- extremely simple to implement

#### cons

- Independence assumption rarely holds
  - e.g., the scenoria in NLP, where considering prefix.
    - As usual, $$P(word='unfit',prefix='un-'|y)=P(prefix='un-',word='unfit'|y)P(word='unfit'|y)=1\times P(word='unfit'|y)$$
    - if use NB, $$P(word='unfit',prefix='un-'|y)=P(word='unfit'|y)P(prefix='un-'|y)$$
- low accuracy compared to similar methods in most situations
- smoothing required for unseen class/feature combinations

### Logistic Regression

#### Cons

‣ 训练速度慢 Slow to train;

‣ 需要标准化或归一化处理 Feature scaling needed

‣ 需要大量的数据 Requires a lot of data to work well in practice

‣ 容易导致 overfitting Choosing regularisation strategy is important since overfitting is a big problem

### Support Vector Machines

- Finds hyperplane which separates the training data with maximum margin

- be popular for NLP, mainly because it works well with huge feature sets and NLP problems often involve large feature sets

#### Pros

• 快且准 Fast and accurate linear classifier

• 能够支持非线性 kernel Can do non-linearity with kernel trick

• 在大特征集中表现良好 Works well with huge feature sets

#### Cons

• 多分类的效果不佳 Multiclass classification awkward

• 需要特征标准化 Feature scaling needed

• 难处理类不平衡问题 Deals poorly with class imbalances

• 可解释性差 Interpretability

### _K_-Nearest Neighbour

- Classify based on majority class of _k_-nearest training examples in feature space

#### Pros

• 简单且有效 Simple but surprisingly effective

• **不需要训练** No training required

• 适用于多分类 Inherently multiclass

• 在无穷大的数据集中能够找到 optimal Optimal classifier with infinite data

#### Cons

• 难选择 k Have to select _k_

• 难处理类不平衡问题 Issues with imbalanced classes

• 速度慢 Often slow (for finding the neighbours)

• 特征选取难 Features must be selected carefully

### Decision tree

#### Pros

• 训练测试速度快 Fast to build and test

• 不需要特征归一化 Feature scaling irrelevant

• 在小特征集中效果好 Good for small feature sets

• 能处理非线性可分的情况 Handles non-linearly-separable problems

#### Cons

• 可解释性差 In practice, not that interpretable

• 子树集合高度冗余 Highly redundant sub-trees

• 在大特征集中效果不佳 Not competitive for large feature sets

### Random Forests

#### Pros

• Usually more accurate and more robust than decision trees

• Great classifier for medium feature sets

• Training easily parallelised

#### Cons:

• Interpretability

• Slow with large feature sets

### Neural Networks

#### Pros

• Extremely powerful, dominant method in NLP and vision

• Little feature engineering

#### Cons

• Not an off-the-shelf classifier

• Many hyper-parameters, difficult to optimise

• Slow to train

• Prone to overfitting

## 参数调优 Hyper-parameter Tuning

### Dataset for tuning

- development set
- not the training set or the test set
- k-fold cross-validation

### Grid Search

for multiple hyper-parameters

