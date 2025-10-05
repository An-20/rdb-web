## Overview
A **column vector** $\left(\begin{smallmatrix}4 \\ 1 \\ 3\end{smallmatrix}\right)$ can be represented as $4i + 1j + 3k$, where $i$, $j$, and $k$ are **basis vectors** (vectors with a magnitude of 1 in the $x$, $y$, and $z$ directions respectively).
```tikz
\usepackage{tikz}
\usepackage{tikz-3dplot} 
\begin{document}

\tdplotsetmaincoords{60}{120} 
\begin{tikzpicture} [scale=1, tdplot_main_coords, axis/.style={->,black,thick}, 
vector/.style={-stealth,red,very thick}, 
vector guide/.style={dashed,red,thick}]

\begin{scope}[shift={(-5.8, 10)}]
	%standard tikz coordinate definition using x, y, z coords
	\coordinate (O) at (0,0,0);
	
	%tikz-3dplot coordinate definition using x, y, z coords
	
	\pgfmathsetmacro{\ax}{4}
	\pgfmathsetmacro{\ay}{1}
	\pgfmathsetmacro{\az}{3}
	
	\coordinate (P) at (\ax,\ay,\az);
	
	%draw axes
	\draw[axis] (0,0,0) -- (5,0,0) node[anchor=north east]{\huge $x$};
	\draw[axis] (0,0,0) -- (0,5,0) node[anchor=north west]{\huge $y$};
	\draw[axis] (0,0,0) -- (0,0,5) node[anchor=south]{\huge $z$};
	
	%draw a vector from O to P
	\draw[vector] (O) -- (P);
	
	%draw guide lines to components
	\draw[vector guide]         (O) -- (\ax,\ay,0);
	\draw[vector guide] (\ax,\ay,0) -- (P);
	\draw[vector guide]         (P) -- (0,0,\az);
	\draw[vector guide] (\ax,\ay,0) -- (0,\ay,0);
	\draw[vector guide] (\ax,\ay,0) -- (0,\ay,0);
	\draw[vector guide] (\ax,\ay,0) -- (\ax,0,0);
	\node[tdplot_main_coords,anchor=east]
	at (\ax,0,0){(\ax, 0, 0)};
	\node[tdplot_main_coords,anchor=west]
	at (0,\ay,0){(0, \ay, 0)};
	\node[tdplot_main_coords,anchor=east]
	at (0,0,\az){(0, 0, \az)};
\end{scope}

\begin{scope}[shift={(0, 0)}]
	%standard tikz coordinate definition using x, y, z coords
	\coordinate (P) at (0,0,0);
	
	%tikz-3dplot coordinate definition using x, y, z coords
	
	%draw axes
	\draw[axis] (0,0,0) -- (1,0,0) node[anchor=north east]{\huge $i$};
	\draw[axis] (0,0,0) -- (0,1,0) node[anchor=north west]{\huge $j$};
	\draw[axis] (0,0,0) -- (0,0,1) node[anchor=south]{\huge $k$};
\end{scope}
\end{tikzpicture}
\end{document}
```
A **position vector** represents a point in space, with respect to the origin. The position vector for the coordinate $(4, 1, 3)$ is $\left(\begin{smallmatrix}4 \\ 1 \\ 3\end{smallmatrix}\right)$.

The **magnitude** of a column vector $\left(\begin{smallmatrix}a_1 \\ a_2 \\ a_3\end{smallmatrix}\right)$ is $\sqrt{a_1^2 + a_2^2 + a_3^2}$ , which comes from applying the Pythagorean theorem.

## Vector Equation of a Line
Given a position vector $\boldsymbol{a}$ of any point on the line, and the direction vector $\boldsymbol{d}$ of the line, the **vector equation of that line** is:
$$
\boldsymbol{r} = \boldsymbol{a} + \lambda \boldsymbol{d}
$$
Where $\lambda$ (lambda) is just a parameter which is varied to give different points on the line, and $\boldsymbol{r}$ is the position vector of a general point on the line.

Two vector equations represent the **same line** if:
- they are parallel (the direction vectors $\boldsymbol{d}$ are scalar multiplies)
- and one point from one line lies upon the other line.

Therefore, there are different vector equations for the same line. For example, all of these represent the same line (with different values of parameter $\lambda$ for any specific point.):
1. $\boldsymbol{r} = \left(\begin{smallmatrix}1 \\ 3 \\ 2\end{smallmatrix}\right) + \lambda \left(\begin{smallmatrix}2 \\ 6 \\ 10\end{smallmatrix}\right)$
2. $\boldsymbol{r} = \left(\begin{smallmatrix}1 \\ 3 \\ 2\end{smallmatrix}\right) + \lambda \left(\begin{smallmatrix}1 \\ 3 \\ 5\end{smallmatrix}\right)$ (the direction vector is a scalar multiple)
3. $\boldsymbol{r} = \left(\begin{smallmatrix}4 \\ 12 \\ 17\end{smallmatrix}\right) + \lambda \left(\begin{smallmatrix}3 \\ 9 \\ 15\end{smallmatrix}\right)$ (the direction vector is a scalar multiple and the position vector $\boldsymbol{a}$ lies upon the other two lines)

## Cartesian Equation of a Line
In two dimensions, a **Cartesian equation of a line** can be written as:
$$
\begin{split}
& y = mx + c
\\& ax + by = c
\\& ax + by + c = 0
\end{split}
$$
For the vector equation of a line, the direction vector $\left(\begin{smallmatrix}p \\ q \end{smallmatrix}\right)$ means that the line has a gradient of $\frac{q}{p}$ in the Cartesian equation.

#### Changing between vector and Cartesian equations
To change between a vector and Cartesian equation, the "point slope" form of the equation can be used (where $(x_1, y_1)$ is a specific point on the line):
$$
y - y_1 = m(x - x_1)
$$

Alternatively, using the fact that the position vector $\boldsymbol{r}$ gives coordinates of a point on the line, making $\lambda$ the subject of both equations and setting them as equal yields the Cartesian form:
$$
\begin{split}
& \boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}
\\& \boldsymbol{r} = \left(\begin{smallmatrix}a_1 \\ a_2 \end{smallmatrix}\right) + \lambda\left(\begin{smallmatrix}d_1 \\d_2 \end{smallmatrix}\right)
\\& x = a_1 + \lambda d_1,\,\,\, y=a_2 + \lambda d_2
\\& \lambda = \frac{x - a_1}{d_1},\,\,\, \lambda=\frac{y - a_2}{d_2}
\\& \frac{x - a_1}{d_1} = \frac{y - a_2}{d_2}
\\& d_2(x-a_1) = d_1(y - a_2)
\end{split}
$$
Which can then be rearranged into the desired form.

#### General method
In general, to find the Cartesian equation given the vector equation:
 - write $x$, $y$, and $z$ in terms of $\lambda$.
 - make $\lambda$ the subject of each equation
 - equate the three equations for $\lambda$, giving an equation of the form $\frac{x-a}{k} = \frac{y-b}{m} = \frac{z-c}{n}$.

Where all of the direction vector components **are not 0**:
$$
\begin{split}
& \boldsymbol{r} = \boldsymbol{a} + \lambda\boldsymbol{d}
\\& \boldsymbol{r} = \left(\begin{smallmatrix}a_1 \\ a_2 \\ a_3 \end{smallmatrix}\right) + \lambda\left(\begin{smallmatrix}d_1 \\ d_2 \\ d_3 \end{smallmatrix}\right)
\\& x = a_1 + d_1\lambda,\,\,\,y = a_2 + d_2\lambda,\,\,\,z = a_2 + d_2\lambda,\,\,\,
\\& \frac{x - a_1}{d_1} = \frac{y - a_2}{d_2} = \frac{z - a_3}{d_3}
\end{split}
$$


In some cases, where one (or more) of the direction vector components is 0 (e.g. $\left(\begin{smallmatrix}1 \\ 3 \\ 0 \end{smallmatrix}\right)$), one of the equations will not contain $\lambda$, so there will be a separate equation that looks like $z = 0$, where one of the $x$, $y$, or $z$ components is a constant term. 

If that didn't make much sense, imagine a 2D line $y = mx + c$. If $m$ was 0, then the line would just be $y = c$, a constant. That's effectively the same idea.

## Intersections of Lines
In a (2D) plane, two different straight lines either intersect, or are parallel (left). However, in 3D, two lines can be not parallel and also never intersect. These are called **skew lines** (right).
```tikz
\usepackage{tikz}
\usepackage{tikz-3dplot}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{white}$#2$]at (#1){};}
% \documentclass[border=5pt, multi, tikz]{standalone}
\usetikzlibrary{quotes,arrows.meta}
\tikzset{
  cuboid/.pic={
    \tikzset{%
      every edge quotes/.append style={midway, auto},
      /cuboid/.cd,
      #1
    }
    \draw [every edge/.append style={pic actions, densely dashed, opacity=.5}, pic actions]
    (0,0,0) coordinate (o) -- ++(-\cubescale*\cubex,0,0) coordinate (a) -- ++(0,-\cubescale*\cubey,0) coordinate (b) edge coordinate [pos=1] (g) ++(0,0,-\cubescale*\cubez)  -- ++(\cubescale*\cubex,0,0) coordinate (c) -- cycle
    (o) -- ++(0,0,-\cubescale*\cubez) coordinate (d) -- ++(0,-\cubescale*\cubey,0) coordinate (e) edge (g) -- (c) -- cycle
    (o) -- (a) -- ++(0,0,-\cubescale*\cubez) coordinate (f) edge (g) -- (d) -- cycle;
    \path [every edge/.append style={pic actions, |-|}]
    ;
  },
  /cuboid/.search also={/tikz},
  /cuboid/.cd,
  width/.store in=\cubex,
  height/.store in=\cubey,
  depth/.store in=\cubez,
  units/.store in=\cubeunits,
  scale/.store in=\cubescale,
  width=10,
  height=10,
  depth=10,
  units=cm,
  scale=.1,
}
\begin{document}
\begin{tikzpicture}[scale = 3]


\begin{scope}[shift={(-3, 0)}, scale=0.33]
	\draw[step=2cm,gray,very thin] (-3.25,-3.25)grid(3.25,3.25);
	\draw(-3.75,0) -- (3.75,0);
	\draw(0,-3.75) -- (0,3.75);
	\node[fill=white] at (-0.4,-0.4){0};
	\foreach \x in {-2,-1,1,2} \node[fill=white] at (-0.4,2*\x){\x};
	\foreach \x in {-2,-1,1,2} \node[fill=white] at (2*\x,-0.4){\x};
	
	\draw[red, thick] (-3.75,-2) -- (3.75,2);
	\draw[green, thick] (-3.75,-1) -- (3.75,3);
	\draw[orange, thick] (-3.75,2.6) -- (3.75,0.5);
\end{scope}

\begin{scope}[shift={(0, 0)}]
  \pic at (0, 0) {cuboid={width=1, height=1, depth=1, scale=3}};
  \draw[very thick,red] (0, 0, 0) -- (-1, 0, -1);
  \draw[very thick,green] (0, -1, 0) -- (-1, -1, 0);
\end{scope}
\end{tikzpicture}
\end{document}
```
When two lines intersect, there are values of $\lambda$ and $\mu$ such that $\boldsymbol{r}_1 = \boldsymbol{r}_2$.

#### Finding Intersections
To find the intersection between two lines (in the vector form):
- Set the two position vectors $\boldsymbol{r}_1$ and $\boldsymbol{r}_2$ to be equal, and form equations for each component.
- Solve the simultaneous equations to find values of $\lambda$ and $\mu$, and ensure they satisfy all equations.
- Substitute $\lambda$ or $\mu$ back into the equation to get the intersection point.

Similarly, to show that two lines do not intersect, show that any value of $\lambda$ and $\mu$ does not hold for all three equations. The same methods apply for the Cartesian form.

## Dot Product
The **dot (scalar) product** is one way to multiply vectors. The motivation behind the dot product is to multiply two vectors to get a scalar result.

The diagram below shows two lines with angle $\theta$ between them. $\boldsymbol{a}$ and $\boldsymbol{b}$ are vectors in the directions of the two lines, pointing away from the intersection point.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}
\begin{document}
\begin{tikzpicture}[thick, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\begin{scope}[very thick,decoration={
		markings,
		mark=at position 0.5 with {\arrow{>}}}
		] 
		\draw[postaction={decorate}] (0, 0) coordinate (o) -- (5, 0);
		\draw[postaction={decorate}] (0, 0) -- (3, 4);
	\end{scope}

	\coordinate[label=above left:\large$a$](a) at (1.5, 2);
	\coordinate[label=below:\large$b$](b) at (2.5, 0);

	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (o) at (0,0) {};
	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (a) at (5,0) {};
	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (b) at (3,4) {};

	\pic [draw, -, "$\theta$", angle eccentricity=1.5] {angle = a--o--b};
\end{tikzpicture}
\end{document}
```
The dot product is defined as: 
$$
\boldsymbol{a} \cdotp \boldsymbol{b} = |\boldsymbol{a}| \times |\boldsymbol{b}| \times \cos({\theta})
$$
The $\cos{\theta}$ is there to multiply the amount of the vectors that point in the same direction, taking the component of $\boldsymbol{a}$ that lies alongside $\boldsymbol{b}$.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}
\begin{document}

\begin{tikzpicture}[thick, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\begin{scope}[very thick,decoration={
		markings,
		mark=at position 0.5 with {\arrow{>}}}
		] 
		\draw[postaction={decorate}] (0, 0) coordinate (o) -- (5, 0);
		\draw[postaction={decorate}] (0, 0) -- (3, 4);
	\end{scope}
	
	\coordinate[label=above left:\large$a$](a) at (1.5, 2);
	\coordinate[label=below:\large$b$](b) at (2.5, 0);

	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (o) at (0,0) {};
	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (a) at (5,0) {};
	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (b) at (3,4) {};

	\draw[very thick, dotted] (3, 0) -- (3, 4);

	\pic [draw, -, "$\theta$", angle eccentricity=1.5] {angle = a--o--b};
	\draw [|-|] (0, -0.5) -- (3, -0.5);
	\node[label=below:$|a|\cos{\theta}$] () at (1.5, -0.5) {};
	
\end{tikzpicture}
\end{document}
```

Another way to define $\boldsymbol{a} \cdotp \boldsymbol{b}$ for $\boldsymbol{a} = \left(\begin{smallmatrix}a_1 \\ a_2 \\a_3\end{smallmatrix}\right)$ and $\boldsymbol{b} = \left(\begin{smallmatrix}b_1 \\ b_2 \\b_3\end{smallmatrix}\right)$ is:
$$
\boldsymbol{a} \cdotp \boldsymbol{b} = a_1b_1 + a_2b_2 + a_3b_3
$$

Thus, to find the angle between two vectors, we can use both definitions:
$$
\begin{split}
& \boldsymbol{a} \cdotp \boldsymbol{b} = |\boldsymbol{a}| \times |\boldsymbol{b}| \times \cos({\theta}) = a_1b_1 + a_2b_2 + a_3b_3
\\& \cos{\theta} = \frac{a_1b_1 + a_2c_2 + a_3c_3}{|\boldsymbol{a}||\boldsymbol{b}|}
\end{split}
$$
#### Applications
For two lines with vector equations, the **angle between the two lines** is equal to the **angle between the direction vectors**. This can be found even if the two lines do not intersect.

The dot product can be used to **test if two vectors are perpendicular**, as the $\cos(\theta)$ term is equal to 0 when two vectors are perpendicular. Therefore, two vectors $\boldsymbol{a}$ and $\boldsymbol{b}$ are perpendicular if $\boldsymbol{a} \cdotp \boldsymbol{b} = 0$. Similarly, two lines are perpendicular if $\boldsymbol{d}_1 \cdotp \boldsymbol{d}_2 = 0$.

## Cross Product
Given two vectors, the cross product (vector product) $\boldsymbol{a} \times \boldsymbol{b}$ will produce a new vector that is perpendicular to $\boldsymbol{a}$ and $\boldsymbol{b}$.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}

\begin{document}
\begin{tikzpicture}[thick, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\draw[ultra thick,-latex](0,0)--(3,0)node[midway,below]{$a$};
	\draw[ultra thick,-latex](0,0)--(1,1)node[midway,above]{$b$};
	\draw[ultra thick,-latex](0,0)--(0,3)node[pos=0.7,right]{$a\times b$};
\end{tikzpicture}
\end{document}
```

The definition of the cross product for $\boldsymbol{a} = \left(\begin{smallmatrix}a_1 \\ a_2 \\a_3\end{smallmatrix}\right)$ and $\boldsymbol{b} = \left(\begin{smallmatrix}b_1 \\ b_2 \\b_3\end{smallmatrix}\right)$ is:
$$
\boldsymbol{a} \times \boldsymbol{b} = \left(\begin{smallmatrix}a_2b_3 - a_3b_2 \\ a_3b_1 - a_1b_3 \\ a_1b_2 - a_2b_1\end{smallmatrix}\right)
$$
This is given in the formula booklet. An application is the cross product of the base vectors, e.g. $\boldsymbol{i} \times \boldsymbol{j} = \boldsymbol{k}$.

#### Determinant definition of the cross product
Alternatively, the cross product can be worked out using the [[1 - Matrices#Determinant of a 3x3 Matrix|determinant of a 3x3 matrix]]:
$$
\boldsymbol{a} \times \boldsymbol{b} = \left|\begin{smallmatrix}\boldsymbol{i} & a_1 & b_1 \\ \boldsymbol{j} & a_2 & b_2 \\ \boldsymbol{k} & a_3 & b_3\end{smallmatrix}\right|
$$

#### Application to 3x3 matrix inverse
The cross product can be used to find the [[1 - Matrices#Inverse of a 3x3 Matrix|inverse of a 3x3 matrix]], by finding the cross products of columns of $\boldsymbol{A}$:
- Find the first row of $\boldsymbol{A}^{-1}$ by $\boldsymbol{c}_2 \times \boldsymbol{c}_3$
- Find the second row of $\boldsymbol{A}^{-1}$ by $\boldsymbol{c}_3 \times \boldsymbol{c}_1$ (note how this is the other way round)
- Find the third row of $\boldsymbol{A}^{-1}$ by $\boldsymbol{c}_1 \times \boldsymbol{c}_2$
- Divide by $\det \boldsymbol{A}$
