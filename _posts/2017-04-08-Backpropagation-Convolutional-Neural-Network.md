---
layout: post
title: Backpropagation for Convolutional Neural Network
---
This post briefly covers backpropagation for a convolutional neural network, derived in the context of work on the second assignment for the Winter 2016 iteration of the Stanford class [CS231n: Convolutional Neural Networks for Visual Recognition](http://cs231n.stanford.edu/index.html).

This should be above the mathjax block.
$$ \begin{equation} \frac{d\mathcal{L}}{dh} = \begin{pmatrix} \frac{d\mathcal{L}}{dh_{11}} & .. & \frac{d\mathcal{L}}{dh_{1H}} \ .. & \frac{d\mathcal{L}}{dh_{kl}} & .. \ \frac{d\mathcal{L}}{dh_{N1}} & ... & \frac{d\mathcal{L}}{dh_{NH}} \end{pmatrix}. \end{equation} $$

This should be below the mathjax block.

Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.


