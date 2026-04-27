## Derivatives
The **derivative** (or gradient function) of a function $f(x)$, is another function, $f'(x)$ that gives the gradient of the graph of $y = f(x)$ at any point with x-coordinate $x$. The gradient at any point of $f(x)$ is the gradient of the tangent at that point.

The derivative itself can be graphed:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\begin{document}
\begin{tikzpicture}
  \draw[->] (-3, 0) -- (3, 0) node[right] {$x$};
  \draw[->] (0, -2) -- (0, 2) node[above] {$y$};
  \draw[scale=0.35, domain=-5.7:1.6, smooth, variable=\x, black] plot ({\x}, {0.3*\x*\x*\x+1.6*\x*\x+0.5*\x+0.5});
  \draw[scale=0.35, domain=-4.9:1.4, smooth, variable=\x, red]  plot ({\x}, {0.9*\x*\x+3.2*\x+0.5});
\end{tikzpicture}
\end{document}
```

The relationship between the graph of a function and its derivative are:
- When the graph is increasing, the gradient is positive.
- When the graph is decreasing, the gradient is negative.
- When the tangent is horizontal, the gradient is zero. This is a **stationary point**.

#### Differentiation from first principles
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=135:\color{black}$#2$]at (#1){};}

\begin{document}
\begin{tikzpicture}
  \draw[scale=1.0, domain=-2:5, smooth, variable=\x, black] plot ({\x}, {0.2*\x*\x});
  \labelledpoint{1, 0.2}{P(x{,}x^2)}
  \labelledpoint{4, 3.2}{Q(x+h{,}(x+h)^2)}
  \draw[dotted, thick](1, 0.2) -- (4, 3.2);

\end{tikzpicture}
\end{document}
```
A chord is a line segment between two points on a curve, e.g. PQ above.
The idea behind **differentiation from first principles** is to consider the gradient of a chord, as the chord becomes smaller and smaller to find the gradient of the function at that point. This gives the (*given*) formula:
$$
f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$

#### Second derivatives
The derivative has $\frac{\text{d}y}{\text{d}x}$ has two interpretations:
- It is the gradient of the graph of $y$ against $x$.
- It measures the rate of change of $y$ with respect to $x$.

Therefore, to calculate the **gradient** (or rate of change) at any particular point, substitute the value of $x$ into the equation for the derivative.

#### Increasing and decreasing functions
The sign of the gradient at a point shows whether the function is increasing or decreasing:
- If the gradient is positive, the function is **increasing**.
- If the gradient is negative, the function is **decreasing**.

#### Higher derivatives
The derivative $\frac{\text{d}y}{\text{d}x}$ can be differentiated with respect to $x$. This gives the **second derivative**, denoted $\frac{\text{d}^2y}{\text{d}x^2}$ or $f''(x)$. The second derivative measures the gradient of the gradient, or the rate of change of the gradient with respect to $x$.

## AS differentiation rules
For a general function $y = x^n$:
$$
\frac{\text{d}y}{\text{d}x} = nx^{n-1}
$$
If $y = kf(x)$, where $k$ is a constant:
$$
\frac{\text{d}y}{\text{d}x} = kf'(x)
$$

If $y = f(x) + g(x)$:
$$
\frac{\text{d}y}{\text{d}x} = f'(x) + g'(x)
$$

These rules show how to differentiate powers, how to differentiate a function multiplied by a constant, and how to differentiate a sum.

Because of the power rule for the derivative of $x^n$, it is useful to rearrange function into the form $ax^n$ before differentiating them, by applying the laws of indices.

## Tangents and normals
The normal to a curve at a given point is a line that crosses the curve at that point and is perpendicular to the tangent:
```tikz
\usetikzlibrary{calc, angles, quotes}

\begin{document}
\begin{tikzpicture}[>=stealth, scale=1.5]
    \def\px{1.5}
    \def\py{0.3375} % 0.1 * 1.5^3
    \def\m{0.675}
    \def\mnormal{-1.481}

    \draw[->] (-1,0) -- (4,0) node[right, black] {$x$};
    \draw[->] (0,-1) -- (0,3) node[above, black] {$y$};

    \draw[thick, black, domain=-0.5:3, samples=100] 
        plot (\x, {0.1*\x^3}) 
        node[right] {$y = f(x)$};

    \draw[blue, thick, domain=0.2:3] 
        plot (\x, {\m*(\x - \px) + \py}) 
        node[above right] {Tangent};

    \draw[red, thick, domain=0.5:2.5] 
        plot (\x, {\mnormal*(\x - \px) + \py}) 
        node[below] {Normal};

    \filldraw[black] (\px, \py) circle (1.5pt) node[above left, xshift=-6pt] {$P$};
    \node[anchor=west, align=left] at (0, 2.5) {
        Tangent: Slope $m = f'(x)$ \\
        Normal: Slope $-\frac{1}{f'(x)}$
    };
\end{tikzpicture}
\end{document}
```

The gradient of the normal can be found by considering that for two perpendicular lines with gradients $m_1$ and $m_2$, $m_1m_2 = -1$.

For a point on $y = f(x)$:
- The gradient of the tangent is $f'(x)$,
- The gradient of the normal is $-\frac{1}{f'(x)}$

## Stationary points
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\begin{document}
\begin{tikzpicture}
  \draw[->] (-3, 0) -- (3, 0) node[right] {$x$};
  \draw[->] (0, -0.5) -- (0, 3) node[above] {$y$};
  \draw[scale=0.5, domain=-5.21:1.6, smooth, variable=\x, black] plot ({\x}, {0.3*\x*\x*\x+1.6*\x*\x+0.5*\x+0.5});
  \draw[scale=0.5, domain=-4.9:-1.9, smooth, variable=\x, red]  plot ({\x}, {5.5049});
  \draw[scale=0.5, domain=-1.5:1.5, smooth, variable=\x, red]  plot ({\x}, {0.45971});

\end{tikzpicture}
\end{document}
```
At **local maxima** and **minima**, $\frac{\text{d}y}{\text{d}x} = 0$. These are local because it is possible that there are several points that have a gradient of zero - these are all stationary points.

To determine the nature of the stationary points, the second derivative can be used:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\begin{document}
\begin{tikzpicture}
  \begin{scope}[shift={(0,0)}]
    \draw[domain=-2:2, smooth, variable=\x] 
        plot (\x, {\x*\x - 2});

    \fill[black] (0, -2) circle (2pt) node[below right] {$\frac{\mathrm{d}x}{\mathrm{d}y} = 0$};
    \draw[dashed, black] (-2.5, -2) -- (2.5, -2) node[above left] {};

    \fill[black] (-1.5, 0.25) circle (2pt) node[left] {$\frac{\mathrm{d}x}{\mathrm{d}y} < 0$};
    \fill[black] (1.5, 0.25) circle (2pt) node[right] {$\frac{\mathrm{d}x}{\mathrm{d}y} > 0$};
  \end{scope}

  \begin{scope}[shift={(6,0)}]
    \draw[domain=-2:2, smooth, variable=\x] 
        plot (\x, {-1 * (\x*\x - 2)});

    \fill[black] (0, 2) circle (2pt) node[above right] {$\frac{\mathrm{d}x}{\mathrm{d}y} = 0$};
    \draw[dashed, black] (-2.5, 2) -- (2.5, 2) node[below left] {};

    \fill[black] (-1.5, -0.25) circle (2pt) node[left] {$\frac{\mathrm{d}x}{\mathrm{d}y} > 0$};
    \fill[black] (1.5, -0.25) circle (2pt) node[right] {$\frac{\mathrm{d}x}{\mathrm{d}y} < 0$};
  \end{scope}
\end{tikzpicture}
\end{document}
```

Given a stationary point:
- If $\frac{\text{d}^2x}{\text{d}y^2} < 0$ at that point, then it is a local maximum.
- If $\frac{\text{d}^2x}{\text{d}y^2} > 0$ at that point, then it is a local minimum.
- If $\frac{\text{d}^2x}{\text{d}y^2} = 0$ at that point, then a conclusion cannot be reached.

## Concavity and points of inflection
**Concave** and **convex** describe functions that bend upwards or downwards:
- A function is **concave** on an interval if $f''(x) \lt 0$ in that interval.
- A function is **convex** on an interval if $f''(x) \gt 0$ in that interval.
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth]
\begin{scope}[shift={(0,0)}]
	\draw[->] (-0.5,0) -- (4,0) node[right] {$x$};
	\draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
	\draw[very thick, domain=0.5:3.5, samples=100] 
		plot (\x, {-0.6*(\x-1.5)*(\x-1.5) + 2.5});
	\node[] at (2, 3.5) {Concave};
	\node[align=center] at (2, -0.5) {$f''(x) < 0$};
\end{scope}

\begin{scope}[shift={(5,0)}]
	\draw[->] (-0.5,0) -- (4,0) node[right] {$x$};
	\draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
	\draw[very thick, domain=0.5:3.5, samples=100] 
		plot (\x, {0.6*(\x-1.5)*(\x-1.5) + 0.2});
	\node[] at (2, 3.5) {Convex};
	\node[align=center] at (2, -0.5) {$f''(x) > 0$};
\end{scope}
\end{tikzpicture}
\end{document}
```
A (semi-useful) mnemonic to remember this is that 'a caveman lives in a concave cave'.  

A **point of inflection** occurs when $f''(x) = 0$ and the sign of $f''(x)$ changes either side, i.e. $f(x)$ goes from being concave to convex, or vice versa. A point of inflection can be stationary (if $f'(x) = 0$), or non-stationary (otherwise).
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth]
    \begin{scope}[shift={(0,0)}]
    	\node[] at (0, 3.25) {Stationary point of inflection};
        \draw[->] (-2.5,0) -- (2.5,0) node[right, black] {$x$};
        \draw[->] (0,-2.5) -- (0,2.5) node[above, black] {$y$};
        \draw[thick, domain=-1.35:1.35, samples=150] 
            plot (\x, {\x*\x*\x}) 
            node[right=2pt] {$y = f(x)$};
        \draw[dashed] (-1.8, 0) -- (1.8, 0);
        \filldraw[black] (0,0) circle (2pt) node[below left=2pt] {$P$};
        \node[below right, align=left, xshift=4pt] at (0, 0) {$g''(0) = 0$\\$g'(0)=0$};
    \end{scope}

    \begin{scope}[shift={(6, 0)}]
	    \node[] at (0, 3.25) {Non-stationary point of inflection};
        \draw[->] (-2.5,0) -- (2.5,0) node[right, black] {$x$};
        \draw[->] (0,-2.5) -- (0,2.5) node[above, black] {$y$};
        \draw[thick,domain=-1.35:1.35, samples=150] 
            plot (\x, {-\x*\x*\x + 3*\x}) 
            node[right=2pt] {$y = g(x)$};
        \filldraw[black] (0,0) circle (2pt) node[below right=2pt] {$Q$};
        \node[below left, align=left, xshift=-4pt] at (0, 0) {$g''(0) = 0$\\$g'(0)\neq0$};
    \end{scope}
\end{tikzpicture}
\end{document}
```

## A2 differentiation rules
The **chain rule** is used to differentiate composite functions (it is *not given*):
$$
\begin{split}
\frac{\text{d}}{\text{d}x}(f(g(x))) &= f'(g(x))\,g'(x) \\\\
\text{or}\quad \frac{\text{d}y}{\text{d}x} &= \frac{\text{d}y}{\text{d}u} \times \frac{\text{d}u}{\text{d}x}
\end{split}
$$

The **product rule** is used to differentiate products of functions (it is *not given*):
$$
\frac{\text{d}}{\text{d}x}(f(x)\,g(x)) = f(x)\,g'(x) + g(x)\,f'(x)
$$
It can be remembered as 'left d-right plus right d-left'.

The **quotient rule** is used to differentiate quotients of functions (it is *given*):
$$
\frac{\text{d}}{\text{d}x}\left(\frac{u}{v}\right) = \frac{v\frac{\text{d}u}{\text{d}x} - u\frac{\text{d}v}{\text{d}x}}{v^2}
$$

The below derivatives are expected to be *known*:
$$
\begin{split}
\frac{\text{d}}{\text{d}x}(\sin x) = \cos x \\
\frac{\text{d}}{\text{d}x}(\cos x) = -\sin x
\end{split}
$$

While the remaining trig derivatives are *given*:
$$
\begin{align*}
\frac{\mathrm{d}}{\mathrm{d}x} \tan(x) &= \sec^2(x) \\
\frac{\mathrm{d}}{\mathrm{d}x} \sec(x) &= \sec(x)\tan(x) \\
\frac{\mathrm{d}}{\mathrm{d}x} \cot(x) &= -\operatorname{cosec}^2(x) \\
\frac{\mathrm{d}}{\mathrm{d}x} \csc(x) &= -\operatorname{cosec}(x)\cot(x)
\end{align*}
$$

#### Examples
Below are examples for the A2 differentiation rules:
$$
\begin{align*}
\frac{\mathrm{d}}{\mathrm{d}x} \sec(5x) &= 5\sec(5x)\tan(5x) && \text{(Chain rule)} \\\\

\frac{\mathrm{d}}{\mathrm{d}x} \sin(x^2 + 1) &= 2x \cos(x^2 + 1) && \text{(Chain rule)} \\\\

\frac{\mathrm{d}}{\mathrm{d}x} \tan^3(x) &= 3\tan^2(x)\sec^2(x) && \text{(Chain rule)} \\\\

\frac{\mathrm{d}}{\mathrm{d}x} (x^2 e^{3x}) &= 3x^2 e^{3x} + 2xe^{3x} && \text{(Product rule)} \\\\

\frac{\mathrm{d}}{\mathrm{d}x} \left( \frac{\ln(x)}{x} \right) &= \frac{1 - \ln(x)}{x^2} && \text{(Quotient rule)}
\end{align*}
$$

#### Connected rates of change
For **connected rates of change**, the following relations are used:
$$
\begin{align}
\frac{\text{d}y}{\text{d}x} &= \frac{\text{d}y}{\text{d}u} \times \frac{\text{d}u}{\text{d}x} \\\\

\frac{\text{d}y}{\text{d}x} &= 1 \div \frac{\text{d}x}{\text{d}y}
\end{align}
$$
