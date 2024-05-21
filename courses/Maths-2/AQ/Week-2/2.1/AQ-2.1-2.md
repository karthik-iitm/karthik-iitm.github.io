---
title: Question-2
pagetitle: Question-2
---

Suppose there exist three square matrices $A,D,P$ of order $3$ such that $D=PAP^{-1}$ and $D$ is diagonal. Find a relationship between $|D|$ and $|A|$. If $D=I$, is it necessary that $A$ is also equal to $I$?

------------------------------------------------------------------------

We have:

$$
\begin{aligned}
|D| & =\left|PAP^{-1}\right|\\
 & =|P|\cdot|A|\cdot\left|P^{-1}\right|\\
 & =|P|\cdot|A|\cdot\cfrac{1}{|P|}\\
 & =|A|
\end{aligned}
$$


Thus, the determinants of $A$ and $D$ are equal. We now turn to the second part of the question. If $D=I$, then:

$$
\begin{aligned}
I & =PAP^{-1}\\
P^{-1}IP & =A\\
P^{-1}P & =A\\
I & =A
\end{aligned}
$$


Thus, if $D=I$, then $A=I$.
