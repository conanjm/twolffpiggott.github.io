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
p_{y_i} &= \frac{e^{f_{y_i}}}{\sum_{j=1}^K e^{f_j}},
\end{align}
$$

$f_j = \boldsymbol{w_j}^\top \boldsymbol{x_i} + b_j$ is the score of the $i$th observation corresponding to the $j$th class, \boldsymbol{x_i} is the column vector corresponding to the $i$th observation, and $\boldsymbol{w_j}$ is the column vector corresponding to the weights for the $j$th class.

Given the upstream derivative of the loss with respect to the scores

$$
\begin{align}
\frac{\partial\mathcal{L}_i}{\partial f_k} &= p_k - \mathbb{1}\left(y_i=k\right)
\end{align}
$$

we're interested in deriving the derivative of the loss with respect to the weights and biases. Starting with the weights, we can use the can rule to get to the desired derivative via the derivatives of the loss with respect to the scores. 

$$
\begin{align}
\frac{\partial\mathcal{L}_i}{\partial \boldsymbol{w_j}} &= \sum_{k=1}^K \frac{\partial\mathcal{L}_i}{\partial f_k}\times\frac{\partial f_k}{\partial \boldsymbol{w_j}}\\
&= \frac{\partial\mathcal{L}_i}{\partial f_j}\times\frac{\partial f_j}{\partial \boldsymbol{w_j}}\\
&= \frac{\partial\mathcal{L}_i}{\partial f_j}\boldsymbol{x_i}\\
\end{align}
$$

which follows as the $j$th score is the only score where the vector $\boldsymbol{w_j}$ arises, and so the derivatives of the other scores with respect to $\boldsymbol{w_j}$ are all zero. Then, the total loss $\mathcal{L}$ is obtained as the summation of the losses across all $N$ observations, and so

$$
\begin{align*}
\frac{\partial\mathcal{L}}{\partial \boldsymbol{w_j}} &= \sum_{i=1}^N \frac{\partial\mathcal{L}_i}{\partial f_j}\boldsymbol{x_i}
\end{align*}
$$

$$
\begin{align*}
\begin{bmatrix}
    y_1y_1x_1^\top x_1&y_1y_2x_1^\top x_2&\ldots& y_1y_Nx_1^\top x_N\\
		y_2y_1x_2^\top x_1&y_2y_2x_1^\top x_2&\ldots& y_2y_Nx_2^\top x_N\\
		\ldots&\ldots&\ldots&\ldots\\
		y_Ny_1x_N^\top x_1&y_Ny_2x_N^\top x_2&\ldots& y_Ny_Nx_N^\top x_N\\
\end{bmatrix}
&=
\begin{bmatrix}
    x_{11} & \cdots & x_{N1}\\
    \vdots & \ddots & \vdots\\
    x_{1D} & \cdots & x_{ND}\\
\end{bmatrix}
\end{align*}
$$
