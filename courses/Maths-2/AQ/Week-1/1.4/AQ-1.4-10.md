---
title: Question-10
pagetitle: Question-10
---

Find the determinant of the matrix given below:

$$
\begin{bmatrix}a & b & c\\
b & c & a\\
c & a & b
\end{bmatrix}
$$


------------------------------------------------------------------------

$$
\begin{aligned}
\begin{vmatrix}a & b & c\\
b & c & a\\
c & a & b
\end{vmatrix} & =\begin{vmatrix}a+b+c & a+b+c & a+b+c\\
b & c & a\\
c & a & b
\end{vmatrix}\\
\\ & =(a+b+c)\begin{vmatrix}1 & 1 & 1\\
b & c & a\\
c & a & b
\end{vmatrix}\\
\\ & =(a+b+c)\begin{vmatrix}1 & 0 & 0\\
b & c-b & a-b\\
c & a-c & b-c
\end{vmatrix}\\
\\ & =(a+b+c)[-(b-c)^{2}-(a-b)(a-c)]\\
\\ & =(a+b+c)[-b^{2}-c^{2}+2bc-a^{2}+ac+ab-bc]\\
\\ & =(a+b+c)[ab+bc+ca-a^{2}-b^{2}-c^{2}]
\end{aligned}
$$


These are the operations:

-   First we start with $R_{1}\rightarrow R_{1}+R_{2}+R_{3}$.

-   This produces a common factor $(a+b+c)$ in the first row which we are moving out.

-   We now move to the columns. We perform $C_{2}\rightarrow C_{2}-C_{1}$ followed by $C_{3}\rightarrow C_{3}-C_{1}$.

-   We now have enough number of zeros and we expand the determinant along the first row.

-   The rest is just basic algebra.
