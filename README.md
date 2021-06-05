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
Each image is 28 pixels in height and 28 pixels in width, for a total of 784 pixels in total. Each pixel has a single pixel-value associated with it, indicating the lightness or darkness of that pixel, with higher numbers meaning darker. This pixel-value is an integer between 0 and 255, inclusive. There are 42000 labeled examples to work with.<br/>
![mnist dataset](https://github.com/rakrkracker/digit-recognizer/blob/master/images/mnist_ex.png)

## Libraries used
* TensorFlow
* Keras
* Numpy
* Pandas
* matplotlob
* seaborn
* sklearn

## Data
The original 42000 images were split into training / validation sets with a ratio of 0.8 (33600 training and 8400 validation).
The images were normalized and the training set was augmented with rotations, axis shifts and zoom, for better generalization.

## The model
The model is a simple deep CNN. It uses 3 convolutional blocks to extract feartures, with added dropouts and batch normalizations for stability,
and a dense head for classification.<br/>
![model architecture](https://github.com/rakrkracker/digit-recognizer/blob/master/images/cnn_model.png)

## Training
The model was trained in batches of size 128 and for a maximum of 100 epochs (a callback was added to stop training if nothing new was learned for multiple epochs).
The training stopped after 25 epochs.

## Evaluation
The model reached an accuracy of about 99.3% (validation) and 99.7% (training), which indicated a good fit, without under- or overfitting.<br/>
![learning plots](https://github.com/rakrkracker/digit-recognizer/blob/master/images/training_plots.png)

The classification confusion matrix shows that most of the digits were handeled correctly, with low false classification.
By digit:
digit 0. 1-766 -> 0.013%
digit 1. 7-948 -> 0.73%
2. 8-831 -> 0.95%
3. 5-903 -> 0.55%
4. 5-810 -> 0.61%
5. 8-745 -> 1.06%
6. 4-828 -> 0.48%
7. 5-853 -> 0.58%
8. 4-798 -> 0.49%
9. 13-857 -> 1.49%
<br/>
![confusion matrix](https://github.com/rakrkracker/digit-recognizer/blob/master/images/conf_matrix.png)
