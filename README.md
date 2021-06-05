# digit-recognizer
A simple deep CNN that classifies hand written digits from the mnist dataset

## Overview
An implementation of a deep CNN to reconize hand written digits from the mnist dataset to their appropriate value
for a kaggle challenge.
The model was built using the tensorflow/keras libraries.
It achieved an accuracy of above 99%.

## Kaggle competition
This project is in response to the kaggle Digit Recocnizer competition https://www.kaggle.com/c/digit-recognizer.
The goal is to correctly identify digits from a dataset of tens of thousands of handwritten images.

## mnist dataset
The data is taken from the mnist (Modified National Institute of Standards and Technology) dataset.
Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255, inclusive. There are 42,000 labeled examples to work with.<br/>
![mnist dataset](https://github.com/rakrkracker/digit-recognizer/blob/master/images/mnist_ex.png)

## Libraries used
* TensorFlow
* Keras
* scikit-learn
* Numpy
* Pandas
* matplotlob
* seaborn

## Data
The original 42,000 images were split into training / validation sets with a ratio of 0.8 (33,600 training and 8,400 validation).
The images were normalized and the training set was augmented with rotations, axis shifts and zoom, for better generalization.

## The model
The model is a simple deep CNN. It uses 3 convolutional blocks to extract feartures, with added dropouts and batch normalizations for stability,
and a dense head for classification.<br/>
![model architecture](https://github.com/rakrkracker/digit-recognizer/blob/master/images/cnn_model_simple.png)

## Training
The model was trained in batches of size 128 and for a maximum of 100 epochs (a callback was added to stop training if nothing new was learned for multiple epochs).
The training stopped after 25 epochs.
The model reached an accuracy of about 99.3% (validation) and 99.7% (training), which indicated a good fit, without under- or overfitting.<br/>
![learning plots](https://github.com/rakrkracker/digit-recognizer/blob/master/images/training_plots.png)

## Evaluation
The classification confusion matrix shows that most of the digits were handeled correctly, with low false classification (mostly below 1%).

![confusion matrix](https://github.com/rakrkracker/digit-recognizer/blob/master/images/conf_matrix.png)

By digit:
0. True: 766, False: 1, False classification: 0.013%
1. True: 948, False: 7, False classification: 0.73%
2. True: 831, False: 8. False classification: 0.95%
3. True: 903, False: 5. False classification: 0.0.55%
4. True: 810, False: 5. False classification: 0.61%
5. True: 745, False: 8. False classification: 1.06%
6. True: 828, False: 4. False classification: 0.48%
7. True: 853, False: 5. False classification: 0.58%
8. True: 798, False: 4. False classification: 0.49%
9. True: 857, False: 13. False classification: 1.49%

There worst classification rate by far was for the digit 9, which was identified as 4 0.91% of the times.
