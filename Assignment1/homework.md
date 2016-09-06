

# Assignment #1 Solutions

Justace Clutter

## 1a

$$
\begin{align}
\frac{e^{x_j}}{\sum\limits_i e^{x_i}} & = \frac{e^{x_j+C}}{\sum\limits_i e^{x_i+C}} \\
& = \frac{e^{C}e^{x_j}}{\sum\limits_i e^{C}e^{x_i}} \\
& = \frac{e^{C}e^{x_j}}{e^{C}\sum\limits_i e^{x_i}} \\
& = \frac{e^{x_j}}{\sum\limits_i e^{x_i}}
\end{align}
$$

## 1b

Completed

## 2a

Let $\sigma(x) = \frac{1}{1+e^{-x}}$.  The derivative is the following:

$$
\begin{align}
\frac{d\sigma(x)}{dx} & = -\left(1+e^{-x}\right)^{-2}\left(-e^{-x}\right) \\
& = \sigma(x)^2e^{-x} \\
& = \sigma(x)^2\left(\frac{1}{\sigma(x)}-1\right) \\
& = \sigma(x)\left(1-\sigma(x)\right)
\end{align}
$$

## 2b

The softmax function is defined as:
$$
\hat{y}_i = \frac{e^{\theta_i}}{\sum\limits_je^{\theta_j}}
$$




The softmax derivative is:
$$
\begin{align}
\frac{\partial \hat{y}_i}{\partial \theta_k} & = \frac{e^{\theta_i}\delta_{ik}}{\sum\limits_je^{\theta_j}}-\frac{e^{\theta_i}}{\left(\sum\limits_ne^{\theta_n}\right)^2}e^{\theta_k} \\
& = \frac{e^{\theta_i}}{\sum\limits_ie^{\theta_i}}\left[\delta_{ik}-\frac{e^{\theta_k}}{\sum\limits_ne^\theta_n}\right] = \begin{cases}
\hat{y}_k(1-\hat{y}_k) & \text{if} \quad i=k\\
-\hat{y}_i\hat{y}_k & \text{if}\quad i\ne k
\end{cases}
\end{align}
$$


The Cross-Entropy function is defined as:
$$
\text{CE}(\mathbf{y},\mathbf{\hat{y}})=-\sum\limits_iy_i\log(\hat{y}_i)
$$
The Cross-Entrpy derivative (with respect to $\theta_k$) is:

$$
\begin{align}
\frac{\partial \text{ CE}}{\partial{\theta_k}} & = -\sum\limits_iy_i\frac{\partial \log(\hat{y}_i)}{\partial \theta_k} \\
& = -\sum\limits_iy_i\frac{1}{\hat{y}_i}\frac{\partial \hat{y_i}}{\partial \theta_k} \\
& = -\left\{y_k\frac{1}{\hat{y}_k}\left(\hat{y}_k(1-\hat{y}_k)\right)-\sum\limits_{i\ne k}y_i\hat{y}_k\hat{y}_i\frac{1}{\hat{y}_i}\right\} \\
& = -\left\{y_k(1-\hat{y}_k)-\sum\limits_{i\ne k}y_i\hat{y}_k\right\} \\
& = -\left\{y_k-y_k\hat{y}_k-\sum\limits_{i\ne k}y_i\hat{y}_k\right\} \\
& = -y_k+\hat{y}_k\sum\limits_iy_i \\
& = \hat{y}_k-y_k
\end{align}
$$

## 2c

This solution will leverage the previous solution and then use the chain rule to get to the final input nodes.  The additional functions $z_1$ and $z_2$ are defined as:
$$
\begin{align}
\mathbf{z_1} & = \text{sigmoid}(\mathbf{x}\mathbf{W_1}+\mathbf{b_1})\\
\mathbf{z_2} & = \mathbf{z_1}\mathbf{W_2}+\mathbf{b_2}
\end{align}
$$

$$
\begin{align}
\frac{\partial \text{ CE}}{\partial x} & = \left(\mathbf{\hat{y}}-\mathbf{y}\right)\frac{\partial z_2}{\partial z_1}\frac{\partial z_1}{\partial x}\\
& = \left(\mathbf{\hat{y}}-\mathbf{y}\right)\mathbf{W_2}\frac{\partial z1}{\partial x}\\
& = \left(\mathbf{\hat{y}}-\mathbf{y}\right)\mathbf{W_2}\sigma' \mathbf{W_1}\\
& = \left(\mathbf{\hat{y}}-\mathbf{y}\right)\mathbf{W_2}\left[\sigma(\mathbf{x}\mathbf{W_1}+\mathbf{b_1})\left(1-\sigma(\mathbf{x}\mathbf{W_1}+\mathbf{b_1})\right)\right]\mathbf{W_1}\\
& = \left(\mathbf{\hat{y}}-\frac{e^{\mathbf{z_2}}}{\left|e^{\mathbf{z_2}}\right|}\right)\mathbf{W_2}\left[\sigma(\mathbf{x}\mathbf{W_1}+\mathbf{b_1})\left(1-\sigma(\mathbf{x}\mathbf{W_1}+\mathbf{b_1})\right)\right]\mathbf{W_1}\\
\end{align}
$$


## 2d

$$
(D_x+1)H+(H+1)D_y
$$

## 2e

Completed

## 2f

Completed

## 2g

Completed.  But I do not understand why the derivaties seem to have reverse matrix multiplication.