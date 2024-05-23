---
order: 2
title: Datasets
pagetitle: Datasets	
---

::: {.callout-note title="Question"}
What is a dataset and why is it important?
:::

## Datasets

There are different kinds of datasets. The housing dataset that we saw right at the beginning is a tabular dataset. Data comes in the form of a table. Each column of this table is called an attribute or a feature and each row represents one record or observation. Recall that we also use the term data-point to refer to each row of the table. By far, tabular datasets are the most common form in which data is represented. Tabular data can be neatly packed into comma-separated files or CSVs. Few other forms of data:

- image
- text
- speech

Image, text and speech data cannot be packed into simple CSVs and are often called unstructured data.

## Whence comes data?

How do we obtain data? Where does data come from? This seems like a simple question but it doesn't have a simple answer. Here are some scenarios that are arranged in increasing order of complexity:

::: {.callout-note title="Scenario-1"}
An FMCG company has given you some historical data concerning its sales over the last three years. It wants you to predict the average sales in the coming quarter.
:::

Here we are lucky. Someone comes to our doorstep and gives us the data. It might be the case that the company has neatly arranged the data in a tabular format. In addition, we also have a very precise definition of the problem statement. We have to predict a real number by looking at the data. It is a regression problem.

::: {.callout-note title="Scenario-2"}
Twitter is developing an algorithm to detect tweets that contain offensive content. As a data scientist, you are given a dump of one million tweets and asked to develop an algorithm to solve the problem.
:::

This is a more challenging problem compared to scenario-1. First, this is an instance of what is called a binary classification problem. Instead of predicting a real number, we have to predict one of two (binary) outcomes for each tweet:

- offensive
- not-offensive

In order to train a computer to distinguish between the two kinds of tweets, we need to give it examples of tweets of both kinds. Unfortunately, we don't have that information. If that information is absent, how can we teach the computer to differentiate between the two? So, the first task here is to get the dataset labeled. That is, for each tweet, mark it as "offensive" or "not-offensive". This process is time consuming and requires considerable manpower, especially if the dataset is large.

::: {.callout-note title="Scenario-3"}
You are a research scientist at a manufacturing company. You want to set up a facility that automates the segregation of defective products from non-defective ones. Come up with an end-end ML solution.
:::

This is by far the most challenging scenario. We don't have access to the data. We need to gather data in the first place. Once we have the data, we need to label it or annotate it. Only then can we start thinking about training ML models on top of the data.

## Supervision

Labeling a dataset is an important part of the data preparation process. However, there may be situations where labeling is not practically feasible. In such cases, we have to settle with unlabeled data. Therefore, datasets in ML can be classified into two categories:

- labeled dataset
- unlabeled dataset

Techniques that work with labeled data fall under the category of supervised learning. Those that work with unlabeled data come under unsupervised learning. What is so special about the term "supervised"? 

[Cambridge dictionary](https://dictionary.cambridge.org/dictionary/english/supervise) defines the verb supervise as follows: to watch a person or activity to make certain that everything is done correctly, safely. By a slight extension of this definition, we could say that a supervisor is a teacher who tells us whether we are right or wrong. In this sense, the label performs the role of a supervisor for the machine as it is learning. With unlabeled data, there is no supervision available.


## Partitioning the dataset

As humans, how do we know if someone has learnt a skill or not? Tests or exams are the way to go. Exams are so ubiquitous that we often conflate learning with scoring well in exams. However, for a machine, getting a good score in an exam is a good enough proxy for learning. For almost every skill that we can think of, there is some test or exam to evaluate our competency in that skill. Take the analogy that we have been working with: three-digit addition. To know if kids have learnt addition, teachers conduct tests that have problems on three digit addition.

An important feature of testing is to make sure that it is challenging. If we ask the same questions that are there in the textbook, kids might score high marks. But chances are that a lot of them would have memorized the answers. Therefore, whenever we have a dataset, we always partition it into two parts:

- train-dataset
- test-dataset

We train the model on the train-dataset and evaluate its performance on the test-dataset. But often, we don't stop with two partitions, we go for three partitions:

- train-dataset
- validation-dataset
- test-dataset

Think about the validation-dataset as additional problems for practice or a mock exam that helps the machine learn a good model. The test-dataset is not shown to the model during the learning stage. The learning algorithm has access to only the train-dataset and the validation-dataset. Once the learning process is complete, the model is evaluated on the test-dataset. The test-dataset is sacred in any ML problem. It should be kept hidden and used only at the end. This is analogous to the effort taken by the administration of colleges and universities to seal exam papers and keep them secure until the day of the examination. If the exam paper somehow gets leaked, the exam can no longer be conducted in a fair manner!

## Summary

Datasets come in different types: tabular data, image, text, speech data and so on. The source of data varies from situation to situation. Sometimes the data could be given to us in a well formatted and usable condition. At other times, we would have to expend effort in gathering data and making it suitable for further processing. Datasets could either be labeled or unlabeled. ML algorithms that deal with labeled data are called supervised learning methods. To evaluate the performance of any ML model, it is important to partition the data into two parts: train, test; the model is trained on the training data and evaluated on the test data.