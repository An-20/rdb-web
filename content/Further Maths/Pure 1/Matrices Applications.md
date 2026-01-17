## Linear Simultaneous Equations
A system of **linear equations** can be written as a matrix multiplication equation. For example:
$$
\begin{split}
3x + 4y - z = 5
\\ 2x + y - 2z = -12
\\ x + 3z = 4
\\ \pmatrix{3 & 4 & -1 \\ 2 & 1 & -2 \\ 1 & 0 & 3}\pmatrix{x\\y\\z} = \pmatrix{5\\-12\\4}
\end{split}
$$
The matrix equation can then be solved.

In general, a system of linear equations can be represented by the matrix equation:
$$
MX = B 
$$
Where M is a matrix of coefficients, X is a column vector of variables, and B is the right-hand side of each equation. This matrix equation can then be solved for the variables:
$$
X = M^{-1}B
$$
If M is **singular**, then there is no unique solution to the system.

## Linear Transformations
The first column of a transformation matrix is the image of $\left(\begin{smallmatrix}1\\0\end{smallmatrix}\right)$, and the second column is the image of $\left(\begin{smallmatrix}0\\1\end{smallmatrix}\right)$. 
### 2D Transformations
#### Rotations
For a rotation with angle $\theta$ anticlockwise, the rotation matrix is given by:
$$\pmatrix{\cos\theta & -\sin\theta \\ \sin\theta & \cos\theta}$$

#### Reflections
A reflection in the $x$ axis is given by:
$$\pmatrix{1 & 0 \\ 0 & -1}$$
A reflection in the $y$ axis is given by:
$$\pmatrix{-1 & 0 \\ 0 & 1}$$
A reflection in the line $y=x$ is given by:
$$\pmatrix{0 & 1 \\ 1 & 0}$$
A reflection in the line $y=-x$ is given by:
$$\pmatrix{0 & -1 \\ -1 & 0}$$

#### Enlargement
For an enlargement with scale factor $k$ centred on the origin, the transformation matrix is given by:
$$\pmatrix{k & 0 \\ 0 & k}$$
#### Stretches
For a stretch with scale factor $k$ and $x$-axis invariant:
$$\pmatrix{1 & 0 \\ 0 & k}$$
For a stretch with scale factor $k$ and $y$-axis invariant:
$$\pmatrix{k & 0 \\ 0 & 1}$$
#### Shears
**Shears** preserve orientation and area.
For a shear with $(0, 1) \mapsto (k, 1)$ and $x$-axis invariant:
$$\pmatrix{1 & k \\ 0 & 1}$$
For a shear with $(1, 0) \mapsto (1, k)$ and $y$-axis invariant:
$$\pmatrix{1 & 0 \\ k & 1}$$

### 3D Transformations
#### Reflections
There are three planes of reflection (needed for this course): the $xy$ plane, the $xz$ plane, and the $yz$ plane. Consider a reflection in the $xy$ plane. This is defined by all points $(x, y, z)$ where $z = 0$, so a reflection in the $xy$ plane has the matrix:
$$\pmatrix{1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & -1}$$
Similar reasoning can be used to find other reflection matrices in 3D.

#### Rotations
There are three axes of rotation: about the three coordinate axis. The axis of rotation is not affected, so one of the matrix columns is a unit vector. The other matrix elements are populated by the standard 2D rotation matrix $\left(\begin{smallmatrix}\cos\theta & -\sin\theta \\ \sin\theta & \cos\theta\end{smallmatrix}\right)$. For example, the matrix for a rotation by $\theta$ anticlockwise about the $x$ axis is:
$$
\pmatrix{1 & 0 & 0 \\ 0 & \cos\theta & -\sin\theta \\ 0 & \sin\theta & \cos\theta}
$$
Note that for rotations about the $y$ axis, the signs on the $\sin\theta$ and $-\sin\theta$ elements are swapped.

### Determinant
For a matrix transformation in two dimensions:
- The determinant gives the area scale factor.
- If the determinant is negative then the transformation reverses orientation.

For a matrix transformation in three dimensions:
- The determinant gives the volume scale factor.
- If the determinant is negative then the transformation changes orientation.

For common 2D transformations:
- The determinant of a rotation is 1.
- The determinant of a reflection is -1.
- The determinant of an enlargement with scale factor $k$ is $k^2$.
- The determinant of a stretch with scale factor $k$ is $k$.
- The determinant of a shear is 1.

### Combining and Inverses
A matrix M representing transformation A followed by transformation B is given by:
$$M = BA$$
The matrix that is applied first is on the right. This stems from function notation (where the rightmost function in a composite function is applied first).

The inverse transformation is represented by the inverse matrix. For a combined transformation $M = BA$:
$$M^{-1} = A^{-1}B^{-1}$$

## Invariant Points and Lines
An **invariant point** of a linear transformation **maps to itself**. The origin is an invariant point for all linear transformations. An invariant point of matrix M is defined as:
$$
M\left(\begin{smallmatrix}u\\v\end{smallmatrix}\right) = \left(\begin{smallmatrix}u\\v\end{smallmatrix}\right)
$$
A **line of invariant points** is formed when there are infinitely many solutions of the form $v = ku$. Lines of invariant points can be found by applying the transformation to a general point $M\left(\begin{smallmatrix}x\\y\end{smallmatrix}\right) = \left(\begin{smallmatrix}x\\y\end{smallmatrix}\right)$, and solving simultaneously.

An **invariant line** is a line where the image of any point on the line is also on the line. Lines of invariant points are a subset of invariant lines. Invariant lines can be found by considering the image of a general line $y = mx$ (or potentially $y = mx + c$).