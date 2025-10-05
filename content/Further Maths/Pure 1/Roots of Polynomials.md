$$
a^2 + b^2 \equiv (a + bi)(a-bi)
$$
For a **polynomial with real coefficients**, **complex roots come in conjugate pairs**, that is:
$f(z) = 0$ if and only if $f(z^*) = 0$.

## Roots and Coefficients
Let $\alpha$, $\beta$, $\gamma$, and $\delta$ be the roots of the following polynomials (as necessary according to the degree of each). The following relationships are known as **Vieta's formulae**.

For a **quadratic** $ax^2 + bx + c = 0$:
$$
\begin{split}
\alpha + \beta &= \frac{-b}{a}
\\ \alpha\beta &= \frac{c}{a}
\end{split}
$$

For a **cubic** $ax^3 + bx^2 + cx + d = 0$:
$$
\begin{split}
\Sigma \alpha' = \alpha + \beta + \gamma &= \frac{-b}{a}
\\ \Sigma \alpha\beta' = \alpha\beta + \alpha\gamma + \beta\gamma &= \frac{c}{a}
\\ \Sigma \alpha\beta\gamma' = \alpha\beta\gamma &= \frac{-d}{a}
\end{split}
$$

For a **quartic** $ax^4 + bx^3 + cx^2 + dx + e = 0$:
$$
\begin{split}
\Sigma \alpha' = \alpha + \beta + \gamma + \delta &= \frac{-b}{a}
\\ \Sigma \alpha\beta' = \alpha\beta + \alpha\gamma + \alpha\delta + \beta\gamma + \beta\delta + \gamma\delta &= \frac{c}{a}
\\ \Sigma \alpha\beta\gamma' = \alpha\beta\gamma + \alpha\beta\delta + \alpha\gamma\delta + \beta\gamma\delta &= \frac{-d}{a}
\\ \Sigma \alpha\beta\gamma\delta' = \alpha\beta\gamma\delta &= \frac{e}{a}
\end{split}
$$

#### Using Substitutions
If an equation in $x$ has a root $x = p$, a substitution $u = f(x)$ can be applied, giving a resulting equation in $u$ having a root $u = f(p)$.

**Example**
The equation $x^2 + 7x + 12 = 0$ has roots $p$ and $q$. Find a quadratic equation with roots $p^2$ and $q^2$.
$$
u = x^2 \implies x = \sqrt{u}
$$
$$
\begin{split}
(\sqrt{u})^2 + 7(\sqrt{u}) + 12 &= 0
\\ u + 12 &= -7\sqrt{u}
\\ (u + 12)^2 &= (-7\sqrt{u})^2
\\ u^2 + 24u + 144 &= 49u
\\ u^2 - 25u + 144 &= 0
\end{split}
$$
