---
title: Question-9
pagetitle: Question-9
---

What are the consequences of a square matrix being equal to its inverse?

------------------------------------------------------------------------

-   We have $A=A^{-1}$. Multiplying both sides by $A$, we get $A^{2}=I$. This is the first observation.

-   Since $\text{det}(A^{-1})=\frac{1}{\text{det}(A)}$, we have:

$$
\text{det}(A)^{2}=1\implies\text{det}(A)=\pm1
$$


-   $A=\pm I$ are two obvious solutions to $A^{2}=I$. But these two are not the only matrices. Let us quickly construct a non-trivial solution:

$$
\begin{aligned}
A & =\begin{bmatrix}a & b\\
c & d
\end{bmatrix}\\
A^{2} & =\begin{bmatrix}a & b\\
c & d
\end{bmatrix}\begin{bmatrix}a & b\\
c & d
\end{bmatrix}\\
 & =\begin{bmatrix}a^{2}+bc & b(a+d)\\
c(a+d) & d^{2}+bc
\end{bmatrix}\\
 & =\begin{bmatrix}1 & 0\\
0 & 1
\end{bmatrix}
\end{aligned}
$$


We can set $a=1,b=c=0,d=-1$. Thus the matrix $A=\begin{bmatrix}1 & 0\\
0 & -1
\end{bmatrix}$ satisfies $A^{2}=I$. Besides, note that it is its own inverse and its determinant is $-1$.
