---
title: Question-1
pagetitle: Question-1
---

Consider the following system of linear equations:

$$
\begin{aligned}
-2x_{1}+3x_{2}+x_{3} & =1\\
-x_{1}+x_{3} & =0\\
2x_{2} & =5
\end{aligned}
$$


-   Convert the system into the form $Ax=b$.

-   Solve the system.

------------------------------------------------------------------------

We have:

$$
A=\begin{bmatrix}-2 & 3 & 1\\
-1 & 0 & 1\\
0 & 2 & 0
\end{bmatrix},\,\,\,x=\begin{bmatrix}x_{1}\\
x_{2}\\
x_{3}
\end{bmatrix},\,\,\,b=\begin{bmatrix}1\\
0\\
5
\end{bmatrix}
$$


From the last equation, we see that $x_{2}=\frac{5}{2}$. The second equation shows that $x_{1}=x_{3}$. Using these two facts in equation-(1), we get $x_{1}=x_{3}=3x_{2}-1=\frac{13}{2}$. The solution is unique and is given by $\left(\frac{13}{2},\frac{5}{2},\frac{13}{2}\right)$.
