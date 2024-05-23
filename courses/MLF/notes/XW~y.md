---
title: $\mathbf{Xw} \approx \mathbf{y}$
pagetitle: Xw~y
order: 7
---

::: {.callout-note title="Question"}
How do we solve for $\mathbf{w}$ in the equation $\mathbf{Xw} \approx \mathbf{y}$?
:::

## Approximation

So far we have seen the well behaved case of $\mathbf{Xw} =\mathbf{y}$. What if $\mathbf{y}$ is not in the column space of $\mathbf{X}$? Then $\mathbf{Xw} \neq \mathbf{y}$. This is by far the most interesting and relevant scenario from the perspective of the linear regression problem. Recall that we are trying to estimate a weight vector $\mathbf{w}$, given the labeled dataset $(\mathbf{X} ,\mathbf{y} )$. The relationship between inputs and outputs is assumed to be linear. But the real world doesn't behave exactly like we want it to. There are going to be obvious deviations from our ideal assumptions. In other words, our models can never be an entirely accurate representation of reality.

This is a typical scenario observed in engineering and the sciences. We don't abandon the problem because it doesn't admit an exact solution. Instead, we turn to a powerful weapon in our armory: approximations. Can we find a $\mathbf{\widehat{w}}$ such that $\mathbf{X}\widehat{\mathbf{w}} \approx \mathbf{y}$? What do we mean by the symbol $\approx$ here? We are dealing with two vectors on either side of the symbol. Let us first understand what the symbol means when we have scalars.

Let us look at the following statements:

- $1.234\approx 1$
- $1.234\approx 1.2$
- $1.234\approx 1.23$

These are three approximations. From experience, we know that the second approximation is better than the first and the third better than the second. If we plot these points on a real line, the goodness of an approximation can be interpreted using the distance between the original point and its approximation: smaller the distance, better the approximation.

This very idea is extended to an $n$ dimensional vector space. If $\mathbf{y}$ and $\mathbf{\widehat{y}}$ are two vectors in $\mathbb{R}^{n}$, then the Euclidean distance between them is a measure of the goodness of the approximation. To avoid taking square roots, we write down the expression for the squared distance:

$$
\begin{equation*}
||\widehat{\mathbf{y}} -\mathbf{y} ||^{2} =(\widehat{y}_{1} -y_{1} )^{2} +\cdots +(\widehat{y}_{n} -y_{n} )^{2}
\end{equation*}
$$

The key to solving the problem $\mathbf{Xw} \approx \mathbf{y}$, is to find a vector $\widehat{\mathbf{w}}$ such that $\mathbf{X}\widehat{\mathbf{w}}$ is as close to $\mathbf{y}$ as possible. This can be framed as an optimization problem:

$$
\begin{equation*}
\widehat{\mathbf{w}} =\underset{\mathbf{w}}{\arg\min} \ \ ||\mathbf{Xw} -\mathbf{y} ||^{2}
\end{equation*}
$$

If you are seeing $\arg\min$ for the first time, think about it like a function (in the programming sense):

- Find the value that minimizes the expression
- Return this value to the user

## Least Squares Problem

Let us go ahead and solve the minimization problem.

$$
\begin{equation*}
\underset{\mathbf{w}}{\min} \ \ \ ||\mathbf{Xw} -\mathbf{y} ||^{2}
\end{equation*}
$$

Let us call the expression to be minimized the loss, $L(\mathbf{w})$, which is also called the objective function of the optimization problem. It can be simplified as follows:

$$
\begin{equation*}
\begin{aligned}
L(\mathbf{w}) & =||\mathbf{Xw} -\mathbf{y} ||^{2}\\
 & \\
 & =(\mathbf{Xw} -\mathbf{y} )^{T} (\mathbf{Xw} -\mathbf{y} )\\
 & 
\end{aligned}
\end{equation*}
$$

This is often called the least squares problem. To see why this name is used, we will look at the loss function from a slightly different perspective. Since $\mathbf{Xw}$ is an approximation of $\mathbf{y}$, $\mathbf{e} =\mathbf{Xw} -\mathbf{y}$ can be seen as an error vector. So:

$$
\begin{equation*}
L(\mathbf{w}) =\mathbf{e}^{T}\mathbf{e} =e_{1}^{2} +\cdots +e_{n}^{2}
\end{equation*}
$$

From a ML standpoint, recall the housing dataset with which we started. $e_{i}$ is the difference between the actual selling price of the $i^{th}$ house and its predicted selling price as given by our linear model. To be more specific, we see that $\displaystyle e_{i} =\mathbf{w}^{T}\mathbf{x}_{i} -y_{i}$. Plugging this into the loss function:

$$
\begin{equation*}
L(\mathbf{w}) =\sum\limits _{i=1}^{n}\left(\mathbf{w}^{T}\mathbf{x}_{i} -y_{i}\right)^{2}
\end{equation*}
$$

In a sense, we are justified in calling $\mathbf{e}$ the error vector. We are minimizing the sum of the squared errors, hence the term "least squares". $\widehat{\mathbf{w}}$ is that weight vector for the linear model which will give us the best possible fit.

## Normal Equations

We now follow the usual procedure of finding the minimum of a function. Take the derivatives and set them to zero. Since we are dealing with a multivariable function, we have to consider all the partial derivatives. The vector of such partial derivatives is called the gradient.

$$
\begin{equation*}
\nabla L(\mathbf{w}) =\begin{bmatrix}
\cfrac{\partial L(\mathbf{w})}{\partial w_{1}}\\
\vdots \\
\cfrac{\partial L(\mathbf{w})}{\partial w_{d}}
\end{bmatrix}
\end{equation*}
$$

Let us now compute the gradient and set it to zero. To simplify the gradient computation, let us go back to that form of the loss function which uses the sum of the squared errors:

$$
\begin{equation*}
\begin{aligned}
L(\mathbf{w}) & =\sum\limits _{i=1}^{n}\left(\mathbf{w}^{T}\mathbf{x}_{i} -y_{i}\right)^{2}
\end{aligned}
\end{equation*}
$$

Taking the gradient with respect to $\displaystyle \mathbf{w}$ and using the chain rule we get:

$$
\begin{equation*}
\begin{aligned}
\nabla L(\mathbf{w}) & =2\cdot \sum\limits _{i=1}^{n}\left(\mathbf{w}^{T}\mathbf{x}_{i} -y_{i}\right) \cdot \mathbf{x}_{i}\\
 & \\
 & =2\cdot \mathbf{X}^{T}(\mathbf{Xw} -\mathbf{y})
\end{aligned}
\end{equation*}
$$

Setting the gradient equal to zero, we get:

$$
\begin{equation*}
\begin{aligned}
\mathbf{X}^{T}(\mathbf{Xw} -\mathbf{y}) & =0
\end{aligned}
\end{equation*}
$$

This gives us the following equation for $\displaystyle \mathbf{w}$:

$$
\begin{equation*}
\mathbf{X}^{T}\mathbf{Xw} =\mathbf{X}^{T}\mathbf{y}
\end{equation*}
$$

This system is called the normal equations. If the matrix $\mathbf{X}^{T}\mathbf{X}$ is invertible, then we have the following solution:

$$
\begin{equation*}
\widehat{\mathbf{w}} =(\mathbf{X}^{T}\mathbf{X} )^{-1}\mathbf{X}^{T}\mathbf{y}
\end{equation*}
$$

We still don't know if this corresponds to a minima. Rest assured that this is indeed a minima. But we won't take up the proof now. The other worrying part is what happens if the matrix $\mathbf{X}^{T}\mathbf{X}$ is singular or non-invertible. It turns out that even in this situation, this system is always consistent. The proof of consistency is a bit involved. It has been moved to the appendix on the matrix $\mathbf{X}^T \mathbf{X}$.

::: {.callout-note title="Remarks" collapse=true}

A few more technical points regarding this system which can be safely skipped for now:

- There is the question concerning the uniqueness of the solution. A unique solution is guaranteed if $\mathcal{N}(\mathbf{X}^T\mathbf{X}) = \{\mathbf{0}\}$ which happens when the columns of $\mathbf{X}$ are linearly independent. Since the columns represent the various features, in practice, this means that the features are all independent of each other. That is, each feature adds some unique information for a data-point and cannot be obtained by combining the other features linearly.
- There is an interesting particular solution to the normal equations given in terms of a quantity called the pseudoinverse, which exits for all matrices. The pseudoinverse of the matrix $\mathbf{X}$ is denoted by $\mathbf{X}^{\dagger}$. The dimension of $\mathbf{X}^{\dagger}$ is $d \times n$. The "least squares solution" to the system $\mathbf{Xw} = \mathbf{y}$ is given by:

$$
\mathbf{X}^{\dagger} \mathbf{y}
$$

- If $\mathbf{X}$ has full column rank, then the pseudoinverse becomes $(\mathbf{X}^T \mathbf{X})^{-1}\mathbf{X}^T \mathbf{y}$.
- This solution has the wonderful property that it has the least norm among all solutions to the normal equations.

:::

## Summary

When $\mathbf{y}$ is not in the column space of $\mathbf{X}$, we look for an approximate solution. One way to specify a good approximation is to find a $\widehat{\mathbf{w}}$ that minimizes the following loss function:

$$
\begin{equation*}
L(\mathbf{w}) =(\mathbf{Xw} -\mathbf{y} )^{T} (\mathbf{Xw} -\mathbf{y} )
\end{equation*}
$$

This $\mathbf{\widehat{w}}$ is given by the solution to the normal equations:

$$
\begin{equation*}
(\mathbf{X}^{T}\mathbf{X} )\widehat{\mathbf{w}} =\mathbf{X}^{T}\mathbf{y}
\end{equation*}
$$

This system always has a solution. In the next few units, we shall try to understand the least squares problem from the lens of geometry.