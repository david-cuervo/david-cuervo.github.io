---
layout: post
title:      "Neural Networks"
date:       2021-04-27 22:35:20 +0000
permalink:  neural_networks
---


For my final blog post, I wanted to write about a topic from the course that I've been really interested in learning more about, neural networks! Specifically, I was amazed to learn about a machine learning method that can deal with **unstructured data**. Unstructured data includes things like images and audio files. My whole career i've only worked with structured data that was packaged nicely into spreadsheets so neural networks really open up a world of possibilities. 

I got my bachelors in Neuroscience so I'm always fascinated when I see computer science takes inspiration from the miraculous machine that is the human brain. Below is an image of a neural network and you can already see how it gets its name.

![Neural Network databricks](https://databricks.com/wp-content/uploads/2019/02/neural1.jpg)

Each circle in the image above is a neuron that makes up the network. They're organized into layers : the input and output, which we've seen before, as well as a hidden layer. Essentially, the neural network takes in information from the input layer and is trained to use that information to predict the outcome. 

Let's see an example to help understand how the neural network learns. 

![8 neural network medium.com](https://miro.medium.com/max/1920/0*CcD4iaKXKMT4W-ap.png)

Numbers like this are common examples of images that can be used to train a neural network. The first step is to make an input layer out of an image like the one above. As we see, the 8 is made up of many pixels that form a grid. If we take this grid apart, or "derow" it, each pixel makes up a neuron in our input layer! Each pixel has a corresponding number that indicates its intensity. The higher the number, the more the pixel is "activated". These activated neurons (or pixels) in the input layer then activate neurons in the next layer and so on until the correct output neuron is selected. Just like neurons in the brain! 

The way the activated neurons from the input layer then activate the following hidden layer relies on the paramaters assigned to the network. This is how the network is trained to recognize the image! Each neuron in that input layer will have a parameter or **weight** assigned to it. These weights are positive or negative numbers. We want neurons that make the 8 shape to have more positive weights and the blank space neurons should have negative weights. 

We then sum the product of all of the input neurons and their weights and squeeze this summation into a sigmoid function (or a logistic function) so we can get a number between 0 and 1. 

![Sigmoid function towardsdatascience](https://miro.medium.com/max/1280/1*sOtpVYq2Msjxz51XMn1QSA.png)

This function determines whether or not a neuron in the following layer is activated. 

This was a very quick explanation of how a neural network works so I suggest checking out the following video which explains it further and with cool animations. 

[But what is a Neural Network?](https://youtu.be/aircAruvnKk)

At the end of the video they mention another function to replace the sigmoid, the ReLU function.

![ReLU medium.com](https://miro.medium.com/max/3228/1*LiBZo_FcnKWqoU7M3GRKbA.png)

It mirrors biological neurons more so than the sigmoid function because neurons in the brain are activated past a threshold. So they are either inactive (zero), or active enough to pass the threshold (above 0), no negative values needed. Apparently using ReLU functions are better at training neural networks than the sigmoid! Just another example of how much nature has to teach us. Hope you found this as interesting as I did! 
