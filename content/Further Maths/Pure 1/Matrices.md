## Overview
A **matrix** is an array of numbers:
$$
\left(\begin{smallmatrix}5 & 1 & -2 \\ 6 & -2 &4\end{smallmatrix}\right)
$$
This matrix has 2 rows and 3 columns. 
An $m \times n$ matrix has $m$ rows and $n$ columns.
A **square** matrix with dimensions $m \times n$ has $m = n$.

A **zero** matrix, or **null** matrix, is denoted by $\boldsymbol{Z}$ and has every element equal to zero:
$$
\left(\begin{smallmatrix}0 & 0 \\ 0 & 0\end{smallmatrix}\right)
$$
The **identity** matrix has a 1 for each element of the main diagonal (top left to bottom right, and a zero everywhere else). It is denoted by $\boldsymbol{I}$.
$$
\left(\begin{smallmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 &1\end{smallmatrix}\right)
$$
The element in the $i$th row and $j$th column of matrix $\boldsymbol{A}$ is $a_{i,j}$.

The **transpose** of a matrix $\boldsymbol{A}$ is $\boldsymbol{A}^\mathrm{T}$, such that the rows of $\boldsymbol{A}^\mathrm{T}$ are the columns of $\boldsymbol{A}$. The transpose can be obtained by reflecting the elements along the main diagonal
$$
\begin{split}
A &= \left(\begin{smallmatrix}5 & 1 & -2 \\ 6 & -3 &4\end{smallmatrix}\right)
\\ A^\mathrm{T} &= \left(\begin{smallmatrix}5  & 6 \\ 1 & -3 \\ -2 & 4\end{smallmatrix}\right)
\end{split}
$$

When **adding** (or **subtracting**) matrices, corresponding elements are added or subtracted. Matrices must be of the same dimension to be added or subtracted.
$$
\left(\begin{smallmatrix}5 & 1 \\ -3 &4\end{smallmatrix}\right) 
+ \left(\begin{smallmatrix}1 & -2 \\ -3 &5\end{smallmatrix}\right) 
= \left(\begin{smallmatrix}6 & -1 \\ -6 &9\end{smallmatrix}\right)
$$
When a matrix is **multiplied** by a **scalar**, each element is multiplied by the scalar.
$$
4\left(\begin{smallmatrix}2 & 3 \\ -1 &5\end{smallmatrix}\right) = 
\left(\begin{smallmatrix}8 & 12 \\ -4 &20\end{smallmatrix}\right)
$$

## Matrix Multiplication
Two matrices $\boldsymbol{A}$ and $\boldsymbol{B}$ with dimensions $m \times n$ and $n \times p$ can be multiplied. The result is an $m \times p$ matrix. If the matrices do not have the right dimensions to be multiplied together, they are not **conformable**.

To find the element in row $i$ and column $j$ of the resulting matrix $\boldsymbol{C}$:
- Take row $i$ of $\boldsymbol{A}$ and column $j$ of $\boldsymbol{B}$.
- Multiply each pair of corresponding values and add the products together.

For $\boldsymbol{A} = \left(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix}\right)$ and $\boldsymbol{B} = \left(\begin{smallmatrix}e & f \\ g & h\end{smallmatrix}\right)$:
$$
\boldsymbol{AB} = \boldsymbol{B} = \left(\begin{smallmatrix}ae + bg & af + bh \\ ce + dg & cf + dh\end{smallmatrix}\right)
$$

$\boldsymbol{A}^2$ indicates a matrix $\boldsymbol{A}$ multiplied by itself. Similarly, $\boldsymbol{A}^3 = \boldsymbol{AAA}$, etc.

Matrix multiplication is **generally associative**; that is, a multiple product $\boldsymbol{ABC}$ can be calculated as $(\boldsymbol{AB})\boldsymbol{C}$ or $\boldsymbol{A}(\boldsymbol{BC})$ with the same result. 

Matrix multiplication is **not generally commutative**; that is, $\boldsymbol{AB}$ does not generally equal $\boldsymbol{BA}$. However, some matrices will **commute**, which is true when $\boldsymbol{AB} = \boldsymbol{BA}$.

An [[Groups#Definitions|identity]] is an operand that produces no change for a given operation. 
- For matrix addition, the zero matrix is the identity, because $\boldsymbol{Z} + \boldsymbol{A} = \boldsymbol{A} + \boldsymbol{Z} = \boldsymbol{A}$
- For matrix multiplication, the identity matrix is the identity, because $\boldsymbol{I}\boldsymbol{A} = \boldsymbol{A}\boldsymbol{I} = \boldsymbol{A}$

A matrix can be thought of as a function that **transforms** a point. An **inverse** matrix can therefore be thought of as an inverse function / transformation that 'undoes' the matrix multiplication.

## Determinant and inverse of a 2x2 matrix
The **determinant** of a matrix determines where it has an inverse. The determinant of a matrix $\boldsymbol{A} = \left(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix}\right)$ is $\det(\boldsymbol{A}) = |\boldsymbol{A}| = ad-bc$

If $\det(\boldsymbol{A}) = 0$, then $\boldsymbol{A}$ is a **singular** matrix, and does not have an inverse.
If $\det(\boldsymbol{A}) \neq 0$, then $\boldsymbol{A}$ is a **non-singular** matrix, and does have an inverse.

Properties of the determinant include:
- $\det(\boldsymbol{AB}) = \det(\boldsymbol{BA}) = \det(\boldsymbol{A}) \times \det(\boldsymbol{B})$
- $\det(k\boldsymbol{A}) = k^2\det(\boldsymbol{A})$


The **inverse** of a $\boldsymbol{A} = \left(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix}\right)$ is denoted as $\boldsymbol{A}^{-1}$ and has the property that:
$$
\boldsymbol{A}\boldsymbol{A}^{-1} = \boldsymbol{A}^{-1}\boldsymbol{A} = \boldsymbol{I}
$$
The inverse of $\boldsymbol{A}$ where $\det{\boldsymbol{A}} \neq 0$ is:
$$
\boldsymbol{A}^{-1} = \frac{1}{\det{\boldsymbol{A}}}\left(\begin{smallmatrix}d & -b \\ -c & a\end{smallmatrix}\right)
$$

#### Applications
The inverse matrix is used to 'undo' matrix multiplication. Matrix multiplication is not generally commutative, so care must be taken to multiply both sides of an equation on the right side.

For example, to find $\boldsymbol{X}$:
$$
\begin{split}
\boldsymbol{AX} &= \boldsymbol{B} \\
\boldsymbol{A^{-1}AX} &= \boldsymbol{A}^{-1}\boldsymbol{B} \\
\boldsymbol{IX} &= \boldsymbol{A}^{-1}\boldsymbol{B} \\
\boldsymbol{X} &= \boldsymbol{A}^{-1}\boldsymbol{B}
\end{split}
$$

The **inverse of a product** consists of the product of the inverses of the individual matrices, but in the **opposite order**[^1]:
$$
(\boldsymbol{ABC})^{-1} = \boldsymbol{C}^{-1}\boldsymbol{B}^{-1}\boldsymbol{A}^{-1}
$$

## Determinant and inverse of a 3x3 matrix
The **determinant** of a $3 \times 3$ matrix is:
$$
\det\left(\begin{smallmatrix}a & b & c \\ d & e & f \\ g & h & i\end{smallmatrix}\right)
= a \left|\begin{smallmatrix}e & f \\ h & i\end{smallmatrix}\right|
- b \left|\begin{smallmatrix}d & f \\ g & i\end{smallmatrix}\right|
+ c \left|\begin{smallmatrix}d & e \\ g & h\end{smallmatrix}\right|
$$
- Each element in a row or column is multiplied by the determinant of the $2 \times 2$ matrix obtained by removing that element's row and column.
- The middle term has a negative sign (according to the alternating sign matrix below).
Any row or column can be used to find the determinant (this is helpful where there are many 0s). 

The **inverse** of a $3 \times 3$ matrix $\boldsymbol{A}$ is:
$$
\boldsymbol{A}^{-1} = \frac{1}{\det{\boldsymbol{A}}}\boldsymbol{C}^T
$$
Where $\boldsymbol{C}$ is the **matrix of cofactors**, found by:
- Deleting the row and column for each element.
- Finding the determinant of the remaining $2 \times 2$ matrix.
- Determining the sign according to the alternating sign matrix $\left(\begin{smallmatrix} + & - & + \\ - & + & - \\ + & - & +\end{smallmatrix}\right)$.

Another method to find the inverse of a $3 \times 3$ matrix is described [[2 - Vectors#Application to 3x3 matrix inverse|in Further Vectors]].

[^1]:**Footnote on inverse of a product of matrices**
	The reason $(\boldsymbol{ABC})^{-1} = \boldsymbol{C}^{-1}\boldsymbol{B}^{-1}\boldsymbol{A}^{-1}$ is because matrix multiplication can be understood as [function composition](https://www.3blue1brown.com/lessons/matrix-multiplication#:~:text=two%20successive%20ones.-,Composition%20is%20Multiplication,-Here%E2%80%99s%20one%20way) - applying one function then the next. With function composition like $f(g(x))$, we read the order of functions from right to left.
