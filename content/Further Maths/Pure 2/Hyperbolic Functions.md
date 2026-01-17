#### Definitions
The **hyperbolic functions** are defined as:
$$
\begin{split}
\sinh x &= \frac{e^x - e^{-x}}{2} \\
\cosh x &= \frac{e^x + e^{-x}}{2} \\
\tanh x &= \frac{\sinh x}{\cosh x} = \frac{e^x - e^{-x}}{e^x + e^{-x}}
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
- $\tanh x$ has a domain of $x \in \mathbb{R}$, range of $-1 \lt \tanh x \lt 1$.

#### Inverse hyperbolic functions
The **inverse hyperbolic functions** are $\DeclareMathOperator{arsinh}{arsinh}\arsinh x$, $\DeclareMathOperator{arcosh}{arcosh}\arcosh x$, and $\DeclareMathOperator{artanh}{artanh}\artanh x$, also denoted $\sinh^{-1}x, \cosh^{-1}x$ and $\tanh^{-1} x$ respectively.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=1]

  \begin{scope}[shift={(0,0)}]
	\node[align=left] at (0, 3.0) {$y = $ arsinh$\, x$};
	\draw[->] (-2,0) -- (2,0) node[right] {$x$};
	\draw[->] (0,-2) -- (0,2) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=-2:2]
	    plot(\x,{ln((2 * \x) + sqrt((2 * \x)^2 + 1)) / 1.4});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
  \end{scope}
  
  \begin{scope}[shift={(5,0)}]
	\node[align=left] at (0, 3.0) {$y = $ arcosh$\, x$};
	\draw[->] (-2,0) -- (2,0) node[right] {$x$};
	\draw[->] (0,-2) -- (0,2) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=1/2:2]
	    plot(\x,{ln((2 * \x) + sqrt((2 * \x)^2 - 1)) / 1.2});
	\node at (1/2, 0) [circle,fill,inner sep=1pt]{};
	\node[font=\small\ttfamily, below] at (1/2, 0) {1};
  \end{scope}
  
  \begin{scope}[shift={(10,0)}]
	\node[align=left] at (0, 3.0) {$y = $ artanh$\, x$};
	\draw[->] (-2,0) -- (2,0) node[right] {$x$};
	\draw[->] (0,-2) -- (0,2) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=tanh(-2):tanh(2)]
	    plot(\x,{ln((1 + \x) / (1 - \x)) / 2});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
	\draw[dotted](-1,-2) -- (-1,2);
	\node[font=\small\ttfamily, below] at (-1, 0) {-1};
	\draw[dotted](1,-2) -- (1,2);
	\node[font=\small\ttfamily, below] at (1, 0) {1};
  \end{scope}
  
\end{tikzpicture}
\end{document}
```
The domains and ranges can be found:
- $\DeclareMathOperator{arsinh}{arsinh}\arsinh x$ has a domain of $x \in \mathbb{R}$, range of $\DeclareMathOperator{arsinh}{arsinh}\arsinh x \in \mathbb{R}$.
- $\DeclareMathOperator{arcosh}{arcosh}\arcosh x$ has a domain of $x \ge 1$, range of $\DeclareMathOperator{arcosh}{arcosh}\arcosh x \ge 0$.
- $\DeclareMathOperator{artanh}{artanh}\artanh x$ has a domain of $-1 \lt x \lt 1$, range of $\DeclareMathOperator{artanh}{artanh}\artanh x \in \mathbb{R}$.

The inverse hyperbolic functions have **logarithmic forms** that can be proved by using the exponential definition of the hyperbolic functions and solving the hidden quadratic. These are:
- $\DeclareMathOperator{arsinh}{arsinh}\arsinh x = \ln(x + \sqrt{x^2+1})$
- $\DeclareMathOperator{arcosh}{arcosh}\arcosh x = \ln(x + \sqrt{x^2-1})$
- $\DeclareMathOperator{artanh}{artanh}\artanh x = \frac{1}{2}\ln(\frac{1+x}{1-x})$
These are given in the formula book. Proofs are given below.

#### Hyperbolic identities
The most important **hyperbolic identity** is:
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

#### Derivation of logarithm definitions of inverse hyperbolic functions
The following proofs are given to derive the logarithm definitions of inverse hyperbolic functions. Broadly, all follow a similar idea of completing the square on $e^x$ (this can even be used to find logarithmic definitions of inverse trigonometric functions, which has come up before on past papers).

###### Proof for $\sinh^{-1}x$
$$
\begin{split}
y = \sinh{x} &= \frac{e^x - e^{-x}}{2} \\
2y &= e^x - e^{-x} \\
2ye^x &= e^{2x} - 1 \\
0 &= (e^x)^2 - 2y(e^x) - 1 \\
\\
e^x &= \frac{2y \pm \sqrt{(2y)^2 - 4(-1)}}{2} \\
&= \frac{2y \pm \sqrt{4y^2 + 4}}{2} \\
&= y \pm \sqrt{y^2 + 1} \\
&= y + \sqrt{y^2 + 1} \quad (e^x > 0)\\
x &= \ln{(y + \sqrt{y^2 + 1})}
\end{split}
$$
###### Proof for $\cosh^{-1}x$
$$
\begin{split}
y = \cosh x &= \frac{e^x + e^{-x}}{2} \\
2y &= e^x + e^{-x} \\
2y e^x &= e^{2x} + 1 \\
0 &= (e^x)^2 -2y(e^x) + 1 \\
\\
e^x &= \frac{2y \pm \sqrt{(2y)^2 - 4(1)}}{2} \\
&= \frac{2y \pm \sqrt{4y^2 - 4}}{2} \\
&= y \pm \sqrt{y^2 - 1} \\
&= y + \sqrt{y^2 - 1} \quad (e^x > 0)\\
x &= \ln{(y + \sqrt{y^2 - 1})}
\end{split}
$$
