---
title: Question-2
pagetitle: Question-2
---

Identify which of the following are in row echelon form and which are in reduced row echelon form. Also identify the pivots along the way.

$$
\begin{aligned}
A & =\begin{bmatrix}0 & 1 & 0\\
1 & 0 & 1\\
0 & 1 & 0
\end{bmatrix} & B & =\begin{bmatrix}-1 & 2 & 0\\
0 & 0 & 1\\
0 & 0 & 0
\end{bmatrix} & C & =\begin{bmatrix}1 & 2 & 0\\
0 & 0 & 1\\
0 & 0 & 0
\end{bmatrix}\\
\\D & =\begin{bmatrix}0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{bmatrix} & E & =\begin{bmatrix}0 & 1 & 3\\
0 & 1 & 1\\
0 & 0 & 1
\end{bmatrix} & F & =\begin{bmatrix}1 & 1 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}\\
\\G & =\begin{bmatrix}0 & 1 & 3 & -1\\
0 & 0 & 1 & 1\\
0 & 0 & 0 & 1
\end{bmatrix} & H & =\begin{bmatrix}0 & 0 & 0\\
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0
\end{bmatrix} & I & =\begin{bmatrix}1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}\\
\\J & =\begin{bmatrix}0 & 1 & 0\\
0 & 0 & 1\\
0 & 0 & 0\\
1 & 0 & 0
\end{bmatrix} & K & =\begin{bmatrix}1 & 0 & 0 & -1\\
0 & 1 & 1 & 0\\
0 & 0 & 0 & 0
\end{bmatrix} & L & =\begin{bmatrix}1 & 0 & -1\\
0 & 1 & 1
\end{bmatrix}
\end{aligned}
$$


------------------------------------------------------------------------

## Pivot

The pivot is the first non-zero entry in a row. As an example, the numbers marked in bold are the pivots:

$$
\begin{bmatrix}\boldsymbol{1} & 0 & -1 & 2\\
0 & \boldsymbol{2} & 1 & 0\\
0 & 0 & 0 & \boldsymbol{-1}\\
0 & 0 & 0 & 0
\end{bmatrix}
$$


Each non-zero row has a pivot. A zero row doesn't have a pivot. The pivot is also called the leading entry.

## REF

For a matrix to be in row echelon form, the following conditions have to be satisfied:

-   The pivot in any row should be to the right of the pivot in the previous row.

-   The pivot is $1$. \[this condition is not binding according to some authors, but it is binding for this course\]

-   All zero rows should come at the end.

## RREF

For a matrix to be in reduced row echelon form, the following conditions have to be satisfied. A column that contains a pivot is called a pivot column:

-   The matrix should be in row echelon form.

-   The pivot should be the only non-zero entry in a pivot column.

## Solutions

$$
A=\begin{bmatrix}0 & \boldsymbol{1} & 0\\
\boldsymbol{1} & 0 & 1\\
0 & \boldsymbol{1} & 0
\end{bmatrix}
$$


$A$ is not in REF. The pivot in the second row is to the left of the pivot in the first row.

$$
B=\begin{bmatrix}\boldsymbol{-1} & 2 & 0\\
0 & 0 & \boldsymbol{1}\\
0 & 0 & 0
\end{bmatrix}
$$


$B$ is not in REF. The pivot in the first row is $-1$.

$$
C=\begin{bmatrix}\boldsymbol{1} & 2 & 0\\
0 & 0 & \boldsymbol{1}\\
0 & 0 & 0
\end{bmatrix}$$ $C$ is in RREF. The first and last columns are pivot columns.

$$
D=\begin{bmatrix}0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{bmatrix}
$$


$D$ is in RREF. It doesn't have any pivots though.

$$
E=\begin{bmatrix}0 & \boldsymbol{1} & 3\\
0 & \boldsymbol{1} & 1\\
0 & 0 & \boldsymbol{1}
\end{bmatrix}$$ $E$ is not in REF. The pivot in the second row is below the pivot in the first row.

$$
F=\begin{bmatrix}\boldsymbol{1} & 1 & 0\\
0 & \boldsymbol{1} & 0\\
0 & 0 & \boldsymbol{1}
\end{bmatrix}
$$


$F$ is in REF. It is not in RREF as the second pivot column has two non-zero entries.

$$
G=\begin{bmatrix}0 & \boldsymbol{1} & 3 & -1\\
0 & 0 & \boldsymbol{1} & 1\\
0 & 0 & 0 & \boldsymbol{1}
\end{bmatrix}
$$


$G$ is in REF. It is not in RREF since the third and fourth pivot columns have other non-zero entries.

$$
H=\begin{bmatrix}0 & 0 & 0\\
\boldsymbol{1} & 0 & 0\\
0 & \boldsymbol{1} & 0\\
0 & 0 & 0
\end{bmatrix}
$$


$H$ is not in REF. The first row is a zero row and for a matrix to be in REF, all zero rows should come at the end.

$$
I=\begin{bmatrix}\boldsymbol{1} & 0 & 0\\
0 & \boldsymbol{1} & 0\\
0 & 0 & \boldsymbol{1}
\end{bmatrix}$$ $I$ is in RREF.

$$
J=\begin{bmatrix}0 & \boldsymbol{1} & 0\\
0 & 0 & \boldsymbol{1}\\
0 & 0 & 0\\
\boldsymbol{1} & 0 & 0
\end{bmatrix}
$$


$J$ is not in REF. There is a zero row above a non-zero row.

$$
K=\begin{bmatrix}\boldsymbol{1} & 0 & 0 & -1\\
0 & \boldsymbol{1} & 1 & 0\\
0 & 0 & 0 & 0
\end{bmatrix}
$$


$K$ is in RREF. Do not be misled by the $-1$ that appears at the end of the first row or the $1$ that appears after the pivot in the second row.

$$
L=\begin{bmatrix}\boldsymbol{1} & 0 & -1\\
0 & \boldsymbol{1} & 1
\end{bmatrix}
$$


$L$ is in RREF.
