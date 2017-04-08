---
layout: post
title: CS231n basic backpropagation derivation
---
Consider the loss function for the net evaluated at the $i$th observation

$$
\begin{align}
\mathcal{L}_i &= \log\left(p_{y_i}\right)
\end{align}
$$

where $p_{y_i}$ is the vector of normalised probabilities

$$
\begin{align}
p_{y_i} &= \frac{e^{f_{y_i}}}{\sum_{j=1}^K e^{f_j}}
\end{align}
$$

and $f_j = \boldsymbol{w_j}^\top \boldsymbol{x_i} + b_j$ is the score of the $i$th observation corresponding to the $j$th class.

Given the upstream derivative of the loss with respect to the scores

$$
\frac{\partial\mathcal{L}_i}{\partial f_k} &= p_k - \mathbbm{1}
$$
