---
title: Question-4
pagetitle: Question-4
---

Express the following system in matrix-vector form and solve it:

$$
\begin{aligned}
0x_{1}+x_{2}+0x_{3}+0x_{4} & =1\\
0x_{1}+0x_{2}+0x_{3}+0x_{4} & =1\\
x_{1}+x_{2}+0x_{3}+0x_{4} & =1\\
0x_{1}+0x_{2}+x_{3}+x_{4} & =1
\end{aligned}
$$


------------------------------------------------------------------------

We have:

$$
A=\begin{bmatrix}0 & 1 & 0 & 0\\
0 & 0 & 0 & 0\\
1 & 1 & 0 & 0\\
0 & 0 & 1 & 1
\end{bmatrix},\,\,\,\,x=\begin{bmatrix}x_{1}\\
x_{2}\\
x_{3}\\
x_{4}
\end{bmatrix},\,\,\,\,b=\begin{bmatrix}1\\
1\\
1\\
1
\end{bmatrix}
$$


We note that the second row is a zero row in $A$, but the corresponding component in the vector $b$ is non-zero. Hence, this system doesn't have any solution.
