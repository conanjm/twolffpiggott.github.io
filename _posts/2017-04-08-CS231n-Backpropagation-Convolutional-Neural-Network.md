---
layout: post
title: CS231n Backpropagation for convolutional neural network
---
This post briefly covers backpropagation for a convolutional neural network, derived in the context of work on the second assignment for the Winter 2016 iteration of the Stanford class [CS231n: Convolutional Neural Networks for Visual Recognition](http://cs231n.stanford.edu/index.html).

As in the assignment, the setting for this post is a convolutional layer with input size $X = \left(  4,  3,  5,  5\right)$, where the dimensions of the input refer to number of input observations $N$, input depth $C$, input height $H$ and input width $W$. The convolutional layer has two channels $F$, again a filter depth $C$ of three and also a filter height $HH$ and filter width $WW$ of three, corresponding to the weight tensor $W = \left(2, 3, 3, 3\right)$. The upstream derivative $dV = \left(4, 2, 5, 5\right)$ corresponds to the number of input observations $N$, number of channels $F$, and output height and width $H_{out}$ and $W_{out}$.

Let's first make sense of the upstream derivative. For the convolutional layer, there are $F = 2$ different 3D filters, each of which convolves over the input (with zero-padding $P$ of size 1), using a stride  $S$ of 1. The first step is to calculate the number of unique positions (and hence output volume) implied by the input size, filter size, stride and padding. This is easily calculated according to

$$
\begin{align}
H_{out} = (H−HH+2P)/S+1 && W_{out} = (W−WW+2P)/S+1\\
= (5 - 3 + 2 \times 1)/1 +1 && = (5 - 3 + 2 \times 1)/1 +1
= 5 && = 5\\
\end{align}
$$
<!---![_config.yml]({{ site.baseurl }}/images/convolution1.png)-->
<img src="/images/convolution1.png" width="500">

