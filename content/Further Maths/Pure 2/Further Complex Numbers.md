#### De Moivre's Theorem
In Pure 1, the modulus-argument form of a complex number was introduced, with multiplication of two complex numbers involving multiplying their moduli and adding their arguments. Repeating this process give's **De Moivre's Theorem**:
$$
z^n = (r(\cos\theta + i\sin\theta))^n = r^n(\cos n\theta + i\sin n\theta)
$$
This is true for any integer power $n$, and can be shown by proof by induction.

#### Euler's formula
**Euler's formula** relates complex exponentiation to trigonometric functions:
$$
e^{i\theta} = \cos\theta + i \sin\theta
$$
While the textbook claims "it makes no sense to ask why it is true or how to prove it", we leave a proof in the footnotes using Maclaurin series.

Euler's formula also gives a new way of writing complex numbers:
$$
re^{i\theta} = r(\cos\theta + i\sin\theta) = r\cis\theta = [r, \theta]
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

The roots of $z^n = w$ form a regular $n$-gon with a circumcircle centred on the origin.

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
(z-w)(z-w^*) = z^2 - 2z\Re{w} + |w|^2
$$
This can be used to factorise expressions of the form $z^n+c$.

#### Geometry of complex numbers
**Multiplication** by $r\cis\theta$ corresponds to a rotation about the origin through angle $\theta$ and an enlargement by scale factor $r$.

**Division** by $r\cis\theta$ corresponds to a rotation about the origin through angle $-\theta$ and an enlargement by scale factor $\frac{1}{r}$.

#### Footnotes
**Proof of Euler's Formula**
*This is taken from non-RDB private notes.*
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
