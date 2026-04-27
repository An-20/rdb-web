#### Vector equation
A **plane** is a flat surface in three-dimensional space that extends indefinitely in all directions. The **vector equation** of a plane containing point with position vector $\boldsymbol{a}$ and parallel to the directions of vectors $\boldsymbol{d}_1$ and $\boldsymbol{d}_2$ is:
$$
\boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}_1 + \mu\boldsymbol{d}_2
$$
Conceptually, this is very similar to the [[Vectors#Vector Equation of a Line|vector equation of a line]], first going to the plane, then travelling along it parallel to the two direction vectors.
```tikz
\usepackage{amsmath, amssymb}
\usetikzlibrary{arrows.meta, calc, positioning}

\begin{document}
\begin{tikzpicture}[>=Stealth]
    \coordinate (Dorig) at (-1.5, 3);
    \draw[thick, ->] (Dorig) -- ++(1,0) node[anchor=north east, pos=0.8, xshift=2pt] {$\mathbf{d}_1$};
    \draw[thick, ->] (Dorig) -- ++(0.7,0.7) node[anchor=south east, pos=0.8, yshift=2pt] {$\mathbf{d}_2$};
    
    \coordinate (O) at (0,0);
    \node[anchor=north east] at (O) {$O$};
    \coordinate (P) at (0.8, 2.3);
    \draw[very thick, red, ->] (O) -- (P);
    \node[red, anchor=mid west, xshift=2pt] at ($(O)!0.5!(P)$) {$\mathbf{a}$};

    \coordinate (PlaneStart) at ($(P) + (-1.5, -0.6)$);
    \coordinate (PlaneEnd) at ($(P) + (3.8, 1.6)$);
    \coordinate (V1) at ($(PlaneStart) + (3.8, 0)$);
    \coordinate (V2) at ($(PlaneEnd) + (-3.8, 0)$);
    \fill[fill=red!20, opacity=0.8] (PlaneStart) -- (V1) -- (PlaneEnd) -- (V2) -- cycle;
    
    \coordinate (Path1) at ($(P) + (2, 0)$);
    \draw[thick, blue, ->] (P) -- (Path1);
    \node[anchor=south, blue] at ($(P)!0.5!(Path1)$) {$\lambda \mathbf{d}_1$};
    
    \coordinate (R) at ($(Path1) + (1.2, 1.2)$);
    \draw[thick, blue, ->] (Path1) -- (R);
    \node[blue, xshift=-15pt, yshift=4pt] at ($(Path1)!0.5!(R)$) {$\mu \mathbf{d}_2$};
    
    \node[blue, anchor=south, xshift=-2pt] at (R) {$R$};
\end{tikzpicture}
\end{document}
```

A plane is uniquely defined by **three non-colinear points**. Alternatively, a plane can also be defined by 
- a line and a point not on the line
- two intersecting lines with direction vectors parallel to the plane.

#### Cartesian equation
The **Cartesian equation of a plane** is often more useful, as it is difficult to tell if two planes in vector equation form are identical or parallel. The Cartesian equation uses the **normal vector**, a vector perpendicular to every line in the plane.

Let $A$ be a point in the plane with position vector $\boldsymbol{a}$, and $P$ be any other point in the plane. The vector $AP$ has to be perpendicular to the normal vector $\boldsymbol{n}$, giving us the Cartesian equation:
$$
\begin{split}
(\boldsymbol{r} - \boldsymbol{a}) \cdot \boldsymbol{n} = 0 &\implies \boldsymbol{r}\cdot\boldsymbol{n} = \boldsymbol{a}\cdot\boldsymbol{n}
\\&\implies \boldsymbol{r}\cdot\boldsymbol{n} = k
\end{split}
$$
By rewriting $\boldsymbol{r} = \left(\begin{smallmatrix}x \\ y \\ z\end{smallmatrix}\right)$ and $\boldsymbol{n} = \left(\begin{smallmatrix}n_1 \\ n_2 \\ n_3\end{smallmatrix}\right)$, we get:
$$
n_1 x + n_2 y + n_3 z = k
$$

To **convert from vector form to Cartesian form**, use the cross product of the two direction vectors to find the normal vector of the plane. Then, use any point in the plane to find the constant dot product.

To **convert from Cartesian form to vector form**, find any three points in the plane and then use these points to find two direction vectors. For simplicity, try substituting different combinations of $x,y,z = 0$.

#### Intersections between lines and planes
The following method requires the equation of the plane in Cartesian form and the equation of the line in vector form:
- Using the vector equation of the line, find expressions in terms of the parameter (often $\lambda$) for the $x,y,z$ components. 
- Substitute each into the Cartesian plane equation.
- Solve for $\lambda$ (or if the equation is inconsistent, the line and plane do not intersect).

#### Angles between lines and planes
The **angle between the line** with direction vector $\boldsymbol{d}$ and the **plane** with normal $\boldsymbol{n}$ is $90\degree - \phi$, where $\phi$ is the acute angle between $\boldsymbol{n}$ and $\boldsymbol{d}$. 
```tikz
\usepackage{amsmath, amssymb}
\usetikzlibrary{arrows.meta, calc, positioning}

\begin{document}
\begin{tikzpicture}[>=Stealth]
	\fill[fill=red!20, opacity=0.8] (-2,-0.5) -- (2,-0.5) -- (3,1) -- (-1,1) -- cycle;
	\coordinate (O) at (0.5,0.25);
	
	\draw[->, thick, red] (O) -- ++(0,2) coordinate (N);
	\node[right, red] at (N) {$\boldsymbol{n}$};
	
	\draw[->, thick, blue] (O) -- ++(2,1.2) coordinate (D);
	\draw[thick, blue] (O) -- ++(-1.2,-0.72);
	\node[above right, blue] at (D) {$\boldsymbol{d}$};
	
	\draw[orange, thick] (O)+(90:0.5) arc[start angle=90,end angle=31,radius=0.5];
	\node[orange] at ($(O)+(62:0.75)$) {$\phi$};
	
	\draw[purple, thick] ($(O)+(0.8,0)$) arc[start angle=0,end angle=31,radius=0.8];
	\node[purple, xshift=14pt, yshift=0pt] at ($(O)+(0.95,0.32)$) {$90^\circ-\phi$};
	
	\draw[dashed] (D) -- ($(O)+(2,0)$);
\end{tikzpicture}
\end{document}
```


The **angle between two planes** is the angle between their normals.
```tikz
\usepackage{tikz}
\usetikzlibrary{calc, 3d, arrows.meta}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[
    x={(0.4cm,0cm)},
    y={(0cm,0.4cm)},
    z={(0.2cm,0.16cm)},
    line join=round,
    line cap=round
]

\def\zfront{-2.5}
\def\zback{4.5}
\def\xint{3}
\def\yint{3}

\fill[red!20, opacity=0.8]
    (-3.5, 0, \zfront) --
    (\xint, 0, \zfront) --
    (\xint, 0, \zback) --
    (-3.5, 0, \zback) -- cycle;

\fill[cyan!40!white, opacity=0.7]
    (-2.0, 5.0, \zfront) --
    (-2.0, 5.0, \zback) --
    (6.0, -3.0, \zback) --
    (6.0, -3.0, \zfront) -- cycle;

\draw[cyan!70!black, thick] (\xint, 0, \zfront) -- (\xint, 0, \zback);

\begin{scope}[canvas is xy plane at z=1.5]
    \draw[purple, thick] (0,0) -- (\xint,0);
    \draw[purple, thick] (0,0) -- (0,\yint);

    \draw[blue!70!white, thick] (4.5, -1.5) -- (-1.0, 4.0);
    \draw[purple, thick] (0.3,0) -- (0.3,0.3) -- (0,0.3);

    \coordinate (P) at (0,3);
    \coordinate (P1) at ($(P) + (-45:0.3)$);
    \coordinate (P2) at ($(P) + (-45:0.3) + (-135:0.3)$);
    \coordinate (P3) at ($(P) + (-135:0.3)$);
    \draw[purple, thick] (P1) -- (P2) -- (P3);

    \draw[purple, thick] (3,0) +(-0.8,0) arc[start angle=180, end angle=135, radius=0.8];
    \node[purple] at (1.9, 0.34) {$\theta$};

    \draw[purple, thick] (0,3) +(0,0.8) arc[start angle=90, end angle=135, radius=0.8];
    \node[purple] at (-0.45, 4.25) {$\theta$};

    \draw[->, red!85!black, line width=1.5pt, >=Stealth] 
        (0,3) -- (0,6) node[left, yshift=-9pt, text=red!85!black] {$\mathbf{n}_1$};
        
    \draw[->, blue!85!black, line width=1.5pt, >=Stealth] 
        (0,3) -- (-2.5,0.5) 
        node[below right, text=blue!85!black] {$\mathbf{n}_2$};
        
\end{scope}
\end{tikzpicture}
\end{document}
```

#### Distances between points, lines, and planes
**Distance between a point and plane**
For a plane with equation $\boldsymbol{r} \cdot \boldsymbol{n} = k$, and a point $M$ outside of the plane, the shortest distance from $M$ to the plane is $MP$ where $MP$ is perpendicular to the plane, making $P$ a foot of the perpendicular.

To find the distance $MP$:
- Find the vector equation of the line with direction vector $n$ through $M$.
- Find the intersection point $P$ between this line and the plane.
- Find the distance $MP$.

Following this gives the formula:
$$
D = \frac{|\boldsymbol{b}\cdot\boldsymbol{n}-k|}{|\boldsymbol{n}|}
$$
Where $\boldsymbol{b}$ is the point being considered.

**Distance between a point and line**
The shortest distance between a point $(x_1, y_1)$ and the line with equation $ax+by=c$ is given by:
$$
D = \frac{|ax_1+by_1-c|}{\sqrt{a^2 + b^2}}
$$
This formula is *given*.

**Distance between two skew lines**
Consider two points $M$ and $N$ along two skew lines. The distance $MN$ is minimised when the line segment $MN$ is perpendicular to both lines [^1].

The shortest distance between two skew lines with equations $\boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}_1$ and $\boldsymbol{r} = \boldsymbol{b} + \mu\boldsymbol{d}_2$ is:
$$
D = \frac{|(\boldsymbol{b} - \boldsymbol{a})\cdot\boldsymbol{n}|}{|\boldsymbol{n}|}
$$
where $\boldsymbol{n} = \boldsymbol{d}_1 \times \boldsymbol{d}_2$.

**Distance between two parallel lines**
Consider two parallel lines with direction vectors $\boldsymbol{d}$. For a fixed point $A$ on the first line and a point $P$ on the second line, the distance $AP$ is minimised when $AP$ is perpendicular to both lines. The distance $AP$ is equal to the distance:
$$
D = |\boldsymbol{a} - \boldsymbol{b}|\sin\theta
$$Where $\theta$ is the angle between $AP$ and $d$, so $\cos\theta = \frac{(\boldsymbol{a} - \boldsymbol{b})\cdot\boldsymbol{d}}{|\boldsymbol{a} - \boldsymbol{b}||\boldsymbol{d}|}$. *This is not given.*

## Simultaneous equations and planes
#### Two variables
For **simultaneous linear equations in two variables**, which can be written as $\boldsymbol{M}\boldsymbol{X}=\boldsymbol{B}$, there are three possible cases:
- One unique solution, when $|\boldsymbol{M}| \not= 0$ (two intersecting lines).
- Infinitely many solutions, when $|\boldsymbol{M}| = 0$ and the equations are consistent (two overlapping parallel lines).
- No solutions, when $|\boldsymbol{M}| = 0$ and the equations are not consistent (two non-overlapping parallel lines).

A visual representation is provided below.
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth, scale=0.8]
    \begin{scope}[shift={(0,0)}]
        \draw[->] (-0.5,0) -- (4,0) node[right] {$x$};
        \draw[->] (0,-0.5) -- (0,4) node[above] {$y$};
        
        \draw[thick, blue] (-0.5, 0.5) -- (3.5, 3.5) node[right] {$L_1$};
        \draw[thick, red] (-0.5, 3.5) -- (3.5, 0.5) node[right] {$L_2$};
        
        \filldraw[black] (1.5,1.5) circle (2pt);
        
        \node[align=center, below] at (1.5, -1) {
            \textbf{Unique solution} \\ 
            $|\mathbf{M}| \neq 0$ \\ 
            Lines intersect
        };
    \end{scope}

    \begin{scope}[shift={(6,0)}]
        \draw[->] (-0.5,0) -- (4,0) node[right] {$x$};
        \draw[->] (0,-0.5) -- (0,4) node[above] {$y$};
        
        \draw[ultra thick, blue] (-0.5, 1) -- (3.5, 3) node[right] {$L_1, L_2$};
        \draw[dashed, white, thick] (-0.5, 1) -- (3.5, 3);
        
        \node[align=center, below] at (1.5, -1) {
            \textbf{Infinite solutions} \\ 
            $|\mathbf{M}| = 0$ (consistent) \\ 
            Lines overlap
        };
    \end{scope}

    \begin{scope}[shift={(12,0)}]
        \draw[->] (-0.5,0) -- (4,0) node[right] {$x$};
        \draw[->] (0,-0.5) -- (0,4) node[above] {$y$};
        
        \draw[thick, blue] (-0.5, 2) -- (3.5, 4) node[right] {$L_1$};
        \draw[thick, red] (-0.5, 0.5) -- (3.5, 2.5) node[right] {$L_2$};
        
        \node[align=center, below] at (1.5, -1) {
            \textbf{No solution} \\ 
            $|\mathbf{M}| = 0$ (inconsistent) \\ 
            Lines are parallel
        };
    \end{scope}

\end{tikzpicture}
\end{document}
```

#### Three variables
For **simultaneous linear equations in three variables**, there are six possible cases:
- One unique solution, when $|\boldsymbol{M}| \not= 0$ where three planes intersect at a point.

- Infinitely many solutions, when $|\boldsymbol{M}| = 0$ and the equations are consistent.
	- Three planes intersect at a line, forming a sheaf.
	- Three overlapping planes.

- No solutions, when $|\boldsymbol{M}| = 0$ and the equations are not consistent.
	- When three planes are all parallel to each other
	- When two planes are parallel and one is not
	- When the planes enclose a triangular prism, with all pairs of planes intersecting at parallel lines.

Two planes are parallel if their normal vectors are parallel (are multiples of each other).


**Footnotes**
[^1]: **Footnote on skew lines and perpendicularity**
	It is not apparent that such a line segment necessarily exists, but it does for all pairs of skew lines.
