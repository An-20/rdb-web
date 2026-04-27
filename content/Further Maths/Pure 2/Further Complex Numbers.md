#### De Moivre's theorem
In [[Complex Numbers|Pure 1]], the modulus-argument form of a complex number was introduced, with multiplication of two complex numbers involving multiplying their moduli and adding their arguments. Repeating this process give's **De Moivre's theorem**:
$$
z^n = (r(\cos\theta + i\sin\theta))^n = r^n(\cos n\theta + i\sin n\theta)
$$
This is true for any integer power $n$, and can be shown by proof by induction.

#### Euler's formula
**Euler's formula** relates complex exponentiation to trigonometric functions:
$$
e^{i\theta} = \cos\theta + i \sin\theta
$$
While the textbook claims "it makes no sense to ask why it is true or how to prove it", we leave a proof in the footnotes using Maclaurin series^[^1].

Euler's formula also gives a new way of writing complex numbers with a modulus and argument, known as **exponential form**:
$$
re^{i\theta} = r(\cos\theta + i\sin\theta) = r\operatorname{cis}\theta = [r, \theta]
$$
The **complex conjugate** of $z = re^{i\theta}$ is $re^{-i\theta}$:
$$
re^{-i\theta} = r(\cos(-\theta) + i\sin(-\theta)) = r(\cos\theta - i\sin\theta) = z^*
$$
For $r = 1$, this gives $z^* = \frac{1}{z} = z^{-1}$.

#### Roots of complex numbers
De Moivre's theorem can also be used to find roots of complex numbers, to solve equations of the form $z^n = w$:
- Write $w$ in modulus-argument form
- Use de Moivre's theorem to write $z^n = r^n(\cos n\theta + i\sin n\theta) = w$
- Compare moduli
- Compare arguments, adding $2\pi$ to generate all solutions
- Write the $n$ different roots in modulus-argument form.

The roots of $z^n = w$ form a regular $n$-gon with a circumcircle centred on the origin:
```tikz
\usetikzlibrary{shapes.geometric, arrows.meta}

\begin{document}
\begin{tikzpicture}
    \def\n{6}
    \def\radius{2}
    \def\angleoffset{30}

    \draw[-{Stealth}] (-2.5,0) -- (2.5,0) node[right] {Re};
    \draw[-{Stealth}] (0,-2.5) -- (0,2.5) node[above] {Im};

    \draw[dashed] (0,0) circle (\radius);
    \node[below left] at (40:\radius+2) {$z^6 = -8 = 8e^{i\pi}$};

    \node[regular polygon, regular polygon sides=\n, minimum size=2*\radius cm, draw=black, thick, rotate=\angleoffset] (hexagon) at (0,0) {};

    \foreach \i in {1,...,\n} {
        \pgfmathsetmacro{\angle}{\angleoffset + (\i-1)*360/\n}
        \filldraw[red] (\angle:\radius) circle (2pt);
        \draw[dotted] (0,0) -- (\angle:\radius);
        \node at (\angle+6:\radius + 0.3) {$z_{\the\numexpr\i-1\relax}$};
    }

    \draw[bend right, ->, red] (\angleoffset:1) arc (\angleoffset:\angleoffset+60:1);
    \node[red] at (\angleoffset+30:1.5) {$\frac{2\pi}{6}$};

    \node[below left] at (0,0) {$0$};
\end{tikzpicture}
\end{document}
```

The **roots of unity** are $z$ such that $z^n = 1$. There are $n$ $n$th roots of unity, each with modulus 1 and differing by an argument of $\frac{2\pi}{n}$. The roots of unity are:
$$
1, e^\frac{2\pi i}{n}, e^\frac{4\pi i}{n},\dots,e^\frac{2(n-1)\pi i}{n}
$$
The roots of unity can also be written as:
$$
w_k = \left(e^\frac{2\pi i}{n}\right)^k = w_1^k\quad\textrm{where}\,k=0,1,\dots,n-1
$$
There are symmetries of the roots of unity that can be applied, e.g. many are complex conjugates. Additionally, as the roots of unity are spaced equally around the circle, the **sum must be zero** (this can also be shown by considering roots of polynomials).

#### Further factorising
$$
(z-w)(z-w^*) = z^2 - 2z\operatorname{Re}(w) + |w|^2
$$
This can be used to factorise expressions of the form $z^n+c$, as many roots will occur in conjugate pairs, which form irreducible quadratic factors.

#### Geometry of complex numbers
**Multiplication** by $r\operatorname{cis}\theta$ corresponds to a rotation about the origin through angle $\theta$ (measured anticlockwise) and an enlargement by scale factor $r$.

**Division** by $r\operatorname{cis}\theta$ corresponds to a rotation about the origin through angle $-\theta$ and an enlargement by scale factor $\frac{1}{r}$.

#### Footnotes
**Proof of Euler's Formula**
The Maclaurin expansion of $f(x)$ is given by:
$$
\begin{split}
f(x) &= f(0) + \frac{f'(0)x}{1!} + \frac{f''(0)x^2}{2!} + \cdots \frac{f^{(r)}(0)x^r}{r!} + \cdots \\
&= \sum^\infty_{n=0} \frac{f^{(n)}(0)x^n}{n!}
\end{split}
$$
For example, considering $f(x)$ = $e^x$:
$$
\begin{split}
&f(0) &&= e^0 = 1,\quad f'(0) = e^0 = 1,\cdots,f^{(n)} = e^0 = 1 \\
\implies &f(x) &&= \frac{f^{(n)}(0)x^n}{n!} = \frac{(1)x^n}{n!} \\
\implies &e^x &&= 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots
\end{split}
$$
Considering $f(x) = \cos(x)$:
$$
\begin{split}
&f(0) &&= \cos(0) = 1 \\
&f'(0) &&= -\sin(0) = 0 \\
&f''(0) &&= -\cos(0) = -1 \\
&f'''(0) &&= \sin(0) = 0 \\
&f^{(4)}(0) &&= \cos(0) = 1, \quad\text{etc.}\\
\implies &\cos(x) &&= 1 + -\frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots
\end{split}
$$
Considering $f(x) = \sin(x)$:
$$
\begin{split}
&f(0) &&= \sin(0) = 0 \\
&f'(0) &&= \cos(0) = 1 \\
&f''(0) &&= -\sin(0) = 0 \\
&f'''(0) &&= -\cos(0) = -1 \\
&f^{(4)}(0) &&= \sin(0) = 0, \quad\text{etc.}\\
\implies &\sin(x) &&= x -\frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \cdots
\end{split}
$$
By considering $e^{ix}$, we can observe that:
$$
\begin{split}
&e^x &&= 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \frac{x^5}{5!} + \frac{x^6}{6!} + \frac{x^7}{7!}+ \cdots \\
\implies &e^{ix} &&= 1 + ix - \frac{x^2}{2!} - \frac{ix^3}{3!} + \frac{x^4}{4!} + \frac{ix^5}{5!} - \frac{x^6}{6!} - \frac{ix^7}{7!}+ \cdots \\
\implies &e^{ix} &&= \left(1 - \frac{x^2}{2!} + \frac{x^4}{4!} + - \frac{x^6}{6!} + \cdots\right) + i\left(x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!}+ \cdots\right) \\
\implies &e^{ix} &&= \cos(x) + i \sin(x)
\end{split}
$$
Proving Euler's formula.

[^1]: **Footnote on Euler's formula as a definition**
	Debating whether Euler's formula is a definition or a result that can be derived from other results such as Maclaurin series is pointless. Regardless, taking the Maclaurin series as the 'primary' axiomatic definition of $e^x$, $\sin x$, and $\cos x$, and plugging complex numbers in, Euler's formula can be derived.
