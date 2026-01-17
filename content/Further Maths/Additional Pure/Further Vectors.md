## Vector Product
The **vector (cross) product** of two vectors is given by:
$$
\boldsymbol{a} \times \boldsymbol{b} = |\boldsymbol{a}|\,|\boldsymbol{b}|\,\sin \theta\,\,\hat{n}
$$
Where $\theta$ is the angle between $\boldsymbol{a}$ and $\boldsymbol{b}$, and $\hat{n}$ is a unit vector perpendicular to $\boldsymbol{a}$ and $\boldsymbol{b}$. The direction of $\hat{n}$ is found using the **right hand rule**, by aligning the first (index) finger with $\boldsymbol{a}$ and the second (middle) finger with $\boldsymbol{b}$, the thumb points in the direction of $\hat{n}$.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}

\begin{document}
\begin{tikzpicture}[thick, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\draw[ultra thick,-latex](0,0)--(3,0)node[midway,below]{$a$};
	\draw[ultra thick,-latex](0,0)--(1,1)node[midway,above]{$b$};
	\draw[ultra thick,-latex](0,0)--(0,3)node[pos=0.7,left]{$a\times b$};
	\draw[ultra thick,-latex](0,0)--(0,1)node[pos=0.7,left]{$\hat{n}$};
\end{tikzpicture}
\end{document}
```
From Pure 1, there is also the definition of the cross product in the formula booklet:
$$
\boldsymbol{a} \times \boldsymbol{b} = \left|\begin{matrix}\boldsymbol{i} & a_1 & b_1 \\ \boldsymbol{j} & a_2 & b_2 \\ \boldsymbol{k} & a_3 & b_3\end{matrix}\right| = \begin{pmatrix}a_2b_3 - a_3b_2 \\ a_3b_1 - a_1b_3 \\ a_1b_2 - a_2b_1\end{pmatrix}
$$
#### Properties
- $|\boldsymbol{a} \times \boldsymbol{b}| = |\boldsymbol{a}|\,|\boldsymbol{b}|\,\sin\theta$.
- If $\boldsymbol{a} \times \boldsymbol{b} = 0,\,a \not= 0,\,\not=0$, this means $\sin\theta = 0 \implies \theta=0$, meaning $\boldsymbol{a}$ and $\boldsymbol{b}$ are parallel or collinear.
- $\boldsymbol{a} \times \boldsymbol{b} = -\boldsymbol{b} \times \boldsymbol{a}$; the vector product is not commutative[^1].
- $\boldsymbol{a} \times (\boldsymbol{b} + \boldsymbol{c}) = \boldsymbol{a} \times \boldsymbol{b} + \boldsymbol{a} \times \boldsymbol{c}$; the vector product distributes over addition.
- $\boldsymbol{a} \times \lambda\boldsymbol{b} = \lambda\boldsymbol{a} \times \boldsymbol{b} = \lambda\boldsymbol{a}\boldsymbol{b}$; multiplication by a scalar can be 'factored out'.

#### Applications
###### Straight lines
The general **vector equation of a straight line** is $\boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}$, where $\boldsymbol{a}$ is a point on the line, $\lambda$ is a parameter varied to give different points along the line, and $\boldsymbol{d}$ is the direction vector of the line.
- Moving terms over gives $\boldsymbol{r} - \boldsymbol{a} = \lambda\boldsymbol{d}$
- Taking the cross product with $\boldsymbol{d}$ on both sides gives $(\boldsymbol{r} - \boldsymbol{a}) \times \boldsymbol{d} = \lambda\boldsymbol{d} \times \boldsymbol{d}$
- Considering $\boldsymbol{d} \times \boldsymbol{d} = 0$ gives $(\boldsymbol{r} - \boldsymbol{a}) \times \boldsymbol{d} = 0$, another equation for a straight line.

###### Area of triangles and parallelograms
Consider **triangle** $\triangle OAB$, which has area $\frac{1}{2}\times OA\times BH = \frac{1}{2}\times OA \times OB \,\sin\theta$ (by trigonometry).
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}
\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[scale=0.75, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\begin{scope}[very thick,decoration={
		markings,
		mark=at position 0.5 with {\arrow{>}}}
		] 
		\draw[postaction={decorate}] (-2, 0) -- (4, 0);
		\draw[postaction={decorate}] (-2, 0) -- (2, 3);
	\end{scope}

	\coordinate[label=above left:\large$b$](b) at (0, 1.5);
	\coordinate[label=below:\large$a$](a) at (1, 0);

	\coordinate[label=above left:$B$](B) at (2, 3);
	\coordinate[label=below right:$A$](A) at (4, 0);
	\coordinate[label=below left:$O$](O) at (-2, 0);
	\coordinate[label=below:$H$](H) at (2, 0);
	
	\draw (O) -- (A) -- (B) -- cycle;
	\draw (B) -- (H);
	\draw (1.6,0) rectangle (2,.4);
	\pic [draw, -, "$\theta$", angle eccentricity=1.5] {angle = A--O--B};
\end{tikzpicture}
\end{document}
```
Let $\boldsymbol{a} = \overrightarrow{OA}$ and $\boldsymbol{b} = \overrightarrow{OB}$. By the definition of the cross product:
$$
\text{Area of }\triangle OAB = \frac{1}{2} |\boldsymbol{a}|\,|\boldsymbol{b}|\,\sin \theta\, = \frac{1}{2} |\boldsymbol{a} \times \boldsymbol{b}|
$$

Consider **parallelogram** $OACB$, which has area $OA \times BH = OA \times OB \,\sin\theta$ (by trigonometry).
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}
\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[scale=0.75, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\begin{scope}[very thick,decoration={
		markings,
		mark=at position 0.5 with {\arrow{>}}}
		] 
		\draw[postaction={decorate}] (-2, 0) -- (4, 0);
		\draw[postaction={decorate}] (-2, 0) -- (2, 3);
	\end{scope}

	\coordinate[label=above left:\large$b$](b) at (0, 1.5);
	\coordinate[label=below:\large$a$](a) at (1, 0);

	\coordinate[label=above left:$B$](B) at (2, 3);
	\coordinate[label=below right:$A$](A) at (4, 0);
	\coordinate[label=below left:$O$](O) at (-2, 0);
	\coordinate[label=above right:$C$](C) at (8, 3);
	\coordinate[label=below:$H$](H) at (2, 0);
	
	\draw (O) -- (B) -- (C) -- (A) -- cycle;
	\draw (B) -- (H);
	\draw (1.6,0) rectangle (2,.4);
	\pic [draw, -, "$\theta$", angle eccentricity=1.5] {angle = A--O--B};
\end{tikzpicture}
\end{document}
```
Let $\boldsymbol{a} = \overrightarrow{OA}$ and $\boldsymbol{b} = \overrightarrow{OB}$. By the definition of the cross product:
$$
\text{Area of } OACB = |\boldsymbol{a}|\,|\boldsymbol{b}|\,\sin \theta\, = |\boldsymbol{a} \times \boldsymbol{b}|
$$

## Scalar triple product
The **scalar triple product** of three vectors is given by:
$$
(\boldsymbol{a} \times \boldsymbol{b}) \cdot \boldsymbol{c} 
= (\boldsymbol{b} \times \boldsymbol{c}) \cdot \boldsymbol{a} 
= (\boldsymbol{c} \times \boldsymbol{a}) \cdot \boldsymbol{b}
$$
Note how swapping the order of the vectors in a circular order does not affect the scalar triple product. However, swapping any two vectors, e.g. $(\boldsymbol{b} \times \boldsymbol{a}) \cdot \boldsymbol{c}$ would give negate the value (by the anticommutativity of the cross product). The scalar triple product can also be defined by the determinant of a matrix:
$$
(\boldsymbol{a} \times \boldsymbol{b}) \cdot \boldsymbol{c} = \boldsymbol{c} \cdot (\boldsymbol{a} \times \boldsymbol{b}) = \left|\begin{matrix} c_1 & a_1 & b_1 \\ c_2 & a_2 & b_2 \\ c_3 & a_3 & b_3\end{matrix}\right|
$$

#### Applications
- The volume of a **parallelepiped** with sides $\boldsymbol{a}$, $\boldsymbol{b}$. and $\boldsymbol{c}$ is given by the magnitude of the scalar triple product: $|(\boldsymbol{a} \times \boldsymbol{b}) \cdot \boldsymbol{c} |$.
- The volume of a **tetrahedra** with sides $\boldsymbol{a}$, $\boldsymbol{b}$. and $\boldsymbol{c}$ is given by one-sixth of the magnitude of the scalar triple product : $\frac{1}{6}|(\boldsymbol{a} \times \boldsymbol{b}) \cdot \boldsymbol{c} |$.

> *we also ran out of budget for tikz diagrams here :(*
> *no seriously do you know how hard 3d is*

**Footnotes**
​[^1]: **Footnote on anticommutativity of the vector product**
	The vector product is anticommutative, that is an operation $\star$ where $a \star b$ is the inverse to $b \star a$ (in this case the inverse is negating the value).
