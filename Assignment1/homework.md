

# Assignment #1 Hand Problems

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
