---
title: Question-8
pagetitle: Question-8
---

Find the adjugate of a general $3\times3$ diagonal matrix, say $D$. If $D=\text{adj}(D)$, what can you say about $D$?

------------------------------------------------------------------------

Let $D=\begin{bmatrix}a & 0 & 0\\
0 & b & 0\\
0 & 0 & c
\end{bmatrix}$. The cofactor matrix is given by:

$$
\begin{aligned}
C & =\begin{bmatrix}bc & 0 & 0\\
0 & ca & 0\\
0 & 0 & ab
\end{bmatrix}
\end{aligned}
$$


We see that the cofactor matrix is also diagonal. The adjugate is equal to the transpose of the cofactor matrix. Since $C$ is diagonal, $\text{adj}(D)=C$.

If $D=\text{adj}(D)$, we have:

$$
\begin{aligned}
a & =bc\\
b & =ca\\
c & =ab
\end{aligned}
$$


If any one of $a,b,c$ is zero, then all three are zero. So we can safely assume that $a,b,c\neq0$. Plugging the first equation into the second:

$$
\begin{aligned}
b & =ca\\
 & =bc^{2}\\
b(c^{2}-1) & =0\\
c & =\pm1
\end{aligned}
$$


By a similar argument, we get $a=\pm1$ and $b=\pm1$. We get the following solutions for $(a,b,c)$:

$$
\begin{aligned}
(1,1,1)\\
(1,-1,-1),(-1,1,-1),(-1,-1,1)
\end{aligned}
$$

