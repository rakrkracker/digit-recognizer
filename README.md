# digit-recognizer
A simple deep CNN that classifies hand written digits from the mnist dataset

## Overview
An implementation of a deep CNN to reconize hand written digits from the mnist dataset to their appropriate value
for the kaggle challenge.
The model was built using the tensorflow/keras libraries.
It achieved an accuracy of above 99%.

## Kaggle competition
This project is in response to the kaggle Digit Recocnizer competition https://www.kaggle.com/c/digit-recognizer.
The goal is to correctly identify digits from a dataset of tens of thousands of handwritten images.

## mnist dataset
The data is taken from the mnist (Modified National Institute of Standards and Technology) dataset.
Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255, inclusive. There are 785 labeled examples to word with.<br/>
![mnist dataset](https://github.com/rakrkracker/digit-recognizer/blob/master/images/mnist_ex.png)

## Libraries used
* TensorFlow
* Keras
* Numpy
* Pandas
* matplotlob
* seaborn
* sklearn

