---
title: Question-10
pagetitle: Question-10
---

Let $A=\begin{bmatrix}-1 & 2\\
-4 & 7
\end{bmatrix}$ and $A^{2}-\alpha A+I=0$ for some $\alpha\in\mathbb{R}$. Find the value of $\alpha$.

------------------------------------------------------------------------

We have:

$$
A^{2}=\begin{bmatrix}-1 & 2\\
-4 & 7
\end{bmatrix}\begin{bmatrix}-1 & 2\\
-4 & 7
\end{bmatrix}=\begin{bmatrix}-7 & 12\\
-24 & 41
\end{bmatrix}
$$


Now:

$$
\begin{aligned}
A^{2}-\alpha A+I & =\begin{bmatrix}-7 & 12\\
-24 & 41
\end{bmatrix}-\alpha\begin{bmatrix}-1 & 2\\
-4 & 7
\end{bmatrix}+\begin{bmatrix}1 & 0\\
0 & 1
\end{bmatrix}\\
\\ & =\begin{bmatrix}-7+\alpha+1 & 12-2\alpha\\
-24+4\alpha & 41-7\alpha+1
\end{bmatrix}\\
\\ & =\begin{bmatrix}0 & 0\\
0 & 0
\end{bmatrix}
\end{aligned}
$$


We can now see that $\boxed{\alpha=6}$.
