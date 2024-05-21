---
title: Question-8
pagetitle: Question-8
---

-   Do there exist square matrices $A$ and $B$ of order two such that $AB=BA$?

-   Does there exist a square matrix $A$ of order two such that $A^{2}=A$?

-   Does there exist a square matrix $A$ of order two such that $A^{2}+A+I=0$?

------------------------------------------------------------------------

## $AB=BA$

In general, matrix multiplication is not commutative. That is, if $A$ and $B$ are two matrices, then $AB\neq BA$. However, not all pairs of matrices are like this.

-   A simple but trivial example is the case of $A=B$.

-   Another example is the case of $B=I$, since $AI=IA=A$.

-   Two diagonal matrices always commute. This is because the product of two diagonal matrices is another diagonal matrix whose entries are the product of the corresponding diagonal entries:

$$
\begin{aligned}
D_{1} & =\begin{bmatrix}2 & 0\\
0 & 3
\end{bmatrix}\\
D_{2} & =\begin{bmatrix}3 & 0\\
0 & 5
\end{bmatrix}\\
D_{1}D_{2} & =D_{2}D_{1}=\begin{bmatrix}6 & 0\\
0 & 15
\end{bmatrix}
\end{aligned}
$$


## $A^{2}=A$

In the case of $A^{2}=A$, we can see that $A=I$ would satisfy $A^{2}=A$. Interestingly, $A=-I$ would not satisfy $A^{2}=A$. Compare this to the single variable equation $a^{2}=a$, in which $a=-1$ is also a solution. To construct a non-trivial example, we can take any $2\times2$ matrix $A=\begin{bmatrix}a & b\\
c & d
\end{bmatrix}$

$$
\begin{aligned}
\begin{bmatrix}a & b\\
c & d
\end{bmatrix}\begin{bmatrix}a & b\\
c & d
\end{bmatrix} & =\begin{bmatrix}a^{2}+bc & ab+bd\\
ac+cd & bc+d^{2}
\end{bmatrix}\\
 & =\begin{bmatrix}a & b\\
c & d
\end{bmatrix}
\end{aligned}
$$


We now have:

$$
\begin{aligned}
a^{2}+bc & =a\\
b(a+d) & =b\\
c(a+d) & =c\\
d^{2}+bc & =d
\end{aligned}
$$


One solution can be $a=1,b=2,c=0,d=0$ which gives us the matrix $\begin{bmatrix}1 & 2\\
0 & 0
\end{bmatrix}$. You can verify that $A^{2}=A$ for this matrix.

## $A^{2}+A+I=0$

First consider the corresponding equation in one variable:

$$
a^{2}+a+1=0
$$


This equation does not have any real solutions. Can we expect something similar for the matrix equation? Taking a general matrix, we get:

$$
\begin{aligned}
\begin{bmatrix}a^{2}+bc & ab+bd\\
ac+cd & bc+d^{2}
\end{bmatrix}+\begin{bmatrix}a & b\\
c & d
\end{bmatrix}+\begin{bmatrix}1 & 0\\
0 & 1
\end{bmatrix} & =\begin{bmatrix}a^{2}+bc+a+1 & ab+bd+b\\
ac+cd+c & bc+d^{2}+d+1
\end{bmatrix}
\end{aligned}
$$


Setting this to the zero matrix:

$$
\begin{aligned}
a^{2}+a+1+bc & =0\\
b(a+d+1) & =0\\
c(a+d+1) & =0\\
d^{2}+d+1+bc & =0
\end{aligned}
$$


If $a+d+1\neq0$, then $b=c=0$. This would imply that $a^{2}+a+1=d^{2}+d+1=0$, which is impossible for real numbers $a,d$. Therefore, $a+d+1=0$. Equating the first and last equations, we get:

$$
a^{2}+a+1=d^{2}+d+1\implies(a-d)(a+d+1)=0.
$$


We see that $a+d+1=0$ will take care of the second and third equations. We now take up the first equation:

$$
\begin{aligned}
a^{2}+a+1+bc & =0\\
\left(a+\frac{1}{2}\right)^{2}+\frac{3}{4}+bc & =0\\
\left(a+\frac{1}{2}\right)^{2} & =-\left(\frac{3}{4}+bc\right)
\end{aligned}
$$


We can use this to get one set of values:

$$
a=-\frac{1}{2},b=3,c=-\frac{1}{4},d=-\frac{1}{2}
$$


The resulting matrix is:

$$
\begin{bmatrix}-\frac{1}{2} & 3\\
\\\frac{-1}{4} & -\frac{1}{2}
\end{bmatrix}
$$


We can characterize all possible solutions here. This is left as an exercise to the reader.
