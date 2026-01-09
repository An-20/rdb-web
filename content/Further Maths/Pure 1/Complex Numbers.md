## Overview
There is no real number $x$ that solves $x^2 = -1$. Mathematicians created an 'imaginary' number that solves this equation. The **imaginary unit**, $i = \sqrt(-1)$, so $i^2 = -1$.  $i$ behaves like a normal constant, with the special property of $i^2 = -1$.

The set of **real numbers**, $\mathbb{R}$, are all the numbers that lie upon a one-dimensional continuum, including all the integers, rational, and irrational numbers. The set of complex numbers is denoted by $\mathbb{C}$. **Complex numbers** can be written as $a + bi$, where $a$ and $b$ are real numbers. Typically, $z$ is used to denote a complex number.

For $z = a + bi$, $a$ is the real part of $z$ and $b$ is the imaginary part of $z$. This can be written as:
- $\Re(z) = a$
- $\Im(z) = b$
($\Re$ is a stylised 'Re' and $\Im$ is a stylised 'Im').

An 'imaginary number' (sometimes 'pure imaginary number') is just the product of a real number and the imaginary unit $i$, e.g. $5i$ or $-12.7i$. The 'imaginary part' of a complex number is only the real coefficient on $i$.

#### Basic Arithmetic
When doing arithmetic with complex numbers, $i$ can be treated as a constant. Then, any powers of $i$ can be simplified.

Examples:
- Addition: $a + bi + c + di = a + c + (b + d)i$
- Subtraction: $(a + bi) - (c + di) = a - c + (b - d)i$
- Multiplication: $(a + bi)(c + di) = ac + adi + bci + bdi^2 = ac - bd + (ad + bc)i$
- Division by a constant: $\frac{a + bi}{k} = \frac{a}{k} + \frac{b}{k}i$

#### Complex Roots
Complex numbers were originally 'invented' to solve quadratics with negative discriminants. Given a quadratic, the quadratic formula gives the solutions:
$$
x = \frac{-b \pm \sqrt{b^2-4ac}}{2a}
$$

Where the discriminant $b^2-4ac$ is negative, the result of taking the square root will give an imaginary number (two imaginary numbers given the $\pm$). Therefore if the discriminant is negative, there are two complex roots.

For example:
$$
\begin{split}
x^2 -4x +6 &= 0
\\ x &= \frac{4 \pm \sqrt{16 - 24}}{2}
\\ x &= \frac{4 \pm \sqrt{-8}}{2}
\\ x &= \frac{4 \pm 2\sqrt{2}i}{2}
\\ x &= 2 \pm \sqrt{2}i
\end{split}
$$

#### Comparing coefficients
A complex number is zero if and only if both the real and imaginary parts are zero.
If two complex numbers are equal, then their real parts and imaginary parts are the same.

# Complex Conjugate
If $z = a + bi$, then the **complex conjugate** of $z$, denoted $z^*$, is $a - bi$.

To divide two complex numbers, multiply the numerator and denominator by the complex conjugate:
$$
\begin{split}
\frac{a+bi}{c+di}&=\frac{a+bi}{c+di}\times\frac{c-di}{c-di}
\\&=\frac{ac - adi + bci + bd}{c^2 + d^2}
\\&=\frac{ac + bd + (bc-ad)i}{c^2 + d^2}
\end{split}
$$
The complex conjugate also extends the idea of the difference of two squares into the **sum of two squares**:
$$
\begin{split}
x^2-y^2 &= (x+y)(x-y)
\\x^2 + y^2 &= (x+iy)(x-iy)
\end{split}
$$
# Argand Diagrams
Complex numbers can be represented on an **Argand diagram**, which has an imaginary axis perpendicular to the real axis.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]

	\draw[step=1cm,gray,very thin] (-3.75,-3.75)grid(3.75,3.75);
	\draw[->, very thick](-3.75,0) -- (3.75,0);
	\draw[->, very thick](0,-3.75) -- (0,3.75);

	\coordinate[label=left:$Im$](A) at (0, 3.75);
	\coordinate[label=below:$Re$](A) at (3.75, 0);

	\node[fill=white] at (-0.4,-0.4){0};
	\labelledpoint{1, 2}{1 + 2i}

\end{tikzpicture}
\end{document}
```

Adding complex numbers on an Argand diagram looks like adding vectors:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]

	\draw[step=1cm,gray,very thin] (-3.75,-3.75)grid(3.75,3.75);
	\draw[->, very thick](-3.75,0) -- (3.75,0);
	\draw[->, very thick](0,-3.75) -- (0,3.75);

	\coordinate[label=left:$Im$](A) at (0, 3.75);
	\coordinate[label=below:$Re$](A) at (3.75, 0);

	\node[fill=white] at (-0.4,-0.4){0};
	\labelledpoint{1, 2}{1 + 2i}
	\labelledpoint{2, -2}{2 - 2i}
	\draw[dotted, ->, very thick](0, 0) -- (1, 2);
	\draw[dotted, ->, very thick](0, 0) -- (2, -2);
	\draw[dotted, ->, very thick](1, 2) -- (3, 0);
	\draw[dotted, ->, very thick](2, -2) -- (3, 0);
	\coordinate[label=above:$(1 + 2i) + (2 - 2i)$](A) at (3, 0);

\end{tikzpicture}
\end{document}
```

Taking a complex conjugate results in a reflection in the real axis:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]

	\draw[step=1cm,gray,very thin] (-3.75,-3.75)grid(3.75,3.75);
	\draw[->, very thick](-3.75,0) -- (3.75,0);
	\draw[->, very thick](0,-3.75) -- (0,3.75);

	\coordinate[label=left:$Im$](A) at (0, 3.75);
	\coordinate[label=below:$Re$](A) at (3.75, 0);

	\node[fill=white] at (-0.4,-0.4){0};
	\labelledpoint{2, 3}{z}
	\labelledpoint{2, -3}{z^*}
	\draw[->, very thick](0, 0) -- (2, 3);
	\draw[->, very thick](0, 0) -- (2, -3);
	\draw[dotted, thick](2, 3) -- (2, -3);

\end{tikzpicture}
\end{document}
```

A circle with centre $a$ and radius $r$ is given by $|z - a| = r$. 
A perpendicular bisector of the line connecting $a$ and $b$ is given by $|z - a| = |z - b|$.
A half-line starting at (but not including) $a$ and making angle $\theta$ to the positive real axis is given by $\arg(z - a) = \theta$.
Vertical and horizontal lines are given by equations of the form $\Re(z) = k$ and $\Im(z) = k$ respectively.

## Modulus-argument Form
A complex number can be uniquely be described by two values:
- The **modulus**, $|z|$ or $r$, is the distance from the origin
- The **argument**, $\arg(z)$ or $\theta$, is the angle in radians anticlockwise from the positive real axis.
A complex number can be expressed in modulus-argument form as $\DeclareMathOperator{cis}{cis}r \cis \theta = r(\cos \theta + i \sin \theta)$.
#### Converting forms
To convert from **Cartesian form** $z = a + bi$ to **modulus-argument form**:
- $r = |z| = \sqrt{a^2 + b^2}$
- $\theta = \arg{z} = \tan^{-1}{\frac{b}{a}}$ (taking care to ensure the correct angle is used).

To convert from modulus-argument form $\DeclareMathOperator{cis}{cis}r \cis \theta$ to Cartesian form $a + bi$:
- $a = r \cos \theta$
- $b = r \sin \theta$.
#### Operations
To multiply in modulus-argument form, multiply the moduli and add the arguments.
$$
zw = |z||w|\cis(\arg(z) + \arg(w))
$$

To divide in modulus-argument form, divide the moduli and subtract the arguments.
$$
\frac{z}{w} = \frac{|z|}{|w|}\cis(\arg(z) - \arg(w))
$$
