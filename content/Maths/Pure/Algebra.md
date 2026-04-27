#### Laws of indices
- Multiplication: $x^a \times x^b = x^{a+b}$
- Division: $x^a \div x^b = x^{a-b}$
- Exponentiation: $(x^a)^b = x^{ab}$
- Fractional exponents: $x^{1/a} = \root{a}\of{x}$
- Negative exponents$x^{-a} = \frac{1}{x^a}$
#### Rationalising the denominator
To rationalise the denominator of a fraction, multiply by the conjugate radical of the denominator (e.g. $a - b\sqrt{c}$ for $a + b\sqrt{c}$) to create a difference of two squares.

## Quadratics
A **quadratic equation** is a polynomial with degree 2. The general form is:
$$
ax^2 + bx + c = 0
$$
Quadratics can be solved by factorising. A quadratic with roots $r$ and $s$ can be factorised as $a(x-r)(x-s)$. The roots, of the quadratic are where the expression equals zero.

#### Quadratic formula
$$
x = \frac{-b \pm \sqrt{b^2-4ac}}{2a}
$$
The quadratic formula can be derived by **completing the square** on a general quadratic $ax^2 + bx + c = 0$. A proof is provided below.

#### Discriminant
The **discriminant** of a quadratic equation with general equation $ax^2 + bx + c = 0$ is $b^2-4ac$. If the discriminant is:
- negative, then there are no real roots.
- 0, then there is one repeated real root.
- positive, then there are two distinct real roots.

If the discriminant is 0, then there is one repeated real root, which is:
$$
x = \frac{-b \pm \sqrt{b^2-4ac}}{2a} = \frac{-b \pm 0}{2a} = \frac{-b}{2a}
$$

If the quadratic has rational coefficients and $x+y\sqrt{z}$ is a root, then $x-y\sqrt{z}$ (the conjugate radical) is a root.

The line of symmetry is at $x = \frac{-b}{2a} = \frac{x_1 + x_2}{2}$. Quadratics can be put into completed square form to find their line of symmetry and vertex:
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth]
    \def\vx{1.5} % p
    \def\vy{1.0} % q

    \def\xmin{-0.5}
    \def\xmax{2.5}
    \def\ymin{-0.5}
    \def\ymax{3.9}

    \draw[->, thick] (\xmin, 0) -- (\xmax, 0) node[below] {$x$};
    \draw[->, thick] (0, \ymin) -- (0, \ymax) node[left] {$y$};
    \node[below left] at (0, 0) {$O$};

    \begin{scope}[shift={(\vx, \vy)}]
        \draw[thick, domain=-1.5:1.5, samples=100]
            plot (\x, {\x*\x});
    \end{scope}

    \draw[dotted, gray] (\vx, 0) -- (\vx, \vy);
    \draw[dotted, gray] (0, \vy) -- (\vx, \vy);
    \node[below] at (1.3, 0) {$p$};
    \node[left] at (0, 3.2) {$q$};

    \filldraw[black] (\vx, \vy) circle (2pt);
    \node[anchor=north west, font=\normalsize, xshift=2pt] at (\vx, \vy) {Vertex $(p, q)$};

    \draw[thick, dashed] (\vx, \ymin) -- (\vx, {\ymax-1.4});
    \node[anchor=south, align=center]
        at (\vx, {\ymax-1.3}) {Line of symmetry\\$x = p$};

    \node[anchor=north]
        at ({0.5*(\xmin+\xmax)}, {\ymax+1.0}) {
        $f(x) = a(x - p)^2 + q$
    };

\end{tikzpicture}
\end{document}
```

#### Hidden quadratics
Quadratics can also be **hidden** by being quadratic in a function. For example, the below are all hidden quadratics:
$$
\begin{split}
3e^{2x} -11 e^x + 6 &= 0 \\
\cot^2x - 5\cot x &= 6 \\
x^4 + 4x^2 + 4 &= 0
\end{split}
$$
These hidden quadratics can all be solved by doing a substitution (e.g. let $y = e^x$), or just directly factorising as if $f(x)$ was just $x$.

## Polynomials
*IS*: expanding brackets, collecting like terms, factorising, simple algebraic division
#### Factor theorem
The **factor theorem** gives a connection between the roots of a polynomial and its factorisation. The two forms are:
$$
\begin{split}
f(a) = 0 &\iff (x-a) \text{ is a factor of } f(x) \\\\
f\left(\frac{b}{a}\right) = 0 &\iff (ax - b) \text{ is a factor of } f(x) \\
\end{split}
$$

## Proofs
#### Quadratic formula
The quadratic formula can be derived as shown:
$$
\begin{aligned}
ax^2 + bx + c &= 0
\\ x^2+\frac{bx}{a}+\frac{c}{a} &=0
\\ \left(x+\frac{b}{2a} \right) ^2 - \left(\frac{b} {2a}\right)^2+\frac{c}{a} &= 0
\\ \left(x+\frac{b}{2a} \right) ^2 &= \frac{b^2}{4a^2} - \frac{c}{a}
\\ \left(x+\frac{b}{2a} \right) ^2 &= \frac{b^2}{4a^2} - \frac{4ac}{4a^2}
\\ \left(x+\frac{b}{2a} \right) ^2 &= \frac{b^2-4ac}{4a^2}
\\ x+\frac{b}{2a} &= \pm \sqrt{\frac{b^2-4ac}{4a^2}}
\\ x+\frac{b}{2a} &= \frac{\pm \sqrt{b^2-4ac}}{\sqrt{4a^2}}
\\ x+\frac{b}{2a} &= \frac{\pm \sqrt{b^2-4ac}}{2a}
\\ x &= \frac{-b}{2a} + \frac{\pm \sqrt{b^2-4ac}}{2a}
\\ x &= \frac{-b \pm \sqrt{b^2-4ac}}{2a}
\end{aligned}
$$
