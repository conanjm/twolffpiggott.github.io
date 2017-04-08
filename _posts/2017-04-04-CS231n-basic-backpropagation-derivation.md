---
layout: post
title: CS231n basic backpropagation derivation
---

Consider the loss function for the $i$th observation

$$
\begin{align}
p_k &= \frac{e^{f_k}}{\sum_{j=1}^K e^{f_j}}
\end{align}
$$
