---
title: Question-8
pagetitle: Question-8
---

Find out the determinant of the following matrix:

$$
\begin{bmatrix}1 & a & bc\\
1 & b & ca\\
1 & c & ab
\end{bmatrix}
$$


------------------------------------------------------------------------

$R_{2}\rightarrow R_{2}-R_{1}$

$$
\begin{bmatrix}1 & a & bc\\
0 & b-a & c(a-b)\\
1 & c & ab
\end{bmatrix}
$$


$R_{3}\rightarrow R_{3}-R_{1}$

$$
\begin{bmatrix}1 & a & bc\\
0 & b-a & c(a-b)\\
0 & c-a & b(a-c)
\end{bmatrix}
$$


Both these operations leave the determinant unchanged. We can now expand the determinant along the first column:

$$
\begin{aligned}
\begin{vmatrix}1 & a & bc\\
1 & b & ca\\
1 & c & ab
\end{vmatrix} & =b(b-a)(a-c)-c(c-a)(a-b)\\
\\ & =(a-b)(c-a)(b-c)\\
\\ & =(a-b)(b-c)(c-a)
\end{aligned}
$$

