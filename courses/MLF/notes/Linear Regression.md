---
title: Linear Regression
pagetitle: Linear Regression
order: 5
---

::: {.callout-note title="Question"}
What is a linear regression model?
:::

## Motivation

In this part, we will try to solve the regression problem that we introduced in the first part. Let us formally define the problem:

::: {.callout-note title="Problem"}
Predict the selling price of a house given the data of $\displaystyle n$ houses, where each house is represented by $\displaystyle d$ features.
:::

Consider two houses, one which has an area of $1000$ square feet and the other which has an area of $2000$ square feet. As the area of the house increases, the selling price is going to go up. Take another feature, say the distance from the nearest school. If the distance increases, then the selling price goes down. Perhaps the effect may not be as drastic. If we have access to only these two features, one function or model could be as follows:

$$
\begin{equation*}
\text{Selling-price} =2\times \text{Area} -0.2\times \text{Distance} +\text{Constant}
\end{equation*}
$$

This is what is called a linear model. The values $2$ and $-0.2$ are called the coefficients or weights. The magnitude of a weight denotes the importance of the corresponding feature. Its sign denotes the effect it has on the output. For example, the distance feature is negatively correlated with the selling-price, but it is not as important as the area.

::: {.callout-note title="Remark"}
We might be wrong about the choice of weights. Even worse, the relationship between the selling price and the two features may not even be linear! It is important to understand that a model is some approximation of the underlying reality. There is a nice quote that summarizes this idea: 
> All models are wrong, but some are useful.
:::

## Linear model

Generalizing this, let us say that we have a feature vector $\mathbf{x}$ and a weight vector $\mathbf{w}$. Recall that the housing data has six features:

$$
\begin{equation*}
\mathbf{x} =\begin{bmatrix}
x_{1}\\
x_{2}\\
x_{3}\\
x_{4}\\
x_{5}\\
x_{6}
\end{bmatrix} ,\ \mathbf{w} =\begin{bmatrix}
w_{1}\\
w_{2}\\
w_{3}\\
w_{4}\\
w_{5}\\
w_{6}
\end{bmatrix}
\end{equation*}
$$


The function or model that maps a data-point to the label $y$ (selling-price) is:

$$
\begin{equation*}
y=x_{1} w_{1} +x_{2} w_{2} +x_{3} w_{3} +x_{4} w_{4} +x_{5} w_{5} +x_{6} w_{6} +\text{constant}
\end{equation*}
$$

We can rewrite the constant as one more weight, say $w_{0}$:

$$
\begin{equation*}
y=x_{1} w_{1} +x_{2} w_{2} +x_{3} w_{3} +x_{4} w_{4} +x_{5} w_{5} +x_{6} w_{6} +w_{0}
\end{equation*}
$$

Going back to the vectors, we add a feature $1$ to the feature vector and a $w_{0}$ to the weights:

$$
\begin{equation*}
\mathbf{x} =\begin{bmatrix}
1\\
x_{1}\\
x_{2}\\
x_{3}\\
x_{4}\\
x_{5}\\
x_{6}
\end{bmatrix} ,\mathbf{w} =\begin{bmatrix}
w_{0}\\
w_{1}\\
w_{2}\\
w_{3}\\
w_{4}\\
w_{5}\\
w_{6}
\end{bmatrix}
\end{equation*}
$$


If we now look at the expression for $y$, it is nothing but the dot-product of the two vectors:

$$
\begin{equation*}
\begin{aligned}
y & =1\cdot w_{0} +x_{1} w_{1} +x_{2} w_{2} +x_{3} w_{3} +x_{4} w_{4} +x_{5} w_{5} +x_{6} w_{6}\\
 & \\
 & =\mathbf{w}^{T}\mathbf{x}
\end{aligned}
\end{equation*}
$$

$\mathbf{w}^{T}\mathbf{x}$ is the dot product between the two vectors $\displaystyle \mathbf{w}$ and $\mathbf{x}$. This is the notation that we will be using for the dot product from now on. This is the same as the matrix-product of a row-vector and a column-vector:


$$
\begin{equation*}
y=\mathbf{w}^{T}\mathbf{x} =\begin{bmatrix}
w_{0} & w_{1} & w_{2} & w_{3} & w_{4} & w_{5} & w_{6}
\end{bmatrix}\begin{bmatrix}
1\\
x_{1}\\
x_{2}\\
x_{3}\\
x_{4}\\
x_{5}\\
x_{6}
\end{bmatrix}
\end{equation*}
$$

The linear model is therefore expressed as:

$$
\begin{equation*}
f(\mathbf{x}) =\mathbf{w}^{T}\mathbf{x}
\end{equation*}
$$

If $\mathbf{x}$ is the feature vector of a house, then $f(\mathbf{x} )$ will be its predicted selling price. We call $\displaystyle \mathbf{w}$ the weight vector of the model. The elements of $\displaystyle \mathbf{w}$ are called the parameters of the model.

::: {.callout-note title="Remark"}
All vectors will be expressed as column vectors. If we want to express a row-vector, then it will be denoted as $\mathbf{x}^{T}$, where $\mathbf{x}$ is some column-vector.}
:::

## Learning problem

So much for one house. But we have several houses.  If we assume that the relationship between the labels and features is perfectly linear, we can write down $\displaystyle n$ linear equations, one for each house, in terms of $\displaystyle 7$ unknowns. For the sake of brevity, we will just list down the equation for the $\displaystyle i^{th}$ house. Since the unknown values are the $\displaystyle w$s, we will make that the LHS and the $\displaystyle y$s the RHS:

$$
\begin{equation*}
\begin{aligned}
w_{0} +x_{i1} \cdot w_{1} +x_{i2} \cdot w_{2} +x_{i3} \cdot w_{3} +x_{i4} \cdot w_{4} +x_{i5} \cdot w_{5} +x_{i6} \cdot w_{6} & =y_{i}
\end{aligned}
\end{equation*}
$$

These $\displaystyle n$ equations can be given a neat matrix representation:

$$
\begin{equation*}
\begin{bmatrix}
1 & x_{1,1} & x_{1,2} & x_{1,3} & x_{1,4} & x_{1,5} & x_{1,6}\\
\vdots  & \vdots  & \vdots  & \vdots  & \vdots  & \vdots  & \vdots \\
1 & x_{n,1} & x_{n,2} & x_{n,3} & x_{n,4} & x_{n,5} & x_{n,6}
\end{bmatrix}\begin{bmatrix}
w_{0}\\
w_{1}\\
w_{2}\\
w_{3}\\
w_{4}\\
w_{5}\\
w_{6}
\end{bmatrix} =\begin{bmatrix}
y_{1}\\
\vdots \\
y_{n}
\end{bmatrix}
\end{equation*}
$$

If we call the data-matrix $\mathbf{X}$, the label vector $\mathbf{y}$ and the weight vector $\mathbf{w}$, this is the equation we have:

$$
\begin{equation*}
\mathbf{Xw} =\mathbf{y}
\end{equation*}
$$

We are given both $\mathbf{X}$ and $\mathbf{y}$. This is nothing but our labeled dataset. We have to learn our weight vector $\mathbf{w}$. This leaves us with two questions:

- Does the equation $\mathbf{Xw} =\mathbf{y}$ have a solution?
- If it doesn't have a solution, how do we estimate $\mathbf{w}$?

The answer to the first question is that, the equation $\mathbf{Xw} =\mathbf{y}$ may not have a solution in practice. This could be because of the following reasons:

- Case-1: The relationship between $\mathbf{X}$ and $\mathbf{y}$ is not linear.
- Case-2: Even if the relationship is linear, the labels may be corrupted by some noise $\epsilon$.

Recall the quote with which we began this unit: "all models are wrong, but some are useful." In the first case, we can't do much. We would have to abandon the simple linear model and go for more complex models. In the second case, we still have hope. This situation is generally expressed as follows:

$$
\begin{equation*}
\mathbf{y} =\mathbf{Xw} +\mathbf{\epsilon }
\end{equation*}
$$

Here, $\mathbf{\epsilon }$ is some small error term. The error-term for each house is assumed to be a small value that is equal to zero on average. The general approach in such situations is to find a set of weights that minimizes the error in prediction. Here is what we mean by this:

Consider the $\displaystyle i^{th}$ house. The actual selling price for it is $\displaystyle y_{i}$. The predicted selling price is $\displaystyle f(\mathbf{x}_{i})$. Therefore, the error in prediction for this house is $\displaystyle f(\mathbf{x}_{i}) -y_{i}$. Since we are only interested in the absolute value of the error, it is a good idea to square this quantity: $\displaystyle [ f(\mathbf{x}_{i}) -y_{i}]^{2}$. Summing this term across all $\displaystyle n$ houses gives us a measure of how good the function $\displaystyle f$ is in predicting the selling prices:

$$
\begin{equation*}
\begin{aligned}
L(\mathbf{w} ) & =\sum\limits _{i=1}^{n}[ f( x_{i}) -y_{i}]^{2}\\
 & \\
 & =\sum\limits _{i=1}^{n}\left[\mathbf{w}^{T}\mathbf{x}_{i} -y_{i}\right]^{2}
\end{aligned}
\end{equation*}
$$

This is called the sum of squared errors or SSE. The quantity $\displaystyle L(\mathbf{w})$ is called the error function or the loss function. Lower the value of the loss function, better our model. The learning problem in linear regression can be formulated as finding a vector of weights — $\mathbf{w}$ — that will minimize the loss $L(\mathbf{w} )$:

$$
\begin{equation*}
\underset{\mathbf{w}}{\min} \ \ L(\mathbf{w})
\end{equation*}
$$

Let us now recast the loss function using the data-matrix $\displaystyle \mathbf{X}$ and label vector $\displaystyle \mathbf{y}$. Consider the vector $\displaystyle \mathbf{Xw}$. This is a $\displaystyle n\times 1$ vector that contains the predicted labels for all $\displaystyle n$ houses. So, the loss function can also be written as:

$$
\begin{equation*}
\begin{aligned}
L(\mathbf{w}) & =\sum\limits _{i=1}^{n}[(\mathbf{Xw})_{i} -y_{i}]^{2}\\
 & \\
 & =(\mathbf{Xw} -\mathbf{y} )^{T} (\mathbf{Xw} -\mathbf{y} )
\end{aligned}
\end{equation*}
$$

## Mathematical Viewpoint

Another way of looking at this problem is as follows. Since we cannot solve $\displaystyle \mathbf{Xw} =\mathbf{y}$, can we at least try to find an approximate solution such that $\displaystyle \mathbf{Xw} \approx \mathbf{y}$? It turns out that the loss function $\displaystyle L(\mathbf{w})$ defined in the previous section is just such a function that makes the notion of approximation precise. Smaller the value of $\displaystyle L(\mathbf{w})$, closer is $\displaystyle \mathbf{Xw}$ to $\displaystyle \mathbf{y}$, and hence better the approximation.

Let us revisit the system of equations we started with: $\displaystyle \mathbf{Xw} =\mathbf{y}$. As stated earlier, we will encounter this situation only if our label is a linear function of the features. But it might still be a good idea to understand how to solve the equality case before we try to find an approximate solution. We will therefore try to solve the following sequence of equations:

- $\mathbf{Xw} =\mathbf{0}$
- $\mathbf{Xw} =\mathbf{y}$
- $\displaystyle \mathbf{Xw} \approx \mathbf{y}$

The equation $\displaystyle \mathbf{Xw} =\mathbf{0}$ serves as a good starting point before jumping into the more general case of $\displaystyle \mathbf{Xw} =\mathbf{y}$.

## Summary

A linear regression model assumes a linear relationship between inputs and outputs, where the model is expressed as $f(\mathbf{x} )=\mathbf{w}^{T}\mathbf{x}$. If the labeled dataset is $(\mathbf{X} ,\mathbf{y} )$, our task is to learn the parameters $\mathbf{w}$ from the data by minimizing a loss function defined as:

$$
\begin{equation*}
L(\mathbf{w} )=(\mathbf{Xw} -\mathbf{y} )^{T} (\mathbf{Xw} -\mathbf{y} )
\end{equation*}
$$