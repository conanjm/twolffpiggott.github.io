---
layout: post
title: CS231n basic backpropagation derivation
---

Consider the vector of normalised probabilities $p$ loss function for the $i$th observation

$$
\begin{align}
p_k &= \frac{e^{f_k}}{\sum_{j=1}^K e^{f_j}}
\end{align}
$$

and the loss function for the net evaluated at the $i$th observation

$$
\begin{align}
\mathcal{L}_i &= \log\left(p_{y_i}}\right)
\end{align}
$$
