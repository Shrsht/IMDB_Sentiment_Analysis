# IMDB_Sentiment_Analysis

The IMDB Review Data Set is a 
This is a dataset for binary sentiment classification containing substantially more data than previous benchmark datasets. It contains a set of 25,000 highly polar movie reviews for training and 25,000 for testing. So, predict the number of positive and negative reviews using either classification or deep learning algorithms.

In our exploration, we make use of this data set to develop a Sentiment Analysis Model that predicts whether a given review has a 'positive' or 'negative'. 

We tried 4 different Machine Learning Algorithms in this exploration:

### 1) NAIVE BAYES - GAUSSIAN (GNB)

In a Gaussian Naive Bayes we assume that the words associated with each class( i.e positive or negative) are distributed along a **Normal Distribution**. This means that the probability density function (PDF) of a given word can be modelled using a **Gaussian Function** of the form :  

$p(x =v\mid y_{k})={\frac {1}{\sqrt {2\pi \sigma _{k}^{2}}}}\,e^{-{\frac {(v-\mu _{k})^{2}}{2\sigma _{k}^{2}}}}$

Where k = 2 (Number of classes - 0,1)

For each word x the classifer calculates the probablity **P(x| Y = y).P(Y=y)** for each class (0/1) y. In our case , if P(x| Y = 0).P(Y=0) > P(x| Y = 1).P(Y=1) , then our classifer predicts 0 (negative) and vice versa.
