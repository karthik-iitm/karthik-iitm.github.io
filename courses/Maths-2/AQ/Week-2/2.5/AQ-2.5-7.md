---
title: Question-7
pagetitle: Question-7
---

Consider the three elementary row operations:

**Type-1:** Interchanging two rows.

**Type-2**: Multiplying a row by a non-zero constant.

**Type-3**: Adding a scalar multiple of a row to another row.

For each statement below, prove it if it is correct and provide a counterexample if it isn't.

1.  If a matrix $A$ can be obtained from **$B$** by a finite number of row operations, then $B$ can be obtained from $A$ by a finite number of row operations.

2.  The reduced row echelon form of a matrix cannot be the identity matrix.

3.  An upper triangular matrix with all diagonal elements equal to $1$ is in row echelon form.

4.  The identity matrix is in reduced row echelon form.

5.  The reduced row echelon form of a scalar matrix (other than identity) can be obtained by applying only operations of type 1.

6.  The reduced row echelon form of a diagonal matrix (other than identity) can be obtained by applying only operations of type-2.

------------------------------------------------------------------------

\(1\) All row operations are reversible. Let us call the matrix $A_{1}$ before the operation and let $A_{2}$ be the matrix after performing the operation.

**Type-1**: If $R_{1}$ and $R_{2}$ are interchanged in $A_{1}$, we can perform this operation on $A_{2}$ to get back the original matrix $A_{1}$.

**Type-2:** If $R_{1}$ of $A_{1}$ scaled by a non-zero constant $c$, we can scale $R_{1}$ of $A_{2}$ by $\frac{1}{c}$ to get back the original matrix $A_{1}$.

**Type-3**: If $R_{1}$ of $A_{1}$ is replaced by $R_{1}+R_{2}$, we can replace $R_{1}$ of $A_{2}$ by $R_{1}-R_{2}$ to get back the original matrix $A_{1}$.

\(2\) This is incorrect. The RREF of a matrix can be the identity matrix. The identity matrix is itself a trivial example. Every invertible matrix has the identity matrix as its RREF.

\(3\) This is true. As a concrete example, consider a $3\times3$ matrix. All the entries not filled below can take arbitrary values:

$$
\begin{bmatrix}1\\
0 & 1\\
0 & 0 & 1
\end{bmatrix}
$$


\(4\) Yes, the identity matrix is indeed in reduced row echelon form.

\(5\) A non-zero scalar matrix is of the form given below ($c\neq0$):

$$
cI=\begin{bmatrix}c & 0 & 0\\
0 & c & 0\\
0 & 0 & c
\end{bmatrix}
$$


To get its RREF, we need type-2 operation of scaling each row by the constant $\frac{1}{c}$. Type-1 operation is going to be of no use here.

\(6\) To reduce a diagonal matrix to its RREF, we may need both type-1 and type-2 operations. This is especially the case if there are any zero entries on the diagonal. For instance:

$$
\begin{bmatrix}1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 1
\end{bmatrix}
$$


We need to perform $R_{2}\leftrightarrow R_{3}$ to convert the above matrix into its RREF.
