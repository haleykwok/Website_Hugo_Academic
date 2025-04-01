---
title: COMP1004 Introduction to Artificial Intelligence and Data Analytics
date: 2022-12-20
updated: 2023-05-20
tags: [2022, Course Notes, Computer Science] 
categories: "Course Notes"
keywords:
summary: The overview of course COMP1004 Introduction to Artificial Intelligence and Data Analytics
top_img: 
comments: true
cover:
toc:
toc_number:
toc_style_simple:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax: true
katex:
aplayer:
highlight_shrink:
aside:
abcjs:
draft: true
---


<span style = 'font-family: Times New Roman'>

> 📢 Disclaimer
> Copyright © [The Hong Kong Polytechnic University, Faculty of Engineering, Department of Computing](https://www.polyu.edu.hk/comp/)
> The lecture notes is for reference only, permission is hereby granted, free of charge, to any person obtaining a copy of this documentation file, to deal in the Page without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Page is furnished to do so.
> The authors or copyright holders are not be liable for any claim, damages or other liabillty, whether in an action of contract, tort or otherwise, arising from, out of or in connection with or the use or other dealings in the Page.



<!-- - [Chapter 1: Data Analytics and Big Data](#chapter-1-data-analytics-and-big-data)
  - [1.1 Four data analytic capabilities](#11-four-data-analytic-capabilities)
    - [1.1.1 Descriptive Analytics](#111-descriptive-analytics)
    - [1.1.2 Diagnostic Analytics](#112-diagnostic-analytics)
    - [1.1.3 Predictive Analytics](#113-predictive-analytics)
    - [1.1.4 Prescriptive Analytics](#114-prescriptive-analytics)
  - [1.2 Big Data](#12-big-data)
  - [1.3 Structured vs. Unstructured data](#13-structured-vs-unstructured-data)
  - [1.4 The big data processing cycle](#14-the-big-data-processing-cycle)
    - [1.4.1 Collect](#141-collect)
    - [1.4.2 Store](#142-store)
    - [1.4.3 Process and analyze](#143-process-and-analyze)
    - [1.4.4 Consume and visualize](#144-consume-and-visualize)
  - [1.5 Databases](#15-databases)
  - [1.6 Data Warehouse](#16-data-warehouse)
  - [1.7 Extract, transform, load (ETL)](#17-extract-transform-load-etl)
  - [1.8 Solving the big data challenges](#18-solving-the-big-data-challenges)
  - [1.9 Processing of Big Data](#19-processing-of-big-data)
  - [2.0 Distributed File Systems](#20-distributed-file-systems)
  - [2.1 Hadoop](#21-hadoop)
    - [Splitting large dataset](#splitting-large-dataset)
    - [Traditional approach](#traditional-approach)
    - [Map Function](#map-function)
    - [Reduce function](#reduce-function)
    - [Visualization](#visualization)
    - [Dashboards](#dashboards)
- [Chapter 2: Overview of AI and Machine Learning](#chapter-2-overview-of-ai-and-machine-learning)
    - [Autonomous Driving Car](#autonomous-driving-car)
    - [Vehicle/Object Detection](#vehicleobject-detection)
    - [Disease Detection](#disease-detection)
  - [1. Subfields of Artificial Intelligence](#1-subfields-of-artificial-intelligence)
    - [1.1 Image Classification](#11-image-classification)
    - [1.2 Object Detection](#12-object-detection)
      - [Automated Face analysis tasks](#automated-face-analysis-tasks)
    - [1.3 Natural language processing (NLP)](#13-natural-language-processing-nlp)
      - [Language Translation](#language-translation)
      - [Sentiment analysis](#sentiment-analysis)
      - [Named Entity Recognition (NER)](#named-entity-recognition-ner)
    - [1.4 Chatbots](#14-chatbots)
      - [Text to speech](#text-to-speech)
      - [Speech to text](#speech-to-text)
  - [AI, Machine Learning and Deep Learning](#ai-machine-learning-and-deep-learning)
  - [2. Problem: Rule-based approach](#2-problem-rule-based-approach)
    - [Learning by examples](#learning-by-examples)
  - [3. Machine Learning](#3-machine-learning)
    - [Spam Classifier](#spam-classifier)
    - [ImageNet](#imagenet)
  - [4. ML models and algorithms](#4-ml-models-and-algorithms)
  - [5. K-nearest neighbor](#5-k-nearest-neighbor)
    - [3-nearest neighbor](#3-nearest-neighbor)
    - [Euclidian Distance](#euclidian-distance)
    - [Boundary method](#boundary-method)
    - [Hand-writing digit recognition](#hand-writing-digit-recognition)
      - [Ground Truth](#ground-truth)
      - [Training and Loss](#training-and-loss)
      - [Epoch](#epoch)
      - [Batch size](#batch-size)
      - [Hyper-parameters](#hyper-parameters)
      - [Overfitting](#overfitting)
  - [6. Types of Machine Learning](#6-types-of-machine-learning)
    - [Supervised Learning](#supervised-learning)
    - [Classification (Binary/Multiclass)](#classification-binarymulticlass)
      - [Evaluation of Model](#evaluation-of-model)
        - [Positive vs. Negative Class](#positive-vs-negative-class)
        - [Confusion Matrix](#confusion-matrix)
        - [Validation Set](#validation-set)
    - [Regression](#regression)
      - [Examples](#examples)
    - [Unsupervised Learning](#unsupervised-learning)
      - [Examples](#examples-1)
    - [Reinforcement Learning](#reinforcement-learning)
      - [Examples](#examples-2)
- [Chapter 3: Regression](#chapter-3-regression)
  - [Simple Linear Regression](#simple-linear-regression)
  - [Finding the Model](#finding-the-model)
  - [Residuals](#residuals)
  - [Loss function](#loss-function)
  - [Tangent Line](#tangent-line)
  - [Optimization: Gradient Descent](#optimization-gradient-descent)
  - [Learning Rate:](#learning-rate)
  - [Multiple Regression](#multiple-regression)
  - [Polynomial Regression](#polynomial-regression)
- [Chapter 4: Classification](#chapter-4-classification)
  - [Logistic Regression](#logistic-regression)
  - [Decision Boundary](#decision-boundary)
  - [Probability](#probability)
- [Chapter 5: Deep Learning](#chapter-5-deep-learning)
  - [Perceptron](#perceptron)
  - [Activation functions](#activation-functions)
  - [SoftMax](#softmax)
  - [Neural network for regression](#neural-network-for-regression)
  - [Backpropagation: How the ANN "learns"?](#backpropagation-how-the-ann-learns)
  - [Deep Learning](#deep-learning)
  - [CNN](#cnn)
    - [LeNet](#lenet)
    - [ResNet](#resnet)
    - [Example](#example)
  - [(Deep) Reinforcement Learning](#deep-reinforcement-learning)
- [Chapter 6: Chatbots and Conversational Agents](#chapter-6-chatbots-and-conversational-agents)
  - [Introduction to Chatbots and/or Conversational Agents](#introduction-to-chatbots-andor-conversational-agents)
  - [Properties of Human Conversation](#properties-of-human-conversation)
    - [Grounding](#grounding)
  - [Rule-based Chatbots: ELIZA and PARRY](#rule-based-chatbots-eliza-and-parry)
- [Chapter 7: NLP and Sentimental Analysis](#chapter-7-nlp-and-sentimental-analysis)
  - [1. Word Meanings](#1-word-meanings)
  - [2. Vector Semantics](#2-vector-semantics)
  - [3. Word and Vectors](#3-word-and-vectors)
    - [3.1 Cosine Similarity](#31-cosine-similarity)
    - [3.2 TF-IDF](#32-tf-idf)
  - [4. NLP Applications for Sentiment Analysis](#4-nlp-applications-for-sentiment-analysis)
    - [4.1 Naive Bayes](#41-naive-bayes)
- [Chapter 8: Recommender Systems](#chapter-8-recommender-systems)
  - [1. Fundamentals](#1-fundamentals)
    - [Non-personalized recommendation](#non-personalized-recommendation)
    - [Personalized recommendation](#personalized-recommendation)
  - [2. Example](#2-example)
    - [Base Case Algorithm: Averages](#base-case-algorithm-averages)
    - [Social information filtering](#social-information-filtering)
    - [Algorithm 1: Mean Squared Differences (MSD)](#algorithm-1-mean-squared-differences-msd)
    - [Algorithm 2: Pearson r](#algorithm-2-pearson-r)
    - [Algorithm 3: Constrained Pearson r](#algorithm-3-constrained-pearson-r)
  - [3. Methods](#3-methods)
    - [3.1 Content-based Filtering](#31-content-based-filtering)
    - [3.2 Collaborative Filtering](#32-collaborative-filtering)
      - [User-based:](#user-based)
      - [Item-based:](#item-based)
    - [Comparsion](#comparsion)
  - [4. Applications](#4-applications)
- [Chapter 9:  Social Network Analysis](#chapter-9--social-network-analysis)
  - [Stories behind various Social Networks](#stories-behind-various-social-networks)
  - [Networks representation with a Graph](#networks-representation-with-a-graph)
    - [Adjacency Matrix](#adjacency-matrix)
  - [Degree Matrix](#degree-matrix)
    - [Exercise](#exercise)
  - [Case Study: Analysis of a real social network](#case-study-analysis-of-a-real-social-network)
  - [Social Network Analysis Examples](#social-network-analysis-examples)
  - [Community Detection](#community-detection)
  - [‘Small-world’ phenomenon](#small-world-phenomenon)
  - [‘Power-law’ degree distributionial Network Analysis](#power-law-degree-distributionial-network-analysis)
- [Chapter 10: Societal Implications of AIDA](#chapter-10-societal-implications-of-aida)
  - [The positive values of AIDA practice](#the-positive-values-of-aida-practice)
  - [The concerns about AIDA’s societal implications](#the-concerns-about-aidas-societal-implications)
    - [Privacy and Data Ownership](#privacy-and-data-ownership)
      - [Three dimensions of Data Privacy](#three-dimensions-of-data-privacy)
      - [Privacy concerns in data use](#privacy-concerns-in-data-use)
      - [Solution](#solution)
    - [Transparency and Explainable AI](#transparency-and-explainable-ai)
    - [Trustworthiness and Accountability](#trustworthiness-and-accountability)
    - [Bias, Equity, and Fairness](#bias-equity-and-fairness)
- [Chapter 11:  Computer Vision and Speech Processing](#chapter-11--computer-vision-and-speech-processing)
  - [1. Computer Vision](#1-computer-vision)
    - [1.1 Fundamentals](#11-fundamentals)
    - [1.2 Representation and learning model](#12-representation-and-learning-model)
      - [Important learning model in CV: CNN](#important-learning-model-in-cv-cnn)
    - [1.3 Essential Tasks](#13-essential-tasks)
      - [Associating one label to a given image: single-label classification](#associating-one-label-to-a-given-image-single-label-classification)
      - [Associating multiple labels to a given image: multi-label classification](#associating-multiple-labels-to-a-given-image-multi-label-classification)
    - [1.4 Object Detection](#14-object-detection)
    - [1.5 Image segmentation](#15-image-segmentation)
      - [Semantic segmentation](#semantic-segmentation)
      - [Instance segmentation](#instance-segmentation)
      - [Panoptic segmentation](#panoptic-segmentation)
  - [2. Speech Processing](#2-speech-processing)
    - [Fundamentals](#fundamentals)
      - [What do computer do?](#what-do-computer-do)
      - [Difficulties](#difficulties)
    - [Feature selection](#feature-selection)
    - [Learning model](#learning-model)
      - [Hidden Markov Chains (HMM) modeling syllable orders](#hidden-markov-chains-hmm-modeling-syllable-orders)
    - [Summary](#summary) -->


# Lecture 1: DATA ANALYTICS AND BIG DATA
Global Datasphere is a measure of all new data that is captured, created, and replicated in any given year across the globe.

- One Terabyte (TB) = 1,000 Gigabytes (GB)
A single TB could hold 1,000 copies of the Encyclopedia Brittanica
- All the X rays in a large hospital

|Name|Symbol|Value|
|:--:|:--:|:--:|
|Kilobyte|KB|1,000 bytes|
|Megabyte|MB|1,000,000 bytes|
|Gigabyte|GB|1,000,000,000 bytes|
|Terabyte|TB|1,000,000,000,000 bytes|
|Petabyte|PB|1,000,000,000,000,000 bytes|
|Exabyte|EB|1,000,000,000,000,000,000 bytes|
|Zettabyte|ZB|1,000,000,000,000,000,000,000 bytes|
|Yottabyte|YB|1,000,000,000,000,000,000,000,000 bytes|

## 1.1 Four data analytic capabilities
Data: Any piece of information stored and/or processed by a computer or mobile
device.

Data Analytics refers to the technologies and processes that turn raw data into
insight for making decisions and facilitates drawing conclusion from data

<center><img src = 'L1fouranalysis.png'></center>
Source: Gartner's 2017 Planning Guide for Data and Analytics.



### 1.1.1 Descriptive Analytics

What has happened?
It is estimated that 80% of generated analytics results are descriptive in nature.
Descriptive analytics are often carried out via ad hoc reporting or dashboards

Examples
- What was the sales volume over the past 12 months?
- What is the number of support calls received as categorized by severity and geographic location?

<center><img src = 'L1descriptive.png'></center>

### 1.1.2 Diagnostic Analytics
Diagnostic analytics aim to determine the cause of a phenomenon that occurred in the past using questions that focus on the reason behind the event.

Sample questions
- Why were Q2 sales less than Q1 sales?
- Why have there been more support calls originating from the Eastern region than from the Western region?

### 1.1.3 Predictive Analytics
Generate future predictions based upon past events.

Sample questions
- What are the chances that a customer will default on a loan if they have
missed a monthly payment?
- What will be the patient survival rate if Drug B is administered instead of
Drug A?

### 1.1.4 Prescriptive Analytics
What should I do if “x” happens?

Prescriptive analytics provide specific (prescriptive) recommendations to the user.
Various outcomes are calculated, and the best course of action for each outcome is suggested.

**[Examples]**
- When is the best time to trade a particular stock?

## 1.2 Big Data
4V of Big Data
- Volume
A huge amount of data
- Velocity
High speed and continuous flow of data
- Variety
Different types of structured, semi structured and unstructured data coming from heterogenous sources
- Veracity
Data may be inconsistent, incomplete and messy



## 1.3 Structured vs. Unstructured data
Structured data
Data conforms to a data model or schema and is often stored in tabular form.

Unstructured data
Data that does not conform to a data model or data schema is known as unstructured data.
Estimated to makes up 80% of the data within any given enterprise.

Semi structured data
Non tabular structure, but conform to some level of structure.

<center><img src = 'L1data.png'></center>


## 1.4 The big data processing cycle
### 1.4.1 Collect
Collecting the raw data such as transactions, logs, and mobile devices.
Permits developers to ingest a wide variety of data.
### 1.4.2 Store
Requires a secure, scalable, and durable repository to store data before or after the processing tasks.
### 1.4.3 Process and analyze
Data is transformed from its raw state into a consumable format.
Usually by means of sorting, aggregating, joining, and performing more advanced functions and algorithms.
The resulting datasets are then stored for further processing or made available for consumption with business intelligence and data visualization tools.
### 1.4.4 Consume and visualize
Data is made available to stakeholders through self service business intelligence and data visualization tools to allow fast and easy exploration of datasets.
Users might also consume the resulting data in the form of statistical predictions (in the case of predictive analytics) or recommended actions (in the case of prescriptive analytics)

<center><img src = 'L1processing.png'></center>

## 1.5 Databases
Designed to store and handle transaction data (live, real time data)

Relational databases (e.g. Mysql store data in tables with fixed rows and columns)

Non relational databases (NoSQL) store data in a variety of data models (e.g. JSON)

More flexible schema (how the data is organized)

<center><img src = 'L1database.png'></center>

## 1.6 Data Warehouse

Data warehouse is a giant database storing highly structured information that is optimized for analytics

Typically store current and historical data from one or more systems and disparate data sources
May not reflect the most up to date state of the data.
Business analysts and data scientists can connect data warehouses to explore the data, look for insights, and generate reports for business stakeholders.

**[Examples]**
Google BigQuery, Amazon

## 1.7 Extract, transform, load (ETL)

The ETL processes move data from its original source (e.g. database or other sources) to the data warehouse on a regular schedule (e.g., hourly or daily)

Extract: Extract data from homogeneous/heterogeneous
Transform: Clean the data and transform the data into appropriate format
Load: Insert data into the target data warehouse

## 1.8 Solving the big data challenges
- Scaling up (Vertical scaling)
Have a supercomputer with enormous amounts of storage attached to an extremely fast network.
- `Scaling out (Horizontal scaling)[A BETTER WAY]`
Have a lot of smaller computers, each with a modest amount of storage, connected by networking.

<center><img src = 'L1scalingout.png'></center>

## 1.9 Processing of Big Data
The challenges of Big Data cannot be handled easily by traditional storage technology, e.g. databases

1. Hadoop
A framework that allows for storing a large amount of data and the distributed processing of
large data sets across clusters of computers

2. MapReduce
a programming paradigm that enables massive scalability across hundreds or thousands of
servers in a Hadoop cluster.

3. Apache Spark
An open source unified analytics engine for large scale data processing

<center><img src = 'L1hadoop.png'></center>

## 2.0 Distributed File Systems
A cluster is a tightly coupled collection of servers, or nodes.
A distributed file system can allow us to store large files which spread across the nodes of a cluster

E.g. Hadoop Distributed File System (HDFS).

## 2.1 Hadoop
### Splitting large dataset
Split large dataset into smaller data blocks and stored in different nodes.

In Hadoop, each block contains 128 MB of data and replicated three times by default.

Replication Factor: The number of times Hadoop framework replicate each and every data block.

<center><img src = 'L1splitting.png'></center>

### Traditional approach
Moving huge amount data to the processing unit is costly.
The processing unit becomes the bottleneck.

<center><img src = 'L1trad.png'></center>

### Map Function
Instead of moving data to the processing unit, we are moving the processing unit to the data

MapReduce consists of two distinct tasks Map and Reduce.
Map: process data to create key value pairs in parallel

<center><img src = 'L1map.png'></center>


### Reduce function
MapReduce consists of two distinct tasks Map and Reduce.

Map: process data by workers based on where data is stored
Reduce: Aggregate results by the “reduce workers”

<center><img src = 'L1reduce.png'></center>


### Visualization
Creation and study of the visual representation of data
One of the most important tools for data analytics/science.

<center><img src = 'L1visual.png'></center>

### Dashboards
Dashboard is a read only snapshot of an analysis that you can share with other users for reporting purposes.

# Lecture 2: OVERVIEW OF AI AND MACHINE LEARNING

### Autonomous Driving Car
Self driving vehicles or “driverless” cars

Combine sensors and software to control,
navigate, and drive the vehicle.

Drivers are NOT required to take control to safely operate the vehicle.

### Vehicle/Object Detection
Classify and detect the objects in the image.

Assign a class to each object and draw a bounding box around it.


### Disease Detection

## 1. Subfields of Artificial Intelligence
AI is concerned with developing machines with the ability that are usually done by us humans with our natural intelligence

Computer Vision: Enabling computers to derive information from images and videos

Natural Language Processing (NLP): Giving computers the ability to understand text and spoken words

Speech Recognition
Machine Learning
Deep Learning


### 1.1 Image Classification
Image classification models take an image as input and return a prediction about which class the image belongs to.

Images are expected to have only one class for each image.


### 1.2 Object Detection
Takes an image as input and output the images with **bounding boxes** and labels on detected objects.

For example, Google Lens.


#### Automated Face analysis tasks
Face detection: Detect if there is a face in images/videos.

Face classification: Determine the kind of face
E.g. the Age, Gender and emotion of a person from the face

Face verification: One to one
Is it the same face (e.g. unlock your mobile phone)?

Face identification: One to many
E.g. Police search

### 1.3 Natural language processing (NLP)

The branch of artificial intelligence (AI) concerned with giving computers the ability to understand text and spoken words in much the same way human beings can.

#### Language Translation

#### Sentiment analysis
Extract subjective qualities (e.g. attitude, emotion) from text.

Predict whether a movie review is positive or negative, based on the words in the movie
review.

#### Named Entity Recognition (NER)
Identify specific entities in a text, such as dates, individuals and places

<center><img src = 'L2NER.png'></center>


### 1.4 Chatbots
Software application built to simulate a human like conversation.

Involve speech recognition, natural language processing and speech synthesis


#### Text to speech

Text to Speech (TTS) is the task of generating natural sounding speech given
text input.

May generates speech for multiple speakers and multiple languages.

#### Speech to text
Convert voice to text


## AI, Machine Learning and Deep Learning

Example: Recognizing a digit

Let’s say that we want to teach a computer to recognize the number 7

Rules for distinguishing 7 from other characters

7s have a mostly horizontal line near the top of the figure

they have a mostly northeast southwest diagonal line

Those two lines meet in the upper right.

<center><img src = 'L2digit.png'></center>

## 2. Problem: Rule-based approach

Finding a good and complete set of rules is frequently an overwhelmingly difficult task.

1. The rules human experts follow are often not explicit.
2. Easy to overlook exceptions and special cases.
3. The technology, laws, and social conventions around human activities are constantly changing.
4. Constantly monitor, update, and repair this tangled web of interconnecting rules.

### Learning by examples

<center><img src = 'L2learn.png'></center>

Provide many examples of each class of image.

The computer looks at these examples and learn about the visual appearance and features of each type of image.

Learning the rules instead of coding the rule.


## 3. Machine Learning
In ML, features are any property or characteristic of the data that the model can use to make predictions

### Spam Classifier
Spam: junk or unwanted email, such as chain letters, promotions, etc.
Ham: non spam emails.

### ImageNet

A large visual database designed for use in visual object recognition software research.

More than 14 million images have been hand annotated by the project to indicate what objects are pictured, covering 100,000 classes.

ImageNet contains more than 20,000 categories.

E.g. "balloon" or "strawberry", each consisting of several hundred images.

## 4. ML models and algorithms

ML Model
A representation of reality using a set of rules that mimic the existing data as closely as possible

Training
Giving examples to a model so it can learn.
Split the dataset into two parts

Training set: Used to train the model
Test set: Used to test the accuracy of the model on data the model has never seen before during training

Algorithm
A procedure, or a set of steps, used to solve a problem or perform a computation
The goal of machine learning algorithms is to build a model for prediction

## 5. K-nearest neighbor 

<center><img src = 'L2KN.png'></center>

The nearest point to this new observation is malignant and located at the coordinates (2.1, 3.6).
If  a point is close to another in the scatter plot, then the perimeter and concavity values
are similar.
We may expect that they would have the same diagnosis.

Classifying unlabelled examples by assigning them the class of  similar labeled examples
“k”is a parameter that specifies the number of  neighbors to consider when making
the classification. 

Applications
Recommendation systems that predict whether a person will enjoy a movie or song 
Identifying patterns in genetic data to detect specific proteins or diseases 
Computer vision applications, including optical character recognition and facial recognition in
both still images and video.

### 3-nearest neighbor
To improve the prediction we can consider several neighboring points 
Among those 3 closest points, we use the majority class as our prediction for the new observation


### Euclidian Distance

Euclidean distance is the distance between two points in Euclidean space.
$$
d(a,b) = \sqrt{(a_1-b_1)^2 + (a_2-b_2)^2 + ... + (a_n-b_n)^2}\\
$$
$a = (a_1, a_2, ..., a_n)\\
b = (b_1, b_2, ..., b_n)$
where $p$ and $q$ are two points in Euclidean space.

<center><img src = 'L2distance.png'></center>

$$
Distance = \sqrt{(3-1)^2 + (4-2)^2 + (5-3)^2} = \sqrt{12} = 3.46
$$



### Boundary method


Accuracy = # of correct predictions / # of total predictions

<center><img src = 'L2boundary.png'></center>

Find a line or curve (decision boundary) that best separates the two classes/labels of the data points
• all the samples with one label are on one side of  the line/curve 
• all those with the other label are on the other side.



### Hand-writing digit recognition
MNIST handwritten digit database



#### Ground Truth
Ground truth is information that is known to be real or true.

#### Training and Loss

<center><img src = 'L2training.png'></center>

#### Epoch
The number of epochs is a hyperparameter that defines the number of times that the learning algorithm will work through the entire training dataset.

In each epoch, each sample in the training dataset has had an opportunity to update the internal model parameters.
• In the first epoch, AI may make large prediction errors
• Feed the training data to AI multiple times to learn from the mistakes and reduce the prediction errors

#### Batch size
Due to computational and memory limits, we generally don’t feed the entire training set to the AI model
• Break down the training data into smaller batches which are fed to the model individually
• The batch size is a hyperparameter that defines the number of samples to work through before

<center><img src = 'L2batch.png'></center>

#### Hyper-parameters
Any quantity that the model creates or modifies during the **training process** is a parameter
• We can twist many other knobs before training a model
• E.g. the number of epochs, batch size, the “k” value in k nearest neighbor, learning rate (more about it later), etc
• Any quantity that you set before the training process is a hyperparameter

#### Overfitting
The word overfitting refers to a model that models the training data well but it fails to generalize.


<center><img src = 'L2overfitting.png'></center>


## 6. Types of Machine Learning

### Supervised Learning
### Classification (Binary/Multiclass)
Use attributes $(𝑥1,𝑥2,….)$ to predict a categorical variable $(𝑦)$ yes/no, rain/no rain


<center><img src = 'L2boundary.png'></center>

#### Evaluation of Model

To know how well our classifier will perform on real-world data (with new and unseen data) before we deploy it.


##### Positive vs. Negative Class
|Item|Meaning|
|---|---|
|True Positive (TP)|Correctly Classified as the class of interest|
|True Negative (TN)|Correctly Classified as not the class of interest|
|False Positive (FP)|Incorrectly Classified as the class of interest|
|False Negative (FN)|Incorrectly Classified as not the class of interest|



##### Confusion Matrix

A confusion matrix is a table that categorizes predictions according to whether they match the actual value.


<center><img src = 'L2confusion.png'></center>



##### Validation Set
To validate which model to use: Cross Validation

 In the case of  small data sets (say, less than 1,000 observations), a very popular scheme is cross-validation 
• The data is split into K folds (e.g., 5).  A model is trained on K − 1 training folds and tested on the remaining validation fold. 
• This is repeated for all possible validation folds resulting in K performance estimates that can then be averaged

To make this estimate, we split the input data into three sets (e.g. 60/20/20)
• Training set: for training all our models 
• Validation set: for making decisions on which model to use
• Testing set: The selected model is finally evaluated on the test set to check how well our model did

<center><img src = 'L2regression.png'></center>

### Regression 

$$y = f(x_1, x_2, x_3, ...) $$

Use attributes $(𝑥1,𝑥2,….)$ to predict a numerical variable $(𝑦)$.  

The output of a regression model is a number, e.g. prices, sizes, or weights.

<center><img src = 'L2regression1.png'></center>

**[Examples]**



### Unsupervised Learning
Unsupervised learning is also a common type of  machine learning. 
Extract information from a dataset that has no labels, or targets to predict.


• Clustering algorithms
• Group data into clusters based on similarity
• Example algorithm: K-means
 
• Dimensionality reduction algorithms
• Simplify our data and faithfully describe it with fewer features
• Example algorithm: Principal component analysis (PCA) 

• Association rule mining 
• Generative algorithms
• generate new data points that resemble the existing data

#### Examples
![请添加图片描述](https://img-blog.csdnimg.cn/69ed1be917cb4f6b926ab019d4956ebf.png)

### Reinforcement Learning

Unlike supervised learning, no labelled data is given 
• Reinforcement learning (RL) aim to build a history of experiences for the AI and learn through trial and error.
• An agent attempts various allowed actions in an environment over multiple cycles, observes the outcome of  those actions based on the environment state 
• The agent is learnt to perform the desired task by taking actions with good outcomes and avoiding actions with bad outcomes.


#### Examples
![请添加图片描述](https://img-blog.csdnimg.cn/4ff55a0064434b20aff77cdb923d1689.png)

# Lecture 3: REGRESSION

<span id='simplelinearregression'></span>

## Simple Linear Regression
## Finding the Model 
Simple linear regression only considers one independent variable (X) and dependent variable (Y).

>$$ Y = b + mX $$


![在这里插入图片描述](https://img-blog.csdnimg.cn/f4a8f6c80d7a4bb4a0f644ab08f498df.png)

 A good linear regression model is one where the line is close to the points. 

![请添加图片描述](https://img-blog.csdnimg.cn/c33c4109da4c4680937846970ad0d3fd.png)

## Residuals
> $$ 𝑒_𝑖 = 𝑦_𝑖 −(𝒎𝑥𝑖+𝒃) $$



Absolute Error: A metric that tells us how good our model is by adding distances between predicted and actual values of the dependent variable


![请添加图片描述](https://img-blog.csdnimg.cn/a879a6d0f2154fbd9ccdc48c0c16eef2.png)


Square Error: The square error is a metric that tells us how good our model is by adding squares of residuals 

![请添加图片描述](https://img-blog.csdnimg.cn/a2ee2e3f2c3c4440b968a419467259f4.png)

## Loss function
![请添加图片描述](https://img-blog.csdnimg.cn/fd5e856819a1463b8255bf7e62616ccc.png)

## Tangent Line
![请添加图片描述](https://img-blog.csdnimg.cn/9ca81cfbbf4646f68e4756ac72800e0d.png)


![请添加图片描述](https://img-blog.csdnimg.cn/c4b271eba6a948de94df9526694f8958.png)

## Optimization: Gradient Descent
![请添加图片描述](https://img-blog.csdnimg.cn/4640729612b446fda6724a42ee4c59aa.png)

A positive slope tells us that we should take a step to the left to get to the lowest SSE 
A negative slope tells us that we should take a step to the right to get to the lowest
SSE

![请添加图片描述](https://img-blog.csdnimg.cn/251dc48f2a534d36bc1e82fbe70e6941.png)

## Learning Rate:

To find the local minima 

![请添加图片描述](https://img-blog.csdnimg.cn/4ccf8d09e0434ebe8643934644f0cc43.png)

## Multiple Regression

## Polynomial Regression 
![请添加图片描述](https://img-blog.csdnimg.cn/d2d346cdd0b547d6a0c79539f9ba5a14.png)


# Lecture 4: CLASSIFICATION

## Logistic Regression

Logistic Function: 
> $$ f(x) = 1 / (1+e^{-x})$$

## Decision Boundary
![请添加图片描述](https://img-blog.csdnimg.cn/62363f9a11954b94b163c2bd5d3ff70c.png)


## Probability 

$z from {\infin}to-{\infin}$

![请添加图片描述](https://img-blog.csdnimg.cn/be294e345a754ed4897122c69b394bb3.png)



---

# Lecture 5: DEEP LEARNING
Artificial Neural Network (ANN)
Inspired by the structure of  the human brain, with a network of  many cells called “neurons”.

## Perceptron 
A single-layer perception is the basic unit of a neural network
A binary classifier which can decide whether or not an input below class
Activation: the output of  the neuron
Activation function: calculates the artificial neuron’s output 

Sometimes we won’t be able to fit a linear classifier to this data, we use two lines by combining linear classifiers this way, is the basis for neural networks.

![请添加图片描述](https://img-blog.csdnimg.cn/c5521c2e22614569938c3b6056b0c7fd.png)


The arrangement of nodes and layers: the architecture of  the neural network
> Input Layers -> Hidden Layers -> Output Layers

The depth of the neural network: the number of layers (excluding the input layer)
> The input layer is not counted as layer
A neural network with depth of 3
• An input layer of size 4
• A hidden layer of size 3 (first hidden layer is formed by linear classifiers )
• A hidden layer of size 2 (classifiers in each successive layer are slightly more complex than those in the previous ones)
• An output layer of size 3



![请添加图片描述](https://img-blog.csdnimg.cn/24558c8e6de54dc1ad1ad5d403d20a43.png)


• To build a neural network, we use the outputs of two perceptrons and a bias node (represented by a classifier that always outputs a value of 1) to a third perceptron. 
• The boundary of the resulting classifier is a combination of the boundaries of the input classifiers.![请添加图片描述](https://img-blog.csdnimg.cn/0cdadb7bb86d4a12b8c1bbd7ce18a141.png)

## Activation functions
• An activation function takes a real number as input and returns a new floating-point number as output 
• We can apply a different activation function to every neuron in our network 
• In practice, we usually assign the same activation function to all the neurons in each layer.

![请添加图片描述](https://img-blog.csdnimg.cn/a44897bb31854247a1f0a4a07a87197d.png)
Sigmoid return 0,1
Tanh return 1,-1
ReLU 0 to positive and negative infinite 

Regression - Linear Activation Function `(for the amount, it is numeric, regression need no activation function)`
Binary Classification—Sigmoid/Logistic Activation Function
Multiclass Classification—Softmax
Multilabel Classification—Sigmoid

The activation function used in hidden layers is typically chosen based on the type of neural network architecture.
Convolutional Neural Network (CNN): ReLU activation function.
Recurrent Neural Network: Tanh and/or Sigmoid activation function.



## SoftMax
•turn the raw numbers that come out of  a classification network into class probabilities

## Neural network for regression
`No activiation function is needed`
Remove the final sigmoid function from the neural network
• The role of  this function is to turn the input into a number between 0 and 1
• If  we remove it, the neural network will be able to return any number.

Local minima



## Backpropagation: How the ANN "learns"?

Remove the final sigmoid function from the neural network
• The role of  this function is to turn the input into a number between 0 and 1
• If  we remove it, the neural network will be able to return any number.

In each epoch, update the weights and bias using gradient descent
• `Forward Propagation`: Take the data point one by one and perform a forward pass to calculate the prediction
• `Backward Propagation`: Based on the answer and the prediction error, compute how much we should adjust each weights and biases best in order decrease the errors



## Deep Learning
Shallow learning algorithms are ML algorithms that do not gain in accuracy beyond a certain amount of  training data. 
Results get better with more data  + bigger models + more computation


![请添加图片描述](https://img-blog.csdnimg.cn/aab162bff90546e2aa9848ffbb2df542.png)


## CNN
• CNN  is a neural network which utilizes a special type of  layer (convolutional layers) to learn from image and image-like data. 
• A convolution is a filter that passes over an image, processes it, and extracts the important features (and blur the inessential features). • Excels at handling image/image-like data and computer vision tasks

### LeNet

LeNet-5 was one of  the earliest convolutional neural networks and promoted the development of  deep learning![请添加图片描述](https://img-blog.csdnimg.cn/9da8ad773d174c188004cc38659c7c2a.png)

### ResNet
ResNet is one of  the most powerful CNN winning the ImageNet challenge in 2015 


### Example
1.  Create images that look like photographs of  human faces, even though the faces don't belong to any real person.
2. Deep Fake 

The use of  artificial intelligence (AI) to create a fake event
• in photo, video, or audio format

![请添加图片描述](https://img-blog.csdnimg.cn/13ec1cd5e667414ea4d7ed300fec22d7.png)

3. Cartoon GAN
![请添加图片描述](https://img-blog.csdnimg.cn/f423e08003c14909919543e3f3af69fb.png)

4. Pix2pix

Training on pairs of  images and then attempts to generate the corresponding output image from any input image you give it

![请添加图片描述](https://img-blog.csdnimg.cn/e6406a8bf24243148c397d90050e8d11.png)

5. ClothingGAN
6. GPT-3
The prompt is text that you input to the model, and the model will respond with a text completion that attempts to match whatever context or pattern you give it.
7. Dalle-2 
DALL·E 2 is a new AI system that can create realistic images and art from a
description in natural language. 

[OpenAI](https://openai.com/dall-e-2)


## (Deep) Reinforcement Learning
Build a history of  experiences for the AI and learn through trial and error. 
1. Agent: The component that makes the decision of  what action to take 
2. State: A representation of  the current environment that the agent is in or the information related to the task at hand
E.g. the velocities of  the robot arm, location of  the objects to be picked up, observations that the agent can perceive
3. Action space: A set of  actions the agent can choose from.
• The agent influences the environment through these actions
• The environment may change states as a response to the agent’s action and may also provide a reward signal as a response. 
4. Reward: Feedback from the environment (Positive or negative)
• The agent learns from trial and error, initially taking random actions and over time identifying the actions that lead to long-term rewards.



Each black circle is some game state and each arrow is a transition 
• Take the two games we won and slightly encourage every single action we made in that episode. 
• Take the two games we lost and slightly discourage every single action we made in that episode.
![请添加图片描述](https://img-blog.csdnimg.cn/4148b372c2ad451085f2f6703ebc2fba.png)





---

# Lecture 6: CHATBOTS AND CONVERSATIONAL AGENTS
## Introduction to Chatbots and/or Conversational Agents 

- Chatbots: open-domain (or Non-task-oriented) dialogue system
• Mimic informal human chatting 
• For fun, or even for therapy (why?)
e.g. Xiaoice from MSRA
- Task-based (or Task-oriented) Dialogue Agents
• Interfaces with personal assistants 
• For task completion
• E.g., Used in cars, robots, appliances
• E.g., Used for booking flights or restaurants
e.g. Siri from Apple


## Properties of Human Conversation
**Barge-in (problems with ending)**
• Allowing the user to interrupt 
**End-pointing (problems with starting)**
• The task for a speech system of deciding whether the user has stopped talking.
• Very hard, since people often pause in the middle of turns

![请添加图片描述](https://img-blog.csdnimg.cn/078f5c0f1c09437e9fbe2c334ef95d38.png)
**[Example]**
Directive: "Turn up the music", 'What day in May do you want to travel?'
Constative: 'I need to travel in May'
Acknowledgement: 'Thanks'

### Grounding 
Principle of closure. Agents performing an action require evidence, sufficient for current purposes, that they have succeeded in performing it (Clark 1996, after Norman 1988) 
- Grounding: acknowledging that the hearer has understood
Grounding is relevant for human-machine interaction
• Why do elevator buttons light up? To confirm they get the point
- Adjacency pairs: 
• QUESTION… ANSWER
• PROPOSAL… ACCEPTANCE/REJECTION
• COMPLIMENTS ("Nice jacket!")… DOWNPLAYER ("Oh, this old thing?"
- Sub-dialogues: interactions where a system question is responded to with a question or request from the user, who thus initiates a subdialogue.
![请添加图片描述](https://img-blog.csdnimg.cn/5e8fd9a30b28406a890e83e92a53fde3.png)
- Clarification: ![请添加图片描述](https://img-blog.csdnimg.cn/3da4a0ea37e344409af6dfb81f679d59.png)
- Pre-Sequenece of Sub-dialogues:
![请添加图片描述](https://img-blog.csdnimg.cn/948e7a7e181c4b40be0fd4474a372ef3.png)

Problems: Inference
![请添加图片描述](https://img-blog.csdnimg.cn/ab4f6e49f1844541a48b23ae591bf9c2.png)

Some conversations are controlled by one person • A reporter interviewing a chef asks questions, and the chef responds. • This reporter has the `conversational initiative` (Walker and Whittaker 1990)

Most human conversations have `mixed initiatives`: • I lead, then you lead, then I lead. • Mixed initiative is very hard for NLP systems, which often default to 

## Rule-based Chatbots: ELIZA and PARRY
- Eliza raised some ethical implications because people developed feelings for it.
![请添加图片描述](https://img-blog.csdnimg.cn/ac2c5f95a9e64cac90bd2aba1f70c0bb.png)
![请添加图片描述](https://img-blog.csdnimg.cn/fd2a5100f1ee457b9cda87851369e1af.png)
- Parry is designed to study psychology problems (to mimic patients) and is the first system that passed the Turing test in 1972.

Another chatbot with a clinical psychology focus patients usually interpret 

![请添加图片描述](https://img-blog.csdnimg.cn/5b83206efe114ae386b4be1b0109c245.png)





---
# Lecture 7: NLP and SENTIMENT ANALYSIS

## 1. Word Meanings 
A  sense or “concept” is the  meaning component of a word

- Relations between senses: Synonymy
- Similarity 




## 2. Vector Semantics

Suppose you see these sentences:
• Ong choi is delicious sautéed with garlic.
• Ong choi is superb over rice
• Ong choi leaves with salty sauces
And you've also seen these:
• …spinach sautéed with garlic over rice
• Chard stems and leaves are delicious
• Collard greens and other salty leafy greens 
Conclusion:
• Ong choi is a leafy green like spinach, chard, or collard greens

- A word vector is also called an " embedding" because it's embedded into a high-dimensional space 
- The standard way to represent meaning in NLP

![请添加图片描述](https://img-blog.csdnimg.cn/ba6ba4642bd74d9cb00008a522877a04.png)

A vector is an ordered list of numbers, such as 
![请添加图片描述](https://img-blog.csdnimg.cn/a15387785b63450eb26b6ebf3e7a3b89.png)

Elements or entries, e.g., the 3rd entry is 3.6
Count of entries, dimension 
Vectors of dimension n: n-vector
Numbers are called scalars 

- with words, a feature is a word identity, need the exact same word
- with embeddings, a feature is a word vector, we generalise similar but unseen words 

Embeddings example: 
- tf-idf, simple baseline model, sparse vectors, represented by the counts of nearby words 
- Word2vec, dense vectors, by creating classifier to predict if a word is likely to appear nearby, where it extensions are called contextual embeddings and it is the ancestor of BERT
![请添加图片描述](https://img-blog.csdnimg.cn/27ab1d434f2a46b096003f1ebd74532c.png)


## 3. Word and Vectors
Term-document matrix 
![请添加图片描述](https://img-blog.csdnimg.cn/14ce484ef826467fb2b12aea4ade775a.png)

![请添加图片描述](https://img-blog.csdnimg.cn/e20ac7f826a4404b83f412c1480678c8.png)

Vectors are the basis of information retrieval (comparing the similarity between documents such as google)

### 3.1 Cosine Similarity
The dot product between two vectors is a scalar: 
![请添加图片描述](https://img-blog.csdnimg.cn/387e5447b77949bfb0d8c387ee4c8e7f.png)


![请添加图片描述](https://img-blog.csdnimg.cn/ed1e926ad41343eab7e76d1dd40a18d3.png)



![请添加图片描述](https://img-blog.csdnimg.cn/d5df3cc1d4c24f259c9ddff9c09af574.png)

![请添加图片描述](https://img-blog.csdnimg.cn/e23bde8c6de248e5824b85f4564c5402.png)

### 3.2 TF-IDF 

![请添加图片描述](https://img-blog.csdnimg.cn/0de3f708ec2249b1abd07a0fcb9e567c.png)


![请添加图片描述](https://img-blog.csdnimg.cn/6bb1e8bf62e241bf831e666787613a5b.png)



## 4. NLP Applications for Sentiment Analysis

Summary: Text Classification
• Sentiment analysis 
• Spam detection 
• Authorship identification 
• Language Identification 
• Assigning subject categories, topics, or genre

Any kind of classifier
• Naïve Bayes 
• LogisXc regression 
• Neural networks 
• k-Nearest Neighbors 

### 4.1 Naive Bayes
Bag of words (the count of words in a document)

![请添加图片描述](https://img-blog.csdnimg.cn/ccbb761ba2c44bee9f915d56cf72e7bc.png)


![请添加图片描述](https://img-blog.csdnimg.cn/b6f71b63c8cf4bc5afb185eea632d379.png)

![请添加图片描述](https://img-blog.csdnimg.cn/3d53850cffe14da9b47462456cb9e07b.png)

It is based on Bayes’ rules and jointly considers likelihood (probability of observing the words in  labeled with the class) and prior (probability of observing a class)

---

# Lecture 8: RECOMMENDATION SYSTEMS 
## 1. Fundamentals 
### Non-personalized recommendation
• Television 
• Newspaper
### Personalized recommendation
• Motivation 1: diverse needs
• Motivation 2: too many choices
• Television → Video website
• Newspaper → Social media

Usenet Communication System

![请添加图片描述](https://img-blog.csdnimg.cn/4378dfdfca28406490d3193559463f55.png)

## 2. Example 

Ringo: Social Information Filtering

- Evaluation Criteria: MAE
• Mean absolute error (MAE), minimise it.
- Evaluation Criteria: STD
• Standard deviation (STD) of the errors, minimise the errors.


### Base Case Algorithm: Averages
Baseline method for comparison 
• For each artist in the target set
• The mean score received by an artist in the source set is used as the predicted score for that artist. 
• A social information filtering algorithm is  neither personalized nor accurate unless it is a significant improvement over this base case (by simply averaging all scores) algorithm.


### Social information filtering
• Idea: recommendation based on similarity between users 
• Notation: two users profiles $U_x$ and $U_y$ are N-dimensional vectors (N-vectors): 

![请添加图片描述](https://img-blog.csdnimg.cn/567f54cba4064c0380251aff176503d6.png)

### Algorithm 1: Mean Squared Differences (MSD)
The lower the mean squared difference, the greater the similarity 



### Algorithm 2: Pearson r
This coefficient ranges from -1 indicating a negative correlation, via 0, indicating no correlation, to +1 indicating a positive correlation between two users. 

### Algorithm 3: Constrained Pearson r
We modifed the Pearson  r scheme so that only when there is an instance where both people have rated an artist positively, above 4, or both negatively, below 4, will the correlation coefficient increase.

`Use 4 as the average instead of, since there may be some constraints and considerations`

## 3. Methods


### 3.1 Content-based Filtering

`Explicit feedback`

Feature Matrix Demonstration

![请添加图片描述](https://img-blog.csdnimg.cn/584d3daf8fe648f889dcd79f104b07df.png)

Similarity: dot production in binary case; We assume this feature matrix is binary: a non-zero value (e.g. 1)means the app has that feature. 

• In this case dot product is the number of features that are active in both vectors simultaneously. As we will see, most metrics for similarity between vectors are based on the dot product.

For example, a user selects ”Education apps" in their profile. Other features can be implicit, based on the apps they have previously installed. For example, the user installed another app published by Science R Us.

 To do so, you must first pick a similarity metric (for example, dot product). Then, you must set up the system to score each candidate item according to this similarity metric. 


Pros
• The model doesn't need any data about other users, since the recommendations are specific to this user. This makes it easier to scale to a large number of users. • The model can capture the specific interests of a user,  and can recommend niche                                                                                                                                                                        items that very few other users are interested in.
Cons
• Since the feature representation of the items are hand-engineered to some extent, this technique requires a lot of domain knowledge. Therefore, the model can only be as good as the hand-engineered features.
• The model can only make recommendations `based on existing interests of the user`. In other words, the model has limited ability to expand on the users' existing interests.




### 3.2 Collaborative Filtering 
`Preference can ve explicit or implicit` 
• Collaborative filtering models can recommend an item to user A based on the interests of a similar user B. 
• Furthermore, the embeddings can be learned automatically, without relying on hand-engineering of features.

Pros
• We don't need domain knowledge because the embeddings are automatically learned.
• The model can help users discover new interests. In isolation, the machine learning system may not know the user is interested in a given item, but the model might still recommend it because similar users are interested in that item.
Cons
• Cold start problem: cannot handle fresh items


#### User-based:
• Based on the user similarity or neighborhood

In user-based collaborative filtering, we have an active user for whom the recommendation is aimed.
• The collaborative filtering engine first looks for users who are similar. That is users who share the active users rating patterns.
• Collaborative filtering basis this similarity on things like history, preference, and choices that users make when buying, watching, or enjoying something.
• For instance, if two users are similar or are neighbors in terms of their interested movies, we can recommend a movie to the active user that her neighbor has already seen.



![请添加图片描述](https://img-blog.csdnimg.cn/9aacb0fa4ac14a7c88e400019e917cb3.png)


#### Item-based:
• Based on similarity among items calculated using people's rating of those items



### Comparsion

![请添加图片描述](https://img-blog.csdnimg.cn/1574f8688f6048ae8ab81e49c23bcdc9.png)

![请添加图片描述](https://img-blog.csdnimg.cn/e960e79195db4ffd8f2320200312b29c.png)

What is the difference between content-based filtering and item-based collaborative filtering?
• In the item-based collaborative filtering, similar items build neighborhoods on the behavior of users. • However, it is not based on their contents. 
• For example, Item 1 and Item 3 are considered neighbors as they were positively rated by both User 1 and User 2. So, Item 1 can be recommended to User 3 as he has already shown interest in Item 3. But all these can be done without knowing the content of items.


## 4. Applications
Healthcare, news, product, building information, tourism, etc.


![请添加图片描述](https://img-blog.csdnimg.cn/3cfecbcf8d68441a89188e491b347fec.png)

# Lecture 9: SOCIAL NETWORKS ANALYSIS
## Stories behind various Social Networks
Behind each such system there is an intricate wiring diagram,  a network, that defines the interactions between the components
## Networks representation with a Graph 

**Distance** (shortest path, **geodesic**) between a pair of nodes is defined as the number of edges along the shortest path connecting the nodes
• If the two nodes are disconnected, the distance is usually
defined as infinite
• In directed graphs paths need to follow the direction
of the arrows
• Consequence: Distance is not symmetric, e.g., $h_{A,C} ≠ h_{C,A}$

![请添加图片描述](https://img-blog.csdnimg.cn/5ae7fff6cb6b465cae7b8cce7a995f59.png#pic_center =160x250 )
![请添加图片描述](https://img-blog.csdnimg.cn/eacdafea89f045aeb8c41e7c2d332d83.png)

### Adjacency Matrix
ROW, COLUMN
![请添加图片描述](https://img-blog.csdnimg.cn/6145e97d319b41e2b48a56a0dce7096c.png)

## Degree Matrix
![请添加图片描述](https://img-blog.csdnimg.cn/54d3a838a6dd4686acf3d73d9d59a251.jpeg)
   
### Exercise
![请添加图片描述](https://img-blog.csdnimg.cn/298b2d04d6de4fd6ac4e0c64734e4f1f.png)


A->B; A->C, so B AND C got 1

A B C D E F G H
B
C
D
E
F
G
H


$$
 \begin{bmatrix}
 0 & 1 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
   1 & 0 & 1 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
   1 & 1 & 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
   0 & 0 & 1 & 0 & 1 & 1 & 0 & 0 & 0 & 0 \\
   0 & 0 & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 0 \\
   0 & 0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 & 0 \\
   0 & 0 & 0 & 0 & 1 & 0 & 0 & 1 & 1 & 0 \\
   0 & 1 & 0 & 0 & 0 & 0 & 1 & 0 & 1 & 0 
  \end{bmatrix} 
$$

## Case Study: Analysis of a real social network 
MSN: Degree Distribution
MSN: Log-Log Degree  Distribution
Key Properties: Degree distribution: heavily skewed, avg degree =  14.4, Path length:6.6
`Most of the path lengths are small`



## Social Network Analysis Examples
## Community Detection

A community is a group of nodes with greater ties internally than to the rest of the network Strictest: **Clique**

A clique is a subset of vertices of an undirected graph such that every two distinct vertices in the clique are adjacent.

For example, ABC, EDF, HGI

**Edge betweenness**: number of shortest paths (among all pair od vertices) passing over the edge.


![请添加图片描述](https://img-blog.csdnimg.cn/55428aa812084978967df2a197c31733.png)

## ‘Small-world’ phenomenon
The small-world experiment comprised several experiments conducted by Stanley Milgram and other researchers examining the average path length for social networks of people in the United States. The research was groundbreaking in that it suggested that human society is a small-world-type network characterized by short path-lengths. The experiments are often associated with the phrase "six degrees of separation", although Milgram did not use this term himself.![请添加图片描述](https://img-blog.csdnimg.cn/e7118e8d90c34a9e862cea006757588e.png)
![请添加图片描述](https://img-blog.csdnimg.cn/3fa52b556521448c8d6958ca937b2010.png)
## ‘Power-law’ degree distributionial Network Analysis

The degree distributions of most real-life networks follow a power law, become straight line

![请添加图片描述](https://img-blog.csdnimg.cn/08ade9c1e82c457e999b4d35909e858a.png)

`Degree distribution: high skewed`
In statistics, a power law is a functional relationship between two quantities, where a relative change in one quantity results in a proportional relative change in the other quantity, independent of the initial size of those quantities: one quantity varies as a power of another. for instance, considering the area of a square in terms of the length of its side, if the length is doubled, the area is multiplied by a factor of four.

Many events of interest to scientists in natural and social life tend to have a typical scale, and the scale of individuals varies little around this characteristic scale. For example, the height of human beings, the vast majority of adult Chinese men are around the average height of 1.70m. Of course, this value varies somewhat by region, but in any case, we have never seen a "dwarf" less than 10cm tall or a "giant" taller than 10m in the street. If we take the height as the horizontal coordinate, the number or probability of obtaining this height as the vertical coordinate, we can draw a bell-shaped distribution curve, which decays very quickly on both sides of the curve; similar to this to a mean can characterize the entire group characteristics of the distribution, we call Poisson distribution.



Social Network
• media = content of twitter, tag, videos, photos ....
• The networks formed by individuals 
• Social Media
• social network + media







---

# Lecture 10: SOCIETAL IMPLICATIONS OF AIDA

## The positive values of AIDA practice
Input and output of AIDA are multidisciplinary

![请添加图片描述](https://img-blog.csdnimg.cn/9c753d65f7aa4387893c146a572729f8.png)

NLP: Read and write 
Speech Processing: Listen and speak
CV: See 

Impacts: 
1. Advance our society’s efficiency and effectiveness toward scientific governance and intelligent decision-making.
2. Optimize the processes and methods of production, and free people from part of the productive labour. 
3. Give human individuals hands-on assistance and revolutionize our everyday life for a better living.


Drone: Learn policy form user demonstrations with RL


## The concerns about AIDA’s societal implications

Ethics change with technological progress
Industrial Revolution -> Right to Internet access -> Birth control, surrogate pregnancy, embryo selection, artificial womb -> Lab-grown meat

### Privacy and Data Ownership
Data privacy is the claim of individuals, groups and institutions to determine for themselves,  when, how, and to what extent information about them is communicated to others.

#### Three dimensions of Data Privacy
• Personal privacy . Protecting a person against undue interference (such as physical searches) and information that violates his/her moral sense. 
• Territorial privacy. Protecting a physical area surrounding a person may not be violated without the person’s acquiescence.
• Safeguards : laws referring to trespassers’ search warrants. 
• Informational privacy. Deals with the gathering, compilation, and selective dissemination of information


#### Privacy concerns in data use 
• Data Collection
e.g., fingerprints, health data, etc. 
• Data Storage and Transportation
Online data may be accessible to anyone. 
• Data Analytics.
Personal data is used for analysis, e.g., recommender systems.

#### Solution
1. Privacy and data protection laws promoted by government
2. Self-regulation for fair information practices by codes of conducts promoted by businesses
3. Privacy-enhancing technologies (PETs) adopted by individuals 
4. Privacy education of consumers and IT professionals


### Transparency and Explainable AI
Blackbox: Deep learning 
![请添加图片描述](https://img-blog.csdnimg.cn/bec42fe993fc46ec886b2a2a03adc02f.png)

![请添加图片描述](https://img-blog.csdnimg.cn/4de07882a95443549768f33ec1eaf121.png)


![请添加图片描述](https://img-blog.csdnimg.cn/0084dbee9d8d4cd7837f9e000b509724.png)

### Trustworthiness and Accountability
• National Safety  (e.g., Defense construction, infrastructure, and classified systems) 
• Social Safety (e.g., unemployment) • Network Safety (e.g., illegal data access) 
• Personal Safety (e.g., accidents caused by mechanical failure)


Replacing human labor
Interesting spinL AI controlling human labour



### Bias, Equity, and Fairness

Hiring Problems: against women since the annotated data 

Word Embeddings 
Word2Vec introduced vector math on word embeddings
• Reveal harmful biases encoded in our language corpora
• Potential solution: de-bias at training time, but at least make users aware

Solutions
1. Support in fairness-aware data collection and curation
2. Overcoming teams' blind spots
3. Auditing complex ML systems
4. Deciding how to address particular instances of unfairness
5. Addressing bites in the humans embedded throughout the ML development pipeline 

---

# Lecture 11: COMPUTER VISION AND SPEECH PROCESSING 

## 1. Computer Vision

Make computers understand visual content (e.g., images and video).
Vision is an amazing feat of natural intelligence
• Visual cortex occupies about 50% of the Macaque brain
• More human brain devoted to vision than anything else

### 1.1 Fundamentals
 In 1966, Marvin Minsk
• 1966: Minsky assigns computer vision as an undergrad summer project • 1960’s: interpretation of synthetic worlds • 1970’s: some progress in interpreting selected images • 1980’s: artificial neural networks (ANNs) come and go; shift toward
geometry and increased mathematical rigor • 1990’s: face recognition; statistical analysis in vogue • 2000’s: broader recognition; large annotated datasets available; video
processing starts • 2010’s to present: deep learning



### 1.2 Representation and learning model

Images consist of pixels
• The smallest discrete component of an image on the screen 
Image resolution
• The number of pixels in a digital image 
Standard images
• Illustrate algorithms and compare the performance
• Lena:  for gray‐level images generally 256*256
- 8‐bit gray‐level image
- Each pixel has a gray value between 0 and 255

• Baboon:  for color images generally 512*512
- Red, green and blue 24 bits
- When two light beams impinge on a target, their colors add


#### Important learning model in CV: CNN
 Convolutional neural networks (CNNs)
• Promoted the development of deep learning

### 1.3 Essential Tasks
1. Image classification
- No spatial extent 
2. Semantic Segmentation
- No objects, just pixels 
3.  Object detection/ Instance segmentation 
- Multiple object


![请添加图片描述](https://img-blog.csdnimg.cn/065e2b2e71fe423098d6a8418c4c815f.png)

####  Associating one label to a given image: single-label classification 

1. Binary Classification: one out of two 
2. Multiclass Classification: one out of several things


#### Associating multiple labels to a given image: multi-label classification

1. Multilabel Classification: more than one choice out of several things 

![请添加图片描述](https://img-blog.csdnimg.cn/b41f31825e1d4b3e9c511e18b61fa991.png)


---
pre-training a neural network refers to first training a model on one task or dataset. Then using the parameters or model from this training to train another model on a different task or dataset. This gives the model a head-start instead of starting from scratch


--- 

### 1.4 Object Detection

• Object detection is the field of computer vision that deals with the localization and classification of objects contained in an image or video. 
• Object detection comes down to drawing bounding boxes around detected objects which allow us to locate them in a given scene (or how they move through it).

- creates a **bounding box** around the classified object.


• Single-stage object detectors
• e.g., YOLO (You Only Look Once): uses a single neural network trained end to end to take in a photograph as input and predicts bounding boxes and class labels directly
• Two-stage object detectors
• First extract ROIs (Region of interest), then classify and regress the ROIs
• e.g., R-CNN, Fast-RCNN, Faster-RCNN, Mask-RCNN




### 1.5 Image segmentation
Image segmentation is a sub-domain of computer vision and digital image processing which aims at grouping similar regions or segments of an image under their respective class labels.


#### Semantic segmentation
• Refers to the classification of pixels in an image into semantic classes
• Pixels belonging to a particular class are classified to that class with no other information or context considered.

#### Instance segmentation
• Models classify pixels based on “instances” rather than classes

![请添加图片描述](https://img-blog.csdnimg.cn/7f1c59b63a11477493539ffcd9e58e4d.png)

#### Panoptic segmentation
The combination of semantic segmentation and instance segmentation 




## 2. Speech Processing

### Fundamentals

• Speech Recognition: enabling a computer to understand spoken language
and convert speech signals into text (**speech-to-text transcription)** 

• Speech Synthesis: enabling a computer to generate spoken language and generate speech signals from the text **(text-to-speech transcription)**


in voice assistants, the paradigm steps come as speech recognition (speech-to-text translation) → natural language understanding → natural language generation → speech synthesis (text-to-speech translation).


Articulation produces sound waves which the ear conveys to the brain for processing.



#### What do computer do?
• Digitization 
• Acoustic analysis of the speech signal 
• Linguistic interpretation



![请添加图片描述](https://img-blog.csdnimg.cn/909844ab0e4c4722885dce1a069b2f21.png)

#### Difficulties
• Digitization
Converting analogue signals into a digital representation
• Signal processing
• Separating speech from background noise distinctions (similar phonemes)
• Phonetics
Variability in human speech 
• Phonology
Recognizing individual sound
• Lexicology and syntax
Disambiguating homophones
Features of continuous speech 
• Syntax and pragmatics
Interpreting prosodic features 
• Pragmatics
Filtering of performance errors
(disfluencies)


### Feature selection
1. Sound wave 
2. Speech signals
• Waveform
• Time
• Amplitude 
3. Spectrogram
• Time
• Frequency
• Power (e.g. marked by color)

![请添加图片描述](https://img-blog.csdnimg.cn/7640c20cc2104438b83c1b8ecded3419.png)


4. Cepstral features have been found to perform well
• Spectrogram 
→ Spectral 
→ Cepstral
• They represent the frequency of the frequencies 
• Mel-frequency cepstral coefficients (MFCC) are the most common variety


![请添加图片描述](https://img-blog.csdnimg.cn/13457e794d474a168ebc8f8aeda15d10.png)


### Learning model

![请添加图片描述](https://img-blog.csdnimg.cn/f38f3c837a8440c19c4676312ba1f2ee.png)
![请添加图片描述](https://img-blog.csdnimg.cn/6acdef7cc7d149dd85e86b020b2ea4fc.png)

![请添加图片描述](https://img-blog.csdnimg.cn/04e2292e16654e608aa43a3d8dfe7dbe.png)

#### Hidden Markov Chains (HMM) modeling syllable orders

![请添加图片描述](https://img-blog.csdnimg.cn/c2022518a64f4e4eb5ca297f6d5fa3aa.png)



### Summary

• Computer Vision (CV) is for “seeing” the world (like our eyes), and Speech Processing (SP) is for “hearing” and “speaking” (like our ears and mouth). Both CV and SP can be based on machine learning and, recently, deep learning. 
• CV takes visual signals as input (e.g., images), usually represented as pixels accordingly to the resolution and colors. 
• Several essential CV tasks, such as image classification, object detection, and semantic/instance segmentation (what are they?) 
• SP involves speech recognition (speech2text) and speech synthesis (text2speech). Its input is speech signals (sound waves)













---
