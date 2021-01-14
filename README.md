# Mask Detection

## How to properly wear a face mask?

<br/>
We have all seen it, people wearing masks under their chins, not at all, or even with their noses hanging out. 

For this capstone I am exloring Convolutional Neural Networks and their ability to classify images. My goal is to build a model that will be able to detect whether or not and individual is wearing a face mask "properly". By "properly" I mean covering the face and nose. 
<br/>

<br/>



## Background and Motivation

For a better part of a year now we have been dealing with with masks due to this Covid pandemic. This period of time has had all kinds of controvesry but nothing as innocuous as wearing a mask! There have been many debates about how to wear a mask properly and whether it prevents you from getting oxygen. 

We have all been there at a grocery store and someone is either wearing a mask with their nose hanging out of the top of their mask (What do they think happens when you sneeze?)

I do believe this has a real world use case, we can track and record how many people are wearing masks correctly, incorrectly, or not at all see what the impact of the virus transmission is with enough data. 

## The Data

[This](https://www.kaggle.com/spandanpatnaik09/face-mask-detectormask-not-mask-incorrect-mask) is the data set I am using

It is broken down into 3 categories:

1. People wearing mask
2. People not wearing mask
3. People wearing mask but in an incorrect manner

This dataset set contains 2089 images. 

### Distribution of Data

You can see that my data has a fairly even distribution, so we have no issues with unbalanced classes.

![alt text](https://github.com/okayvinay/mask_detection/blob/main/img/train_dist.png) ![alt text](https://github.com/okayvinay/mask_detection/blob/main/img/Validation_dist.png)

Here the data is split 80/20 for training and validation. I used Keras Tensorflow to read in the image and apply some preprocessing. 

I also use Data Augmentation here
![alt text](https://github.com/okayvinay/mask_detection/blob/main/img/augmented.png)


## Convolutional Neural Networks 
Convolutional Neural Networks are great for image classification, I built a 3 layer CNN using RELU for my activation function. Below you will see an illustration of my model

![alt text](https://github.com/okayvinay/mask_detection/blob/main/img/Screen%20Shot%202021-01-14%20at%2012.39.50%20PM.png)

From left to right we have an input layer where the image is received in and passed through each convolutional layer and pooling layer and then finally being output and a probability is assigned to the classification. 

Below you can see more detail of what happens in each convolutional layer. 

![alt text](https://github.com/okayvinay/mask_detection/blob/main/img/Screen%20Shot%202021-01-14%20at%2012.40.04%20PM.png)

In each convolutional layer a "filter" slides or "convolves" over the image to match patterns, edges, shapes, and textures. The deeper the network the more complex objects can be identified including facial features, whole dogs, lizards, or other objects. 


## Results 
The results were very surprising and suspicious, I only had 18 misclassifications and an accuracy of 96%. This is unusually high for such a shallow CNN. 

![https://github.com/okayvinay/mask_detection/blob/main/img/confusion_matrix.png]

