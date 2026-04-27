## Overview
$$
\intop f(x)\,dx = F(x) + C \iff f(x) = \frac{d}{dx}F(x)
$$
The **Fundamental Theorem of Calculus** states that integration is the reverse of differentiation. 

An **indefinite integral** has no limits, and is an infinite family of functions differing by some constant of integration, $C$. The constant of integration can be found if a value of $F(x)$ for a given $x$ is known.

The **definite integral** $\intop^b_a f(x) dx$ is found by evaluating the integrated expression at the upper limit $b$ and subtracting the integrated expression evaluated at the lower limit $a$. This gives the signed area. If the integrand changes sign between the two limits, then the interval needs to be split to find the total area.
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth, scale=1.3]
    \def\xa{1.0}
    \def\xc{3.0}
    \def\xb{5.0}
    
    \begin{scope}
        \fill[blue!20] (1,0) -- plot[domain=1:3, samples=100] (\x, {-0.5*(\x-1)*(\x-3)*(\x-5)}) -- (3,0) -- cycle;
    \end{scope}

    \begin{scope}
        \fill[red!20] (3,0) -- plot[domain=3:5, samples=100] (\x, {-0.5*(\x-1)*(\x-3)*(\x-5)}) -- (5,0) -- cycle;
    \end{scope}

    \draw[thick, black, domain=0.6:5.3, samples=150] 
        plot (\x, {-0.5*(\x-1)*(\x-3)*(\x-5)});
    \node[anchor=west] at (5.3, 1.5) {$y = f(x)$};

    \draw[thick, ->] (-0.5,0) -- (6.0,0) node[right] {$x$};
    \draw[thick, ->] (0,-1.5) -- (0,2.5) node[above] {$y$};

    \draw[dashed] (\xa, 0) -- (\xa, 0) node[below, xshift=-14pt, font=\small] {$a=1$};
    \draw[dashed] (\xb, 0) -- (\xb, 0) node[below, xshift=-12pt, font=\small] {$b=5$};
    \filldraw[black] (\xc, 0) circle (1.5pt) node[below, xshift=12pt, font=\small] {$c=3$};
    
    \draw[thick] (\xa, 0.1) -- (\xa, -0.1);
    \draw[thick] (\xb, 0.1) -- (\xb, -0.1);
    
    \node[blue!80!black, font=\large] at (2.0, -0.2) {$A_1$};
    \node[blue!80!black, font=\small, align=center] at (2.0, -0.7) {$f(x) < 0$ \\ $A_1 < 0$};

    \node[red!80!black, font=\large] at (4.0, 1) {$A_2$};
    \node[red!80!black, font=\small, align=center] at (4.0, 0.5) {$f(x) > 0$ \\ $A_2 > 0$};

    \node[anchor=north, align=left] at (3.0, 3.3) {
        $\displaystyle \int_a^b f(x) \, dx = A_1 + A_2$ \\\\
        $\text{Total area} = |A_1| + |A_2|$
    };

\end{tikzpicture}
\end{document}
```

The **area between two curves** can be found with a single integral. For two curves $f(x$) and $g(x)$, provided that $f(x) \gt g(x)$ for $a \lt x \lt b$ (the curves do not intersect), the area bounded by the two curves,$x=a$, and $x=b$ is given by:
$$
\text{Area} = \int^a_b(f(x) - g(x))\,\textrm{d}x
$$
This can be shown visually:
```tikz
\usetikzlibrary{shapes.misc}

\tikzset{
    function f/.style={thick, color=blue},
    function g/.style={thick, color=red},
}

\begin{document}
\begin{tikzpicture}[>=stealth]
    \def\xa{0.6}
    \def\xb{3.3}
    \def\ftop#1{ -0.6*(#1-2)*(#1-2) + 2.5 }
    \def\gbot#1{ 0.7*(#1-1.3)*(#1-1.3) + 0.8 }

    \coordinate (Pa) at (0.6, 1.33);
    \coordinate (Pb) at (3.3, 1.48);

    \def\pathf{ (Pa) .. controls (1.5, 3.0) and (2.5, 3.0) .. (Pb) }
    \def\pathg{ (Pa) .. controls (1.0, 0.6) and (2.0, 1.2) .. (3.0, 1.0) .. controls (3.2, 1.0) .. (Pb) }

    \fill[blue!20] (Pa) .. controls (1.5, 3.0) and (2.5, 3.0) .. (Pb) --
                (Pb) .. controls (3.2, 1.0) .. (3.0, 1.0) .. controls (2.0, 1.2) and (1.0, 0.6) .. (Pa) --
                cycle;

    \draw[function f] \pathf;
    \draw[function g] \pathg;
    \draw[function g, ->] (0, 3.5) .. controls (0.2, 2.0) .. (Pa);
    \draw[function f, ->] (0, -0.2) .. controls (0.2, 0.2) .. (Pa);
    \draw[function g, ->] (Pb) .. controls (3.6, 2.0) .. (3.8, 2.2);

    \draw[thick, ->] (-0.3,0) -- (4.2,0) node[right] {$x$};
    \draw[thick, ->] (0,-0.3) -- (0,4.2) node[above] {$y$};
    \node[below left] at (0,0) {$O$};

    \draw[dashed, thin] (\xa, 0) -- (Pa);
    \draw[dashed, thin] (\xb, 0) -- (Pb);
    \node[below] at (\xa, 0) {$a$};
    \node[below] at (\xb, 0) {$b$};

    \fill[black] (Pb) circle (1.5pt);
    \node[font=\large, color=blue!80!black] at (1.8, 1.8) {$A$};
    \node[function f, anchor=west] at (3.1, 3.1) {$y = f(x)$};
    \node[function g, anchor=west] at (0.3, 3.0) {$y = g(x)$};
\end{tikzpicture}
\end{document}
```
As with the area between the function and the axis, this area is signed, so if the functions intersect, then multiple integrals must be considered.

## Integration rules
#### Integration of polynomials
For all rational $n \neq 1$:
$$
\intop x^n dx = \frac{1}{n + 1}x^{n+1} + C
$$


#### Reverse chain rule
Consider differentiating a power of a function:
$$
\frac{d}{dx} \left( f(x) \right)^n = n \left( f(x) \right)^{n-1} f'(x)
$$
We can reverse this to get a general rule for integration (*given*):
$$
\int \left( f(x) \right)^n f'(x) \, dx = \frac{1}{n+1} \left( f(x) \right)^{n+1} + c, \quad n \neq -1
$$

There is a special case for when $n = -1$ (*given*):
$$
\int \frac{f'(x)}{f(x)} \, dx = \ln|f(x)| + c
$$

#### Integration by parts
**Integration by parts** allows for integration of products of functions. The formula is:
$$
\int u\, \frac{\textrm{d}v}{\textrm{d}x}\, {\textrm{d}x} = uv - \int v\,\frac{\textrm{d}u}{\textrm{d}x}\,\textrm{d}x
$$
Generally, $u$ should be chosen to get simpler when differentiated, and $v$ should be chosen to not get any more complicated when integrated. A general rule for choosing $u$ is ILATE:
- Inverse trigonometric functions
- Logarithmic functions
- Algebraic functions
- Trigonometric functions
- Exponential functions

At A-level, repeated application of integration by parts may be required. Also, integration by parts can be used to find integrals of functions such as $\ln x$, by setting $u = \ln x,\,\frac{\textrm{d}u}{\textrm{d}x} = \frac{1}{x}$ and $\frac{\textrm{d}v}{\textrm{d}x} = 1,\,v=x$:
$$
\begin{split}
\int\ln x\,\textrm{d}x &= \int (1)\ln x\,\textrm{d}x \\
&= x\ln x - \int x\left(\frac{1}{x}\right)\,\textrm{d}x \\
&= x\ln x - \int 1\,\textrm{d}x \\
&= x\ln x - x + C
\end{split}
$$

###### Derivation
*IS?*: Learners should understand the relationship between \[integration by parts\] and the product rule.
Integration by parts comes from integrating an application of the product rule:
$$
\begin{split}
\frac{\text{d}}{\text{d}x}(uv) &= u\frac{\text{d}v}{\text{d}x} + v\frac{\text{d}u}{\text{d}x} \\\\
uv &= \int u\frac{\text{d}v}{\text{d}x}\,\text{d}x + \int v\frac{\text{d}u}{\text{d}x} \,\text{d}x \\\\
\int u\frac{\text{d}v}{\text{d}x}\,\text{d}x &= uv - \int v\frac{\text{d}u}{\text{d}x} \,\text{d}x \\\\
\end{split}
$$

#### Integration by substitution
To **integrate by substitution**:
1. Define a new variable.
2. Rewrite the integrand in terms of the new variable.
3. Make use of the chain rule to change the integral from an integral in terms of the old variable into an integral in terms of the new variable.
4. If the integral has limits, change the limits on the integral from limits for the old variable to limits for the new variable.
5. Carry out the integration.
6. Substitute for the original variable if needed.

#### Integration using trig identities
Pythagorean identities are used to integrate $\tan^2\theta$ and $\cot^2\theta$:
$$
\begin{aligned}
\sin^2\theta + \cos^2\theta &\equiv 1 \\
1 + \cot^2\theta &\equiv \operatorname{cosec}^2\theta \\
\tan^2\theta + 1 &\equiv \sec^2\theta \\
\end{aligned}
$$

Double angle identities are used to integrate $\sin^2\theta$ and $\cos^2\theta$:
$$
\begin{aligned}
\sin2\theta &\equiv 2 \sin \theta \cos \theta \\
\cos2\theta &\equiv \cos^2\theta - \sin^2\theta \\
\cos2\theta &\equiv 2\cos^2\theta - 1 \\
\cos2\theta &\equiv 1 - 2\sin^2\theta \\
\end{aligned}
$$

#### Integration by partial fractions
For some rational functions, [[Functions#Partial fractions|partial fractions]] can be used to put them in a form that allows for integration:
$$
\begin{split}
\int\frac{ax+b}{(x+p)(x+q)}\,\textrm{d}x &= \int\left(\frac{A}{x+p} + \frac{B}{x+q}\right)\,\textrm{d}x \\\\
&= A\ln|x+p| + B\ln|x+q| + C
\end{split}
$$

#### Integration as the limit of a sum
*IS*: learners should know that the area under a graph can be found as the limit of a sum of areas of rectangles.
**Integration** can be defined as the **limit of a sum**. This can be expressed using the following formula:
$$
\int^a_b f(x) \,\mathrm{d}x = \lim_{n\to\infty} \sum^n_{i=1} f(a + i\Delta x)\Delta x
$$
This process can also be shown graphically as the sum of areas of rectangles:
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth, scale=1.3]

% domain [a,b]
\def\xa{0}
\def\xb{5}
\def\N{20} % number of rectangles
\def\dx{0.25}
\def\sampleoffset{0.125} % midpoint = dx / 2

\begin{scope}
    \foreach \i in {1,2,...,\N} {
        \pgfmathsetmacro{\xleft}{\xa + (\i-1)*\dx}
        \pgfmathsetmacro{\xsample}{\xleft + \sampleoffset}
        \pgfmathsetmacro{\xsampletwo}{\xsample * \xsample}
        \pgfmathsetmacro{\xsamplethree}{\xsampletwo * \xsample}
        \pgfmathsetmacro{\h}{ (1/6)*\xsamplethree - \xsampletwo + \xsample + 2 }
        \draw[fill=blue!15, opacity=0.8, draw=blue!50] (\xleft, 0) rectangle (\xleft + \dx, \h);
    }
\end{scope}

\draw[very thick, red!90!black, domain=-0.2:5.2, samples=150] 
    plot (\x, { (1/6)*\x*\x*\x - \x*\x + \x + 2 });
\node[red!90!black, anchor=west, font=\small] at (4.5, 3.2) {$y = f(x)$};

\draw[thick, ->] (-0.5,0) -- (6,0) node[right] {$x$};
\draw[thick, ->] (0,-0.5) -- (0,3.5) node[above] {$y$};

\draw (0, 0.1) -- (0, -0.1) node[below, xshift=5pt] {$a$};
\draw (5, 0.1) -- (5, -0.1) node[below] {$b$};

\draw[|-|] (2*\dx, -0.4) -- (3*\dx, -0.4) node[midway, below, font=\small] {$\Delta x$};

\def\iL{8}
\pgfmathsetmacro{\xlL}{\xa + (\iL-1)*\dx}
\pgfmathsetmacro{\xsL}{\xlL + \sampleoffset}
\pgfmathsetmacro{\xsLtwo}{\xsL * \xsL}
\pgfmathsetmacro{\xsLthree}{\xsLtwo * \xsL}
\pgfmathsetmacro{\hL}{ (1/6)*\xsLthree - \xsLtwo + \xsL + 2 }

\draw[dashed, black!50] (\xsL, 0) -- (\xsL, \hL);
\node[above, font=\small, fill=white, inner sep=1pt] at (\xsL, \hL+0.05) {$f(x_i^*)$};
\filldraw[red!90!black] (\xsL, \hL) circle (1pt);

\end{tikzpicture}
\end{document}
```

