
# Tensorflow Playground

[Tensorflow playground](https://playground.tensorflow.org/)

* Learning tunable parameters
* Classification and regression with toy datasets
* Feature engineering, overfitting, train/test splits

## Regression

* Model 
  * 2 inputs (X1 & X2)
  * Goal: Model the data
* Measure model performance
  * Define a metric (single number) that measures performance in one of two equivalent ways:
  * Option #1: Define a score that rewards accurate predictions; maximize the score
    * Score of 1 means you make no mistakes
    * Negative score means the model makes too many mistakes
  * Option #2: define a loss metric that penalizes mistakes; minimize the loss
    * Loss = 1 - Score
    * Loss of 0 means you make no mistakes
    * Large positive loss if the model makes too many mistakes
* Learning
  * Objective: Learn the "weights" that you use for the feature inputs
  * Stated another way: Train the model by finding the weights that maximize the training score
  * Equivalently: Train the model by finding the weights that minimize the training loss
* Setup
  * Remove all the hidden layers
  * Reset
  * Show how the two inputs add to one another -- modify their weights
  * Let the model train on the data
  * Discretize the output -- either one or the other
  * Show the test data
* Loss -- measures the fraction of the data that has not been "learned"
  * Loss measures the fraction of the data that cannot be predicted?
* Generalizability
  * Use "Regenerate" to create a new version of the "noise" -- demonstrates the random behavior of "noisy data"
  * The model does extremely well with this dataseta (the features and the predictable part of the data are both linear)
* Discussion
  * We're limited in what we can achieve with regression in the playground
  * The classification demo has more interesting and challenging datasets

### Default configuration

* train/test ratio: 50%
* noise: 0
* 2 features: X1 & X2
* http://playground.tensorflow.org

### Exercise #1

* Problem type: Regression
* No hidden layers (no neural network)
* Investigate "ratio of training to test data"
* Investigate "noise"
* QUESTION: Can you find a scenario where training loss noticeably exceeds testing loss?
* ANSWER:
  * without any noise -- training and test loss are exactly zero
  * with a lot of noise the effect is there, but it's not large
    * ratio: training data 80%
    * noise: 50
    * test loss is 0.030
    * training loss is 032

## Classification

### Exercise #2

Problem type: Classification
* No hidden layers (no neural network)
* Data: Two blobs (dataset on lower left)
* Investigate "ratio of training to test data"
* Investigate "noise"
* QUESTION: Can you find a scenario where training loss noticeably exceeds testing loss?
* ANSWER:
  * without any noise -- training and test loss are exactly zero
  * with a lot of noise the effect is there, but it's not large
    * ratio: training data 80%
    * noise: 50
    * test loss is 0.030
    * training loss is 032

### Exercise #3

Repeat Exercise #2 using the XOR dataset (dataset on upper right -- 2 blue squares & 2 orange squares)
* ANSWER:
  * with or without noise -- train and test loss are about 50%

### Exercise #4

Repeat Exercise #2 using concentric circles (dataset on lower left)
* ANSWER:
  * discrepancy with train and test loss is noticeble
  * gets particularly large with noisy data and small test set
  * "Discretize output" shows that the model is predicting that everything is orange!

### Exercise #5

Repeat Exercise #2 using concentric spirals (dataset on lower right)
* ANSWER:
  * discrepancy with train and test loss is noticeble
  * gets particularly large with noisy data and small test set
  * "Discretize output" shows that the model is predicting that everything is orange!

### Exercise #6

* Start with the default configuration at this URL: http://playground.tensorflow.org
  * This should be the concentric circles dataset (upper left)
  * There should be 2 hidden layers with 4/2 neurons each
* QUESTION: How small can you make the network and still achieve perfect train/test scores of 0?
* QUESTION: What happens when you then reduce the number of neurons by one?
