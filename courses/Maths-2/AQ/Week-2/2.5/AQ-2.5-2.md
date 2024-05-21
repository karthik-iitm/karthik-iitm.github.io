---
title: Question-2
pagetitle: Question-2
---

Comment on the truth value of the following statements:

1.  If two matrices $A$ and **$B$** have the same row echelon form, then $A$ must be equal to $B$.

2.  If two matrices $A$ and **$B$** have the same reduced row echelon form, then $A$ must be equal to $B$.

3.  The row echelon form of a diagonal matrix with non-zero diagonal entries must be the identity matrix.

4.  The reduced row echelon form of a non-zero scalar matrix must be the identity matrix.

------------------------------------------------------------------------

## Row echelon form

The row echelon form of a matrix is not unique. As an example, consider the following matrix:

$$
A_{1}=\begin{bmatrix}1 & 1\\
0 & 2
\end{bmatrix}
$$


Dividing the second row by $2$ turns $A$ into a matrix in row echelon form:

$$
A_{2}=\begin{bmatrix}1 & 1\\
0 & 1
\end{bmatrix}
$$


But this is not the only one possible. For instance, we could do a perfectly valid but useless transformation of adding the second row to the first row to give:

$$
A_{3}=\begin{bmatrix}1 & 2\\
0 & 1
\end{bmatrix}
$$


$A_{3}$ is still in row echelon form. We could turn around and say that both $A_{3}$ and $A_{1}$ can be reduced to $A_{2}$. Thus, two unequal matrices could share a common row echelon form.

## Reduced row echelon form

The reduced row echelon form of a matrix is unique. The proof is slightly involved and requires some concepts that are yet to be introduced. The interested reader can take a look at Topics/Linear Algebra/RREF in the sidebar.

------------------------------------------------------------------------

For a diagonal matrix with non-zero diagonal entries, we can divide each row by the corresponding entry and reduce it to the identity matrix. For a non-zero scalar matrix, we can divide each row by the non-zero scalar associated with it to get the identity matrix. We see that the RREF of both matrices is the identity.

Note that both matrices discussed here are invertible. In fact, it can be shown that the RREF of any invertible matrix is the identity matrix.
