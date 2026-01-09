#### Polar coordinates
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\node at (-0.4,-0.4) {$0$};
	\foreach \r in {1,2,3} {
		\draw (0,0) circle (\r);
		\node[above right] at (\r,0) {$\r$};
	}
	\foreach \k in {0,...,11} {
		\draw (0,0) -- ({30*\k}:3.5);
	}
	\foreach \k/\lbl in {
		0/{0},
		1/{\frac{\pi}{6}},
		2/{\frac{\pi}{3}},
		3/{\frac{\pi}{2}},
		4/{\frac{2\pi}{3}},
		5/{\frac{5\pi}{6}},
		6/{\pi},
		7/{\frac{7\pi}{6}},
		8/{\frac{4\pi}{3}},
		9/{\frac{3\pi}{2}},
		10/{\frac{5\pi}{3}},
		11/{\frac{11\pi}{6}}
	} {
		\node at ({30*\k}:3.8) {$\lbl$};
	}
	
	\labelledpoint{0.71,0.71}{A_1}
\end{tikzpicture}
\end{document}
```
Polar coordinates have each point labelled by the ordered pair $(r, \theta)$, where $r$ is the **distance from the origin** (or pole) and $\theta$ is the **angle from the initial line**. By convention, the initial line is taken to be in the direction of the positive $x$-axis, and the angle is measured anticlockwise. $\theta$ is typically taken to be between $0$ and $2\pi$.

A polar equation of a curve is a relationship between $r$ and $\theta$. Below are two examples of polar curves.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[scale=0.6, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
  \begin{scope}[shift={(0,0)}]
	\foreach \r in {1,2,3} {
		\draw (0,0) circle (\r);
		\node[above right] at (\r,0) {$\r$};
	}
	\foreach \k in {0,...,11} {
		\draw (0,0) -- ({30*\k}:3.5);
	}
	\foreach \k/\lbl in {
		0/{0},
		1/{\frac{\pi}{6}},
		2/{\frac{\pi}{3}},
		3/{\frac{\pi}{2}},
		4/{\frac{2\pi}{3}},
		5/{\frac{5\pi}{6}},
		6/{\pi},
		7/{\frac{7\pi}{6}},
		8/{\frac{4\pi}{3}},
		9/{\frac{3\pi}{2}},
		10/{\frac{5\pi}{3}},
		11/{\frac{11\pi}{6}}
	} {
		\node at ({30*\k}:3.8) {$\lbl$};
	}
	\draw[thick, blue, samples=200, domain=0:360]
		plot ({2.5*cos(\x)}, {2.5*sin(\x)});
	\node[align=left] at (0, -5) {r\,=\,2};
  \end{scope}
  
    \begin{scope}[shift={(10,0)}]
	\foreach \r in {1,2,3} {
		\draw (0,0) circle (\r);
		\node[above right] at (\r,0) {$\r$};
	}
	\foreach \k in {0,...,11} {
		\draw (0,0) -- ({30*\k}:3.5);
	}
	\foreach \k/\lbl in {
		0/{0},
		1/{\frac{\pi}{6}},
		2/{\frac{\pi}{3}},
		3/{\frac{\pi}{2}},
		4/{\frac{2\pi}{3}},
		5/{\frac{5\pi}{6}},
		6/{\pi},
		7/{\frac{7\pi}{6}},
		8/{\frac{4\pi}{3}},
		9/{\frac{3\pi}{2}},
		10/{\frac{5\pi}{3}},
		11/{\frac{11\pi}{6}}
	} {
		\node at ({30*\k}:3.8) {$\lbl$};
	}
	\draw[thick, blue, samples=300, smooth, domain=0:360]
		plot (
			{sqrt(\x*pi/180)*cos(\x)},
			{sqrt(\x*pi/180)*sin(\x)}
		);
	\node[align=left] at (0, -5) {$r\,=\,\sqrt\theta$};
  \end{scope}
\end{tikzpicture}
\end{document}
```

For some curves, there might be values for $\theta$ for which the $r$ is not defined. If $r$ is negative, then the curve is not defined. Some calculators still plot parts of the curve with negative $r$, but *for this course $r$ must be positive for the curve to be defined*.

##### Features of polar curves
**Minima and maxima**
As $r$ is a function of $\theta$, the **minimum and maximum** values of $r$ are when $\frac{\textrm{d}r}{\textrm{d}\theta} = 0$. For curves where $r$ is defined in terms of trigonometric functions, it may be easier to consider the graphs or ranges of the functions instead of differentiating.

**Tangents at the pole**
Consider the graph of $r = 3\sin2\theta$ below. The value of $r$ changes from positive to negative for $\theta = 0,\frac{\pi}{2},\pi,\frac{3\pi}{2}$. As the curve approaches these values of $\theta$, $r$ gets closer to 0, so points on the curve get closer to the pole. Thus, each of the half-lines (in red) $\theta = 0,\frac{\pi}{2},\pi,\frac{3\pi}{2}$ is tangent to the curve at the pole.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[scale=0.6, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\foreach \r in {1,2,3} {
		\draw (0,0) circle (\r);
		\node[above right] at (\r,0) {$\r$};
	}
	\foreach \k in {0,...,11} {
		\draw (0,0) -- ({30*\k}:3.5);
	}
	\foreach \k in {0,...,3} {
		\draw[red] (0,0) -- ({90*\k}:3);
	}
	\foreach \k/\lbl in {
		0/{0},
		1/{\frac{\pi}{6}},
		2/{\frac{\pi}{3}},
		3/{\frac{\pi}{2}},
		4/{\frac{2\pi}{3}},
		5/{\frac{5\pi}{6}},
		6/{\pi},
		7/{\frac{7\pi}{6}},
		8/{\frac{4\pi}{3}},
		9/{\frac{3\pi}{2}},
		10/{\frac{5\pi}{3}},
		11/{\frac{11\pi}{6}}
	} {
		\node at ({30*\k}:3.8) {$\lbl$};
	}
	\draw[thick, blue, samples=200, smooth, domain=0:90]
		plot (
			{3*sin(2*\x)*cos(\x)},
			{3*sin(2*\x)*sin(\x)}
		);
	
	\draw[thick, blue, samples=200, smooth, domain=180:270]
		plot (
			{3*sin(2*\x)*cos(\x)},
			{3*sin(2*\x)*sin(\x)}
		);
	\node[align=left] at (0, -5) {$r\,=\,3\sin2\theta$};
\end{tikzpicture}
\end{document}
```
For a curve with polar equation $r = f(\theta)$, the line $\theta = a$ is a **tangent at the pole** if $f(a) = 0$ and $f(a) \gt 0$ on one side of the line.

##### Changing between polar and Cartesian
Trigonometry can be used to change between polar and Cartesian coordinates.:
- A point with polar coordinates $(r,\theta)$ has Cartesian coordinates $(r\cos\theta,r\sin\theta)$.
- A point with Cartesian coordinates $(x,y)$ has $r$ and $\theta$ satisfying $\sqrt{x^2 + y^2} = r$ and $\tan\theta = \frac{y}{x}$.
This is effectively the same method as changing between the Cartesian and modulus-argument form of a [[Complex Numbers#Converting forms|complex number]].

##### Area enclosed by a polar curve
The area between a polar curve and the half-lines $\theta=\alpha$ and $\theta=\beta$ is given by:
$$
\int_\alpha^\beta \frac{1}{2}r^2\,\textrm{d}\theta
$$
