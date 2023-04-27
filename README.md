# IMDB_Sentiment_Analysis

The IMDB Review Data Set is a 
This is a dataset for binary sentiment classification containing substantially more data than previous benchmark datasets. It contains a set of 25,000 highly polar movie reviews for training and 25,000 for testing. So, predict the number of positive and negative reviews using either classification or deep learning algorithms.

In our exploration, we make use of this data set to develop a Sentiment Analysis Model that predicts whether a given review has a 'positive' or 'negative'. 

We tried 4 different Machine Learning Models in this exploration:

### 1) NAIVE BAYES - GAUSSIAN (GNB)

In a Gaussian Naive Bayes we assume that the words associated with each class( i.e positive or negative) are distributed along a **Normal Distribution**. This means that the probability density function (PDF) of a given word can be modelled using a **Gaussian Function** of the form :  

$p(x =v\mid y_{k})={\frac {1}{\sqrt {2\pi \sigma _{k}^{2}}}}\,e^{-{\frac {(v-\mu _{k})^{2}}{2\sigma _{k}^{2}}}}$

Where k = 2 (Number of classes - 0,1)

For each word x the classifer calculates the probablity **P(x| Y = y).P(Y=y)** for each class (0/1) y. In our case , if P(x| Y = 0).P(Y=0) > P(x| Y = 1).P(Y=1) , then our classifer predicts 0 (negative) and vice versa.


### 2) MULTIVARIATE NAIVE BAYES (MNB)

In a Multivariate Model we assume that the words are not *discrete* variables but *continuous* variables therefore are distributed along a **Multinomial Distribution**. The Likelihood function of a Multivariate Distribution is as follows:

$$p(\mathbf {x} \mid C_{k})={\frac {(\sum _{i=1}^{n}x_{i})!}{\prod _{i=1}^{n}x_{i}!}}\prod _{i=1}^{n}{p_{ki}}^{x_{i}}$$

In order to find the maximizer of the above likelihood function, we take the log of the function and try to maximize it:

$${\displaystyle {\begin{aligned}\log p(C_{k}\mid \mathbf {x} );=\log p(C_{k})+\sum _{i=1}^{n}x_{i}\cdot \log p_{ki}\\= \log p(C_{k}) +\mathbf {w} _{k}^{\top }\mathbf {x} \end{aligned}}}$$

Where ${w} _{k}^{\top }\mathbf {x} $ referes to the covariance matrix of the multivariate distribution

### 3) BERNOULLI NAIVE BAYES (BNB)

This is similar to a Multivariate Model, except individual words are treated as **Bernouli Random Variables**. That is, they are treated as Binary Variables- 0-1. This means that BNM differs from MNB, in that BNB measures onnly the presence/absence of a word. However a MNB measures the frequency (# of occourances) of a given word in a text. 

The likelihood function is as follows:

$${\displaystyle p(\mathbf {x} \mid C_{k})=\prod _{i=1}^{n}p_{ki}^{x_{i}}(1-p_{ki})^{(1-x_{i})}}$$

### 4) VADER SENTIMENT ANALYSIS

**VADER**(*Valence Aware Dictionary and Sentiment Reasoner*) is a fully open-source lexicon and rule-based sentiment analysis tool that is specifically attuned to sentiments expressed in social media. 
Given the nature of IMBDB Ratings as bearing some resemblence to Social- Media and microblogging sites, this lexicon might be usefull in increasing model accuracy as it is designed to handle slang and social-media related lexicons.

However, unlike our previous models the VADER lexicon assigns a *sentiment score* to each prediction. We then assign the classification of positive/negative(0,1) depending on a user-defined threshold. 

## RESULTS:

## PRIMARY ACCURACY RANKING:

- 1) Bernouli Naive Bayes - 83.8% Testing Accuracy
- 2) Multivariate Naive Bayes - 83.2% Testing Accuracy
- 3) Gaussian Naive Bayes - 78.4% Testing Accuracy
- 4) VADER Sentiment Analysis - 65.3%
