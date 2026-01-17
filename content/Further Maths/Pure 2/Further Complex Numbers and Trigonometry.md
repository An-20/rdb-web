#### Exponential Form of Trigonometric Functions
From [[Further Complex Numbers#Euler's formula|Euler's formula]], substituting in $-\theta$,
$$
\begin{split}
e^{i\theta} &= \cos(\theta) + i \sin(\theta) \\
e^{-i\theta} &= \cos(-\theta) + i\sin(-\theta) \\
&= \cos(\theta) - i\sin(\theta)
\end{split}
$$
By combining these equations, we can form alternative equations for sine and cosine:
$$
\begin{split}
e^{i\theta} + e^{-i\theta} &= 2\cos(\theta) \\
\cos(\theta) &= \frac{e^{i\theta} + e^{-i\theta}}{2}
\end{split}

\hspace{3em}

\begin{split}
e^{i\theta} - e^{-i\theta} &= 2i\sin(\theta) \\
\sin(\theta) &= \frac{e^{i\theta} - e^{-i\theta}}{2i}
\end{split}
$$

This can be generalised; if we let $z = e^{i\theta}$ then $z^n = e^{in\theta}$ which leads to
$$
\begin{split}
e^{in\theta} + e^{-in\theta} &= 2\cos(n\theta) \\
2\cos(n\theta) &= z^n + \frac{1}{z^n}
\end{split}

\hspace{3em}

\begin{split}
e^{in\theta} - e^{-in\theta} &= 2i\sin(n\theta) \\
2i\sin(n\theta) &= z^n - \frac{1}{z^n}
\end{split}
$$
#### Multiple angle formulae
A complex number can be raised to a power both using the **binomial expansion** and **de Moivre's Theorem**. These two results can then be equated and the real and imaginary components used to find multiple angle formulae for sine and cosine.
##### Example finding formulae for $\cos(3\theta)$ and $\sin(3\theta)$
Let $z = \text{cis}\,\theta = \cos\theta + i \sin\theta$. Using the binomial expansion:
$$
\begin{split}
z^3 &= (\cos\theta + i \sin\theta)^3 \\
&= \cos^3\theta + 3i\cos^2\theta\sin\theta - 3\cos\theta\sin^2\theta - i \sin^3\theta
\end{split}
$$
Using de Moivre's Theorem:
$$
z^3 =\text{cis}(3\theta) = \cos(3\theta) + i \sin(3\theta)
$$
Equating real and imaginary parts:
$$
\begin{split}
\cos(3\theta) &= \cos^3\theta - 3\cos\theta\sin^2\theta \\
&= \cos^3\theta + 3 \cos^3\theta - 3\cos\theta \\
&= 4\cos^3\theta - 3\cos\theta
\end{split}
\hspace{3em}
\begin{split}
\sin(3\theta) &= 3\cos^2\theta\sin\theta - \sin^3\theta\\
&= 3\sin\theta - 3\sin^3\theta - \sin^3\theta \\
&= 3\sin\theta - 4\sin^3\theta
\end{split}
$$

#### Powers of trigonometric functions
The general exponential form of trigonometric functions can be expanded and collected in order to find powers of trigonometric functions in terms of multiple angle functions.
##### Example finding formulae for $\cos^5\theta$
Let $z = \text{cis}\,\theta$. Using the binomial expansion:
$$
\begin{split}
\left(z + \frac{1}{z} \right)^5 &= z^5 + 5z^4 \left(\frac{1}{z}\right) + 10z^3 \left(\frac{1}{z}\right)^2 + 10z^2 \left(\frac{1}{z}\right)^3 + 5z \left(\frac{1}{z}\right)^4 + \left(\frac{1}{z}\right)^5 \\
&= z^5 + 5z^3 + 10z + 10 \left(\frac{1}{z}\right) + 5\left(\frac{1}{z^3}\right) + \left(\frac{1}{z^5}\right) \\
&= \left(z^5 + \frac{1}{z^5} \right) + 5\left(z^3 + \frac{1}{z^3} \right) + 10\left(z + \frac{1}{z} \right) \\ \\

(2\cos(\theta))^5 &= 2\cos(5\theta) + 5(2\cos(3\theta)) + 10(2\cos(\theta)) \\
32\cos^5(\theta) &= 2\cos(5\theta) + 10\cos(3\theta) + 20\cos(\theta) \\
cos^5(\theta) &= \frac{1}{16}\cos(5\theta) + \frac{5}{16}\cos(3\theta) + \frac{5}{8}\cos(\theta)
\end{split}
$$
A similar method can be used by expanding $\left(z - \frac{1}{z} \right)^n$ to find $\sin^n(\theta)$.

#### Trigonometric Series
Some **sums of trigonometric series** can be calculated using the sum of the geometric series formed by the exponential form of the trigonometric functions (if one is formed).
##### Example sum of a trigonometric series
Show that $\sin(x) + \sin(2x) + \sin(3x) + \dots + \sin(10x) = \displaystyle\frac{\sin(x) + \sin(10x) - \sin(11x)}{4\sin^2(\frac{x}{2})}$

Consider the geometric series
$$
a = e^{ix} \hspace{1em} r = e^{ix}
$$
We can sum the first 10 terms to get
$$
e^{ix} + e^{2ix} + e^{3ix} + \dots + e^{10ix} = \frac{e^{ix}(1 - e^{10ix})}{1 - e^{ix}}
$$
As $\sin(nx) = \text{Im}(e^{inx})$,
$$
\begin{split}
\sin(x) + \sin(2x) + \sin(3x) + \dots + \sin(10x) &= \text{Im}(e^{ix} + e^{2ix} + e^{3ix} + \dots + e^{10ix}) \\
&= \text{Im} \left( \frac{e^{ix}(1 - e^{10ix})}{1 - e^{ix}} \right) \\
&= \text{Im} \left( \frac{e^{ix}(1 - e^{10ix})}{1 - e^{ix}} \times \frac{1 - e^{-ix}}{1 - e^{-ix}} \right) \\
&= \text{Im} \left( \frac{e^{ix} - 1 - e^{11ix} + e^{10ix}}{1 - e^{ix} - e^{-ix} + 1} \right) \\
&= \text{Im} \left( \frac{e^{ix} - 1 - e^{11ix} + e^{10ix}}{2 - 2\cos x} \right) \\
&= \frac{\sin x - \sin 11x + \sin 10x}{2 - 2\cos x} \\
&= \frac{\sin x - \sin 11x + \sin 10x}{4\sin^2 \left( \frac{x}{2} \right)}
\end{split}
$$
