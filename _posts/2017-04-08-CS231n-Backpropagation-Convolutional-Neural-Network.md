---
layout: post
title: CS231n Backpropagation for convolutional neural network
---
This post briefly covers backpropagation for a convolutional neural network, derived in the context of work on the second assignment for the Winter 2016 iteration of the Stanford class [CS231n: Convolutional Neural Networks for Visual Recognition](http://cs231n.stanford.edu/index.html).

The setting for this post is a convolutional layer with input size $\left( N\atop 4, C\atop 3, H\atop 5, W\atop 5\right)$ $X = \left(  4,  3,  5,  5\right)$
<!---![_config.yml]({{ site.baseurl }}/images/convolution1.png)-->
<img src="/images/convolution1.png" width="500">

