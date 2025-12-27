#### Maclaurin series
Some functions can be written as an **infinite series** in the following form, where the coefficients on powers of $x$ are real constants:
$$
f(x) = a_0 + a_1x + a_2x^2 + a_3x^3 + \cdots
$$
We can consider repeatedly differentiating this series:
$$
\begin{split}
f'(x) &= a_1 + 2a_2 + 3a_3x^2 + 4a_4x^3 + \cdots \\
f''(x) &= 2a_2 + (3\times2)a_3x + (4\times3)a_4x^2 + \cdots \\
f'''(x) &= (3\times2)a_3 + (4\times3\times2)a_4x + \cdots \\
&\,\,\,\vdots
\end{split}
$$
Then evaluating on $x=0$ to find the constants:
$$
\begin{split}
f(0) &= a_0 \\
f'(0) &= a_1 \\
f''(0) &= 2a_2 &= 2! a_2 \\
f'''(0) &= (2 \times 3)a_3 &= 3! a_3 \\
&\,\,\,\vdots
\end{split}
$$
Substituting back into to the original form gives the **Maclaurin series** for a given function:
$$
f(x) = f(0) + f'(0)x + \frac{f''(0)x^2}{2!} + \frac{f'''(0)x^3}{3!} + \cdots + \frac{f^{(r)}(0)x^r}{r!} + \cdots
$$

Some functions do not have a Maclaurin series, for example $\ln x$ is not defined at $x = 0$ (nor is any of its derivatives). However, the function $f(x) = \ln(x+1)$ does have a Maclaurin series as the function and its derivatives are defined for $x = 0$.

Maclaurin series can be used to **approximate integrals** of functions that otherwise can't be integrated. By considering the first few terms of the Maclaurin series, a polynomial can be integrated instead of the actual function to approximate the integral.

The following Maclaurin series are *given in the formula book*:
- $e^x = 1 + x + \frac{x^2}{2!} + \cdots + \frac{x^r}{r!} + \cdots$ for all $x$
- $\ln(1+x) = x - \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots + (-1)^{r+1}\frac{x^r}{r} + \cdots$ for $-1 \lt x \le 1$
- $\sin(x) = x - \frac{x^3}{3!} + \frac{x^5}{5!} + \cdots + (-1)^r\frac{x^{2r+1}}{(2r+1)!} + \cdots$ for all $x$
- $\cos(x) = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} + \cdots + (-1)^r\frac{x^{2r}}{(2r)!} + \cdots$ for all $x$
- $(1+x)^n = 1 + nx + \frac{n(n-1)}{2!}x^2 + \cdots + \frac{n(n-1)\cdots(n-r+1)}{r!}x^r + \cdots$ for $|x| \lt 1$, $n\in\mathbb{R}$
The values for $x$ for which these series are valid is very important.

#### Improper integrals
Evaluating **definite integrals** involves finding the indefinite integral, then evaluating the definite integral on the limits:
$$
\int_a^b f(x)\,\textrm{d}x = F(b) - F(a)\,\,\,\textrm{where}\,\,\frac{\textrm{d}F}{\textrm{d}x} = f(x)
$$
##### Improper integrals with infinite limits
One type of **improper integral** is an integral where one of the limits is infinite:
$$
\int_a^\infty f(x)\,\textrm{d}x
$$
To evaluate these improper integrals, replace the infinite limit with $b$, find the value of the integral in terms of $b$, then take limits:
$$
\begin{split}
\int_a^\infty f(x)\,\textrm{d}x 
&= \lim_{b\to\infty}\int_a^bf(x)\,\textrm{d}x \\
&= \lim_{b\to\infty}\{F(b)\} - F(a) \quad\textrm{where}\,\,\frac{\textrm{d}F}{\textrm{d}x} = f(x)
\end{split}\
$$
The improper integral only has a value if the **limit exists and is finite**. If the limit does not exist, or is infinite, the improper integral **diverges**.
##### Improper integrals with undefined integrands
Another type of improper integral is where the range of integration is finite, but the **integrand is not defined** at a point within the range of integration. There are two possible cases:
- The undefined point is an **endpoint** of the range of integration
- The undefined point is **within the range** of integration.

If the undefined point is an **endpoint** of the range of integration, then a similar method can be used to the infinite limits, by replacing the undefined point $k$ with $b$, finding the value of the integral in terms of $b$, then taking limits:
$$
\begin{split}
\int_a^k f(x)\,\textrm{d}x 
&= \lim_{b\to k}\int_a^bf(x)\,\textrm{d}x \\
&= \lim_{b\to k}\{F(b)\} - F(a) \quad\textrm{where}\,\,\frac{\textrm{d}F}{\textrm{d}x} = f(x) \\
\textrm{similarly:}
\int_k^c f(x)\,\textrm{d}x 
&= \lim_{b\to k}\int_k^cf(x)\,\textrm{d}x \\
&= F(c) - \lim_{b\to k}\{F(b)\} \quad\textrm{where}\,\,\frac{\textrm{d}F}{\textrm{d}x} = f(x)
\end{split}
$$
If the limit does not exist, or is infinite, the improper integral **diverges**.

If the undefined point is **within the range of integration**, then the integral needs to be split into two (for an undefined point $k \in (a, b)$):
$$
\int_a^c f(x)\,\textrm{d}x = \lim_{b\to k}\int_a^b f(x)\,\textrm{d}x + \lim_{b\to c}\int_b^c f(x)\,\textrm{d}x
$$
If either limit does not exist, or is infinite, the improper integral **diverges**.

#### Volumes of revolution
The area between a curve and the $x$-axis from $x=a$ to $x=b$ is given by $\int_a^b y \,\textrm{d}x$, if $y \gt 0$. This area can be revolved about the $x$ or $y$ axes to create a **solid of revolution**. The volume of a solid of revolution is the **volume of revolution**.

When the curve $y=f(x)$ between $x=a$ to $x=b$ is revolved $360\degree$ about the $x$-axis, the resulting volume of revolution is given by:
$$
\pi\int_a^b y^2\,\textrm{d}x
$$
Similarly, when the curve $x=f(y)$ between $y=a$ to $y=b$ is revolved $360\degree$ about the $y$-axis, the resulting volume of revolution is given by:
$$
\pi\int_a^b x^2\,\textrm{d}y
$$
Both of these results can be proven by considering the volume of revolution as being formed of many small cylinders of height $\textrm{d}x$ or $\textrm{d}y$ lying along the axis of revolution, each with volume $\pi y^2\,\textrm{d}x$ or $\pi x^2\,\textrm{d}y$.

Volumes of revolution can also be formed by **revolving the area between two curves**. When the area between $y=g(x)$  and $y = f(x)$ between $x=a$ and $x=b$ (where $g(x)$ lies above $f(x)$) is revolved $360\degree$ about the $x$-axis, the resulting volume of revolution is given by:
$$
\pi\int_a^b \left((g(x))^2 - (f(x))^2\right)\,\textrm{d}x
$$

Volumes of revolution can also be calculated for **curves defined parametrically**. When part of a curve with parametric equation $x=f(t)$ and $y=g(t)$ between points with parameter values $t=t_1$ and $t = t_2$ is revolved about one of the coordinate axes, the resulting volume of revolution is given by:
$$
\begin{split}
\textrm{rotation\,about\,}x:\quad \pi\int_{t_1}^{t_2}y^2\,\frac{\textrm{d}x}{\textrm{d}t}\,\textrm{d}t \\
\textrm{rotation\,about\,}y:\quad \pi\int_{t_1}^{t_2}x^2\,\frac{\textrm{d}y}{\textrm{d}t}\,\textrm{d}t
\end{split}
$$

#### Mean value of a function
The mean value of function $f(x)$ between $x=a$ and $x=b$ is given by:
$$
\frac{1}{b - a}\int_a^b f(x)\,\textrm{d}x
$$
