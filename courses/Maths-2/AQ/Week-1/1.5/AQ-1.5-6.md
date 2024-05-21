---
title: Question-6
pagetitle: Question-6
---

Let $A,B,C$ be three matrices of order $3$. Comment on the truth value of the following statements:

1.  $\text{det}(ABC)=\text{det}(A)\text{det}(B)\text{det}(C)$

2.  $\text{det}\left(A^{3}\right)=\left(\text{det}(A)\right)^{3}$

3.  $\text{det}(A+B+C)=\text{det}(A)+\text{det}(B)+\text{det}(C)$

4.  $\text{det}\left(AB^{T}\right)=\text{det}(A)\text{det}(B)$

------------------------------------------------------------------------

\(1\) We have:

$$
\begin{aligned}
\text{det}(ABC) & =\text{det}((AB)C)\\
 & =\text{det}(AB)\text{det}(C)\\
 & =\text{det}(A)\text{det}(B)\text{det}(C)
\end{aligned}
$$


\(2\) Using the previous result and setting $A=B=C$ shows that $\text{det}(A^{3})=\text{det}(A)^{3}$.

\(3\) This is not true. Here is a counter-example:

$$
\begin{aligned}
A=B=C= & I\\
\implies A+B+C & =3I\\
\implies\text{det}(A+B+C) & =27\\
\implies\text{det}(A)+\text{det}(B)+\text{det}(C) & =3
\end{aligned}
$$


\(4\) This result is true.

$$
\begin{aligned}
\text{det}(AB^{T}) & =\text{det}(A)\text{det}(B^{T})=\text{det}(A)\text{det}(B)
\end{aligned}
$$

