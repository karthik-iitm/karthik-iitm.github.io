---
title: Question-4
pagetitle: Question-4
---

If $A$ is invertible, does the system $\text{adj}(A)x=b$ have a solution? If yes, find the solution. Is it unique?

------------------------------------------------------------------------

We have:

$$
A\cdot\text{adj}(A)=\text{det}(A)\cdot I
$$


Since $A$ is invertible, $A^{-1}$ exists. We can pre-multiply both sides of the above equation by $A^{-1}$ to get:

$$
\begin{aligned}
A^{-1}A\cdot\text{adj}(A) & =\text{det}(A)A^{-1}\\
\implies\text{adj}(A) & =\text{det}(A)A^{-1}
\end{aligned}
$$


Notice that $\text{adj}(A)$ is just a non-zero multiple of $A^{-1}$. So $\text{adj}(A)$ is also invertible. Its inverse will be $\cfrac{A}{\text{det}(A)}$. Now:

$$
\begin{aligned}
\text{adj}(A)x & =b\\
\text{det}(A)A^{-1}x & =b\\
x & =\cfrac{Ab}{\text{det}(A)}
\end{aligned}
$$


Therefore, $\cfrac{Ab}{\text{det}(A)}$ is the unique solution to the system $\text{adj}(A)x=b$.
