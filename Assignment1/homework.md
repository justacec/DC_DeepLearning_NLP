# 1a
 $$
\begin{align}
\frac{e^{x_j}}{\sum\limits_i e^{x_i}} & = \frac{e^{x_j+C}}{\sum\limits_i e^{x_i+C}} \\
& = \frac{e^{C}e^{x_j}}{\sum\limits_i e^{C}e^{x_i}} \\
& = \frac{e^{C}e^{x_j}}{e^{C}\sum\limits_i e^{x_i}} \\
& = \frac{e^{x_j}}{\sum\limits_i e^{x_i}}
\end{align}
$$

# 2a 

Let $$\sigma(x) = \frac{1}{1+e^{-x}}$$.  The derivative is the following:

$$
\begin{align}
\frac{d\sigma(x)}{dx} & = -\left(1+e^{-x}\right)^{-2}\left(-e^{-x}\right) \\
& = \sigma(x)^2e^{-x} \\
& = \sigma(x)^2\left(\frac{1}{\sigma(x)}-1\right) \\
& = \sigma(x)\left(1-\sigma(x)\right)
\end{align}
$$

# 2b

