#### Definitions
The **hyperbolic functions** are defined as follows:
$$
\begin{split}
\sinh x &= \frac{e^x - e^{-x}}{2} \\
\cosh x &= \frac{e^x + e^{-x}}{2} \\
\tanh x &\equiv \frac{\sinh x}{\cosh x} \equiv \frac{e^x - e^{-x}}{e^x + e^{-x}}
\end{split}
$$

The graphs of hyperbolic functions are below:
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=1]

  \begin{scope}[shift={(0,0)}]
	\node[align=left] at (0, 3.0) {$y = \sinh{x}$};
	\draw[->] (-2,0) -- (2,0) node[right] {$x$};
	\draw[->] (0,-2) -- (0,2) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=-2:2]
	    plot(\x,{(exp(\x)-exp(-\x))/4});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
  \end{scope}
  
  \begin{scope}[shift={(5,0)}]
	\node[align=left] at (0, 3.0) {$y = \cosh{x}$};
	\draw[->] (-2,0) -- (2,0) node[right] {$x$};
	\draw[->] (0,-2) -- (0,2) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=-2:2]
	    plot(\x,{(exp(\x)+exp(-\x))/4});
	\node at (0, 1/2) [circle,fill,inner sep=1pt]{};
	\node[font=\small\ttfamily, left] at (0, 0.7) {1};
  \end{scope}
  
  \begin{scope}[shift={(10,0)}]
	\node[align=left] at (0, 3.0) {$y = \tanh{x}$};
	\draw[->] (-2,0) -- (2,0) node[right] {$x$};
	\draw[->] (0,-2) -- (0,2) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=-2:2]
	    plot(\x,{(exp(\x)-exp(-\x))/((exp(\x)+exp(-\x)))});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
	\draw[dotted](-2,-1) -- (2,-1);
	\node[font=\small\ttfamily, left] at (0, 1) {1};
	\draw[dotted](-2,1) -- (2,1);
	\node[font=\small\ttfamily, left] at (0, -1) {-1};
  \end{scope}
  
\end{tikzpicture}
\end{document}
```

From these graphs, the domain and range of the hyperbolic functions can be found:
- $\sinh x$ has a domain of $x \in \mathbb{R}$, range of $\sinh x \in \mathbb{R}$.
- $\cosh x$ has a domain of $x \in \mathbb{R}$, range of $\cosh x \ge 1$.
- $\tanh x$ has a domain of $x \in \mathbb{R}$, range of $-1 \le \tanh x \le 1$.

#### Inverse hyperbolic functions
The **inverse hyperbolic functions** are $\DeclareMathOperator{arsinh}{arsinh}\arsinh x$, $\DeclareMathOperator{arcosh}{arcosh}\arcosh x$, and $\DeclareMathOperator{artanh}{artanh}\artanh x$.
The domains and ranges can be found:
- $\DeclareMathOperator{arsinh}{arsinh}\arsinh x$ has a domain of $x \in \mathbb{R}$, range of $\DeclareMathOperator{arsinh}{arsinh}\arsinh x \in \mathbb{R}$.
- $\DeclareMathOperator{arcosh}{arcosh}\arcosh x$ has a domain of $x \ge 1$, range of $\DeclareMathOperator{arcosh}{arcosh}\arcosh x \ge 0$.
- $\DeclareMathOperator{artanh}{artanh}\artanh x$ has a domain of $-1 \le x \le 1$, range of $\DeclareMathOperator{artanh}{artanh}\artanh x \in \mathbb{R}$.

The inverse hyperbolic functions have logarithmic forms that can be proved by using the exponential definition of the hyperbolic functions and solving the hidden quadratic. These are:
- $\DeclareMathOperator{arsinh}{arsinh}\arsinh x = \ln(x + \sqrt{x^2+1})$
- $\DeclareMathOperator{arcosh}{arcosh}\arcosh x = \ln(x + \sqrt{x^2-1})$
- $\DeclareMathOperator{artanh}{artanh}\artanh x = \frac{1}{2}\ln(\frac{1+x}{1-x})$
These are given in the formula book.

#### Hyperbolic identities
The most important hyperbolic identity is:
$$
\cosh^2 x - \sinh^2 x = 1
$$
When proving identities, it is often useful to return to the exponential definitions of $\cosh$, $\sinh$, and $\tanh$. Outside of the syllabus, there is [Osborn's Rule](https://en.wikipedia.org/wiki/George_Osborn_(mathematician)#:~:text=%5B5%5D-,Osborn%27s%20Rule%5Bedit%5D,-Osborn%E2%80%99s%20Rule%20which) for converting normal trigonometric identities into hyperbolic identities.

#### Calculus of hyperbolic functions
The **derivatives** of hyperbolic functions are:
- $\frac{\textrm{d}y}{\textrm{d}x}(\sinh x) = \cosh x$
- $\frac{\textrm{d}y}{\textrm{d}x}(\cosh x) = \sinh x$
- $\frac{\textrm{d}y}{\textrm{d}x}(\tanh x) = \frac{1}{\cosh^2x}$
Only the last one is given. These can be found by returning to the exponential definitions.

The **integrals** of hyperbolic functions are:
- $\int\sinh x\,\textrm{d}x = \cosh x + C$
- $\int\cosh x\,\textrm{d}x = \sinh x + C$
- $\int\tanh x\,\textrm{d}x = \ln{\cosh x} + C$
