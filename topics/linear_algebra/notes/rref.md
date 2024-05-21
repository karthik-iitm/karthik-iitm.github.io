---
title: RREF is unique
pagetitle: RREF is unique
---

The reduced row echelon form of a matrix is unique. The proof requires an observation about the row spaces of a matrix and its RREF.

## Row operations preserve row space

If a matrix $A$ has $n$ rows, say $r_{1},\cdots,r_{n}$, then the span of the rows is the set of all possible linear combinations of the rows and is called the row space of the matrix:

$$
\text{span}\{r_{1},\cdots,r_{n}\}
$$


Swapping two rows or scaling a row by a non-zero constant clearly preserves this span. Let us now try to add one row to the other, the third type of elementary operation. Without loss of generality, let us say we add the second row to the first. The span becomes:

$$
\text{span}\{r_{1}+r_{2},r_{2},\cdots,r_{n}\}
$$


We need to show the following:

$$
\text{span}\{r_{1}+r_{2},r_{2},\cdots,r_{n}\}=\text{span}\{r_{1},\cdots,r_{n}\}
$$


We will denote these two sets $R_{1}$ and $R_{2}$. Let us take any element $R_{1}$:

$$
\begin{aligned}
a_{1}(r_{1}+r_{2})+a_{2}r_{2}+\cdots+a_{n}r_{n} & =a_{1}r_{1}+(a_{1}+a_{2})r_{2}+a_{3}r_{3}+\cdots+a_{n}r_{n}
\end{aligned}
$$


We see that this element is present in $R_{2}$ as well. Therefore:

$$
\text{span}\{r_{1}+r_{2},r_{2},\cdots,r_{n}\}\subset\text{span}\{r_{1},\cdots,r_{n}\}
$$


To go the other way, take any element in $R_{2}$:

$$
\begin{aligned}
a_{1}r_{1}+\cdots+a_{n}r_{n} & =a_{1}(r_{1}+r_{2})+(a_{2}-a_{1})r_{2}+a_{3}r_{3}+\cdots+a_{n}r_{n}
\end{aligned}
$$


We see that this element is there in $R_{1}$ as well. Therefore:

$$
\text{span}\{r_{1},\cdots,r_{n}\}\subset\text{span}\{r_{1}+r_{2},r_{2},\cdots,r_{n}\}
$$


Thus, all elementary operations preserve the span of the rows of the original matrix. An important consequence of this is that the row space of a matrix is equal to that of its RREF.

## Non-zero rows in RREF form a basis for row space

A concrete example will be used below, but it is quite easy to generalize it:

$$
\begin{bmatrix}\boldsymbol{1} &  & 0 &  & 0\\
0 & 0 & \boldsymbol{1} &  & 0\\
0 & 0 & 0 & 0 & \boldsymbol{1}\\
0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0
\end{bmatrix}
$$


All entries that are not filled are irrelevant to the discussion and could take arbitrary real values. Notice that the non-zero rows are linearly independent. If we call the non-zero rows $r_{1},r_{2},r_{3}$, we have:

$$
ar_{1}+br_{2}+cr_{3}=0\implies a=b=c=0
$$


We already know that row operations preserve the span of the rows. Hence, the non-zero rows form a basis for the row space.

## Proof

Assume that $R_{1}$ and $R_{2}$ are two RREFs for the matrix $A$. From the observations made so far, $R_{1}$ and $R_{2}$ have the same number of non-zero rows and the span of the non-zero rows of the two matrices are equal, each being equal to the row space of $A$.

The pivot columns in $R_{1}$ and $R_{2}$ have to be identical, both in number and position. The number of pivots is equal to the number of non-zero rows, which is the dimension of the row space. So this can't be different in the RREFs. This leaves us with the possibility of the position of the pivot columns being different. Let us look at a potential contradiction to this:

$$
\begin{aligned}
\begin{bmatrix}\boldsymbol{1} &  & 0 &  & 0\\
0 & 0 & \boldsymbol{1} &  & 0\\
0 & 0 & 0 & 0 & \boldsymbol{1}\\
0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0
\end{bmatrix} &  & \begin{bmatrix}\boldsymbol{1} & 0 &  &  & 0\\
0 & \boldsymbol{1} & \boldsymbol{} &  & 0\\
0 & 0 & 0 & 0 & \boldsymbol{1}\\
0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0
\end{bmatrix}
\end{aligned}
$$


Assume that these two matrices are two distinct RREFs for some matrix $A$ with the same number of pivot columns, but at different locations. We know that the row space has dimension $3$, so any set of four vectors in the row space are dependent. If we take the first three rows from the matrix on the left and the second row from the matrix on the right, these four vectors make a linearly independent subset of the row space, which is a contradiction. So the position of the pivot columns have to be the same.

We are now back to two RREFs whose general outline looks like this:

$$
\begin{bmatrix}\boldsymbol{1} &  & 0 &  & 0\\
0 & 0 & \boldsymbol{1} &  & 0\\
0 & 0 & 0 & 0 & \boldsymbol{1}\\
0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0
\end{bmatrix}
$$


Once the pivot columns are fixed for both the RREFs consider the last non-zero row, $r_{3}^{(2)}$, from the second RREF. This should be expressible as a linear combination of the non-zero rows of the first RREF:

$$
r_{3}^{(2)}=a_{1}r_{1}^{(1)}+a_{2}r_{2}^{(1)}+a_{3}r_{3}^{(1)}
$$


We immediately see that $a_{1}=a_{2}=0$. $a_{3}$ is forced to be $1$ as the pivots have to agree. Thus the last non-zero row is identical in both RREFs. We can now repeat the process for the second non-zero row:

$$
r_{2}^{(2)}=a_{1}r_{1}^{(1)}+a_{2}r_{2}^{(1)}+a_{3}r_{3}^{(1)}
$$


$a_{1}=0$, $a_{2}=1$ and $a_{3}=0$. So the last two rows of the two RREFs are the same. A similar argument shows that all non-zero rows in the two RREFs are the same, which means that the two RREFs are one and the same.
