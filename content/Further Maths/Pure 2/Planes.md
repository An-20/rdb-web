#### Vector equation
A **plane** is a flat surface in three-dimensional space that extends indefinitely in all directions. The **vector equation** of a plane containing point with position vector $\boldsymbol{a}$ and parallel to the directions of vectors $\boldsymbol{d}_1$ and $\boldsymbol{d}_2$ is:
$$
\boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}_1 + \mu\boldsymbol{d}_2
$$
Conceptually, this is very similar to the [[2 - Vectors#Vector Equation of a Line|vector equation of a line]], first going to the plane, then travelling along it parallel to the two direction vectors.

A plane is uniquely defined by **three non-colinear points**. Alternatively, a plane can also be defined by 
- a line and a point not on the line
- two intersecting lines with direction vectors parallel to the plane.

#### Cartesian equation
The **Cartesian equation of a plane** is often more useful, as it is difficult to tell if two planes in vector equation form are identical or parallel. The Cartesian equation uses the **normal vector**, a vector perpendicular to every line in the plane.

Let $A$ be a point in the plane and $P$ be any other point in the plane. The vector $AP$ has to be perpendicular to the normal vector $\boldsymbol{n}$, giving us the Cartesian equation:
$$
\begin{split}
(\boldsymbol{r} - \boldsymbol{a}) \cdot \boldsymbol{n} = 0 &\implies \boldsymbol{r}\cdot\boldsymbol{n} = \boldsymbol{a}\cdot\boldsymbol{n}
\\&\implies \boldsymbol{r}\cdot\boldsymbol{n} = d
\end{split}
$$
By rewriting $\boldsymbol{r} = \left(\begin{smallmatrix}x \\ y \\ z\end{smallmatrix}\right)$ and $\boldsymbol{n} = \left(\begin{smallmatrix}n_1 \\ n_2 \\ n_3\end{smallmatrix}\right)$, we get:
$$
n_1 x + n_2 y + n_3 z = d
$$

To **convert from vector form to Cartesian form**, use the cross product of the two direction vectors to find the normal vector of the plane. Then, use any point in the plane to find the constant dot product.

To **convert from Cartesian form to vector form**, find any three points in the plane and then use these points to find two direction vectors. For simplicity, try substituting different combinations of $x,y,z = 0$.

#### Intersections between lines and planes
The following method requires the equation of the plane in Cartesian form and the equation of the line in vector form:
- Using the vector equation of the line, find expressions in terms of the parameter (often $\lambda$) for the $x,y,z$ components. 
- Substitute each into the Cartesian plane equation.
- Solve for $\lambda$ (or if the equation is consistent, the line and plane do not intersect).

#### Angles between lines and planes
The angle between the line with direction vector $\boldsymbol{d}$ and the plane with normal $\boldsymbol{n}$ is $90\degree - \phi$, where $\phi$ is the acute angle between $\boldsymbol{n}$ and $\boldsymbol{d}$. 

The angle between two planes is the angle between their normals.

#### Distances between points, lines, and planes
**Distance between a point and plane**
For a plane with equation $\boldsymbol{r} \cdot \boldsymbol{n} = d$, and a point $M$ outside of the plane, the shortest distance from $M$ to the plane is $MP$ where $MP$ is perpendicular to the plane, making $P$ a foot of the perpendicular.

To find the distance $MP$:
- Find the vector equation of the line with direction vector $n$ through $M$.
- Find the intersection point $P$ between this line and the plane.
- Find the distance $MP$.

Following this gives the formula:
$$
D = \frac{|\boldsymbol{b}\cdot\boldsymbol{n}-d|}{|\boldsymbol{n}|}
$$

**Distance between a point and line**
The shortest distance between a point $(x_1, y_1)$ and the line with equation $ax+by=c$ is given by:
$$
D = \frac{|ax_1+by_1-c|}{\sqrt(a^2 + b^2)}
$$
This formula is given (don't even bother asking where it comes from).

**Distance between two skew lines**
Consider two points $M$ and $N$ along two skew lines. The distance $MN$ is minimised when the line segment $MN$ is perpendicular to both lines^[^1].

The shortest distance between two skew lines with equations $\boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}_1$ and $\boldsymbol{r} = \boldsymbol{b} + \mu\boldsymbol{d}_2$ is:
$$
D = \frac{|(\boldsymbol{b} - \boldsymbol{a}\cdot\boldsymbol{n}|}{|\boldsymbol{n}|}
$$
where $\boldsymbol{n} = \boldsymbol{d}_1 \times \boldsymbol{d}_2$.

**Distance between two parallel lines**
Consider two parallel lines with direction vectors $\boldsymbol{d}$. For a fixed point $A$ on the first line and a point $P$ on the second line, the distance $AP$ is minimised when $AP$ is perpendicular to both lines. The distance $AP$ is equal to the distance $|\boldsymbol{a} - \boldsymbol{b}|\sin\theta$, where $\theta$ is the angle between $AP$ and $d$, so $\cos\theta = \frac{(\boldsymbol{a} - \boldsymbol{b})\cdot\boldsymbol{d}}{|\boldsymbol{a} - \boldsymbol{b}||\boldsymbol{d}|}$. *This is not given.*

> we ran of budget for tikz diagrams so you just have to imagine it.

## Simultaneous Equations and Planes
#### Two variables
For **simultaneous linear equations in two variables**, which can be written as $\boldsymbol{M}\boldsymbol{r}=\boldsymbol{a}$, there are three possible cases:
- One unique solution, when $|\boldsymbol{M}| \not= 0$ (two intersecting lines).
- Infinitely many solutions, when $|\boldsymbol{M}| = 0$ and the equations are consistent (two overlapping parallel lines).
- No solutions, when $|\boldsymbol{M}| = 0$ and the equations are not consistent (two non-overlapping parallel lines).

#### Three variables
For **simultaneous linear equations in three variables**, there are five possible cases:
- One unique solution, when $|\boldsymbol{M}| \not= 0$ where three planes intersect at a point.

- Infinitely many solutions, when $|\boldsymbol{M}| = 0$ and the equations are consistent, where three planes intersect at a line forming a sheaf.

- No solutions, when $|\boldsymbol{M}| = 0$ and the equations are not consistent.
	- When three planes are all parallel to each other
	- When two planes are parallel and one is not
	- When the planes enclose a triangular prism, with all pairs of planes intersecting at parallel lines.

Two planes are parallel if their normal vectors are parallel (are multiples of each other).

**Footnotes**
[^1]: **Footnote on skew lines**
	It is not apparent that such a line segment necessarily exists, but it does for all pairs of skew lines.
