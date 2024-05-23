---
order: 1
title: Introduction
pagetitle: Introduction
---

::: {.callout-note title="Question"}
Why should we study linear algebra in a course on data science?
:::



## Data

The simplest answer to this question is that we choose vectors and matrices to represent data. Let us take a simple example of data coming from the housing industry. Every house in a locality has the following **features** or attributes associated with it:

- latitude
- longitude
- age
- number of rooms
- area
- distance from nearest school

The selling price of a house depends on these features. For example, a house with more number of rooms may have a higher selling price and a house that is very far from the nearest school may have a lower selling price. A natural question that we might want to ask is this:

::: {.callout-note title="Question"}
Given the features of a house can we train a machine to predict its selling price?
:::

This is called a **regression problem**: given a set of features, map it to a real number. In our example problem, the real number which we wish to predict is the selling price.



## Vectors

Let us take a concrete example of a single house. Since each house represents one instance of the data we are working with, we will call it a **data-point**:

| Name                         | Values |
| ---------------------------- | ------: |
| latitude                     | 12.9   |
| longitude                    | 80.2   |
| age                          | 3      |
| number of rooms              | 2      |
| area                         | 1000   |
| distance from nearest school | 3      |
: A Data-Point {.striped .hover}

Latitude and longitude are in degrees, age is in years, area is in square feet, distance is in kilometers, selling price is in lakhs of rupees. But none of these "units" really matter for an ML algorithm: it is going to abstract out the details and look at this as a column of numbers, which is nothing but a vector:

$$
\begin{equation*}
\begin{bmatrix}
12.9\\
80.2\\
3\\
2\\
1000\\
3
\end{bmatrix}
\end{equation*}
$$

The selling price is not included as an element in the vector as that is usually unknown to us. This unknown quantity which we have to estimate or predict is called the **target**.

::: {.callout-note title="Remarks"}
1. Vectors are usually represented as column vectors or $d \times 1$ matrices.
2. An alternative terminology for features/target is independent/dependent variables. The term independent variables stands for the features and dependent variable for the label. You can think about the dependent variable as a function of the independent variables.
:::


## Matrices

We cannot learn anything substantial from looking at the data of one house. We have to look at the data of multiple houses. That will give us an idea of the general picture. Rather than look at each vector in isolation, we can arrange them in a tabular form. For now, we only focus on the features:


| house number | latitude | longitude | age  | rooms | area | distance | selling price |
| :-------: | :--------: | :---------: | :----: | :-----: | :------: | :--------: | :-------: |
| 1            | 12.9     | 80.2      | 3    | 2     | 1000 | 3        | 40            |
| $\cdots$     |          |           |      |       |      |          |               |
| 50           | 14.3     | 75.9      | 30   | 2     | 1200 | 5        | 20            |
| $\cdots$     |          |           |      |       |      |          |               |
| 100          | 20.8     | 90.5      | 1    | 3     | 1500 | 2        | 35            |

This data for $100$ houses is nothing but a $100\times 6$ matrix:

$$
\begin{equation*}
\begin{bmatrix}
12.9 & 80.2 & 3 & 2 & 1000 & 3\\
\vdots  & \vdots  & \vdots  & \vdots  & \vdots  & \vdots \\
14.3 & 75.9 & 30 & 2 & 1200 & 5\\
\vdots  & \vdots  & \vdots  & \vdots  & \vdots  & \vdots \\
20.8 & 90.5 & 1 & 3 & 1500 & 2
\end{bmatrix}
\end{equation*}
$$

Each row of this matrix corresponds to one data-point. In general, if a dataset has $d$ features and $n$ data-points, it is represented as a $n \times d$ or a $d \times n$ **data-matrix** or design matrix.

::: {.callout-note}
If you find yourself lost when working with matrices, remember that a matrix is a way to represent a collection of data-points (dataset).
:::

## Summary

Data is represented as vectors and matrices. If we wish to extract insights from data, we need to know how to manipulate vectors and matrices. Therefore, we need to have a reasonable understanding of linear algebra — the study of vectors and matrices — if we wish to understand how ML algorithms work.