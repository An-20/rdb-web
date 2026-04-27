## Exponentials
**Exponential functions** take the form $y = a^x$. Their features include:
- A $y$-intercept of $(0, 1)$
- All $y \gt 0$
- The $x$-axis as an asymptote.
- If $a \gt 1$, then $y$ increases as $x$ increases, giving **exponential growth**.
- If $0 \lt a \lt 1$, then $y$ decreases as $x$ increases, giving **exponential decay**.

```tikz
\begin{document}
\begin{tikzpicture}[>=stealth]
    \draw[->] (-4,0) -- (4,0) node[right] {$x$};
    \draw[->] (0,-0.5) -- (0,3.2) node[above] {$y$};
    
    \draw[thick, blue, domain=-4:2.8, samples=100] 
        plot (\x, {pow(1.45, \x)}) 
        node[right] {$a > 1$};

    \draw[thick, red, dashed, domain=-2.8:4, samples=100] 
        plot (\x, {pow(1.45, -\x)}) 
        node[right, yshift=14pt, xshift=-28pt] {$0 < a < 1$};

    \filldraw[black] (0,1) circle (1.5pt) node[above right] {$(0,1)$};
    \node[blue, anchor=west] at (1.5, 3.3) {Growth};
    \node[red, anchor=east] at (-1.5, 3.3) {Decay};
\end{tikzpicture}
\end{document}
```

#### Modelling
Exponential functions are used to model situations where the rate of growth or decay is **proportional to the current amount**. This is because the derivative of $e^{kx}$ is $ke^{kx}$. A model with equation $y = Ae^{kt}$ has:
- Initial value ($t=0$) of $y = A$
- A rate of change of $ky$.

## Logarithms
**Logarithms** are the inverse of exponentials. Below are rules of logarithms:
- Converting: $a^b = c \iff \log_a c = b$
- Multiplication$: \log_b(xy) = \log_b x + \log_b y$
- Division: $\log_b(\frac{x}{y}) = \log_b x - \log_b y$
- Exponentiation: $\log_b(x^y) = y\log_b x$

Other required knowledge:
- For any base, $\log_a a = 1$ and $\log_a 1 = 0$
- Logarithms in base $e$ are written as $\ln x$.
- Logarithms in base 10 are written as $\log x$.

A logarithmic function of the form $y = \log_b(x)$ has:
- An $x$-intercept of $(1, 0)$
- The $y$-axis as an asymptote.

```tikz
\begin{document}
\begin{tikzpicture}[>=stealth]
    \draw[->] (-0.5,0) -- (5,0) node[right] {$x$};
    \draw[->] (0,-3) -- (0,2) node[above] {$y$};

    \draw[thick, red, domain=0.05:4.5, samples=200] 
        plot (\x, {ln(\x)}) 
        node[right] {$y = \ln(x)$};

    \filldraw[black] (1,0) circle (1.5pt) node[below right] {$(1,0)$};
    
    \draw[dotted] (2.718, 0) -- (2.718, 1) -- (0, 1);
    \node[below, font=\small] at (2.718, 0) {$e$};
    \node[left, font=\small] at (0, 1) {$1$};
    \filldraw[black] (2.718,1) circle (1pt);
\end{tikzpicture}
\end{document}
```

#### Straightening graphs
###### Exponential
For a graph $y = Ab^x$, taking $\ln$ on both sides gives:
$$
\ln y = x\ln b + \ln A
$$
Thus when plotting $\ln y$ against $x$, the gradient is $\ln b$ and $y$-intercept is $\ln A$.
###### Polynomial
For a graph $y = Ax^b$, taking $\ln$ on both sides gives:
$$
\ln y = b\ln x + \ln A 
$$
Thus when plotting $\ln y$ against $\ln x$, the gradient is $b$ and the $y$-intercept is $\ln A$.
