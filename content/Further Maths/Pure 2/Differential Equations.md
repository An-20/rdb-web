A **differential equation** describes the relationship between an indepdendent variable (on the bottom of the derivative), and a dependent variable (on the top of the derivative) and its derivatives. Differential equations can be categorized by:
- The **order** of a differential equation is the highest order derivative of the dependent variable.
- A **linear differential equation** is where the dependent variable appears to a maximum power of 1. Any differential equation with other functions of the dependent variable, $y$ e.g. $y^2$, $\sin y$, is not linear.
- A **homogenous differential equation** is where every term involves the dependent variable. All **non-homogeneous differential equations** have an associated homogeneous differential equation by removing terms that don't involve the dependent variable.

For a differential equation with independent variable $x$ and dependent variable $y$, **solving a differential equation** involves finding $y$ in terms of $x$. The solution will contain arbitrary constants of integration, where the **general solution to an $n$-th order differential equation has $n$ arbitrary constants**. 

To find the arbitrary constants, initial conditions or boundary conditions are needed. Each piece of information, e.g. $y$ or $\frac{\textrm{d}y}{\textrm{d}x}$ for a value of $x$ gives another arbitrary constant. The **particular solution** is where all the arbitrary constants have been found so the solution fits the conditions.

#### Separable differential equations
Some differential equations can be solved by **separation of variables**. This is where the equation can be rearranged so one side only has $x$ terms and the other side only has $y$ terms. Then:
- $\frac{\textrm{d}y}{\textrm{d}x}$ can be separated as a fraction.
- Integrate both sides.

A proof for this result is given below. A separable differential equation can be written in the following form:
$$
\frac{\textrm{d}y}{\textrm{d}x} f(y) = g(x)
$$

By considering the integrals of $f(z)$ and $g(z)$:
$$
\begin{split}
& \int f(z)\textrm{d}z = F(z) \quad\textrm{where}\,\frac{\textrm{d}}{\textrm{d}z}(F(z)) = f(z) \\
& \int g(z)\textrm{d}z = G(z) \quad\textrm{where}\,\frac{\textrm{d}}{\textrm{d}z}(G(z)) = g(z)
\end{split}
$$
Consider the following equation:
$$
\begin{split}
&F(y) = G(x) +C \\
\iff & \frac{\textrm{d}y}{\textrm{d}x} f(y) = g(x)
\end{split}
$$
Where going from the first line to the second involves differentiating by $x$ and applying the chain rule on the left. Thus, our original equation can be solved by multiplying across by $\textrm{d}x$ and integrating both sides.

#### Non-homogeneous differential equations
For linear differential equations, the general solution to a non-homogeneous differential equation is the sum of:
- The general solution to the associated homogeneous equation, called the **complementary function**.
- One solution to the full non-homogeneous equation, called the **particular integral**.
For a linear differential equation, the general solution is:
$$
y = y_c + y_p
$$
Where $y_c$ is the complementary function and $y_p$ is a particular integral.

#### The integrating factor
Consider a linear first-order differential equation:
$$
\frac{\textrm{d}y}{\textrm{d}x} + F(x)y = G(x)
$$
We define $I(x)$, the **integrating factor**, to be:
$$
\begin{split}
I(x) &= e^{\int F(x) \,\textrm{d}x} \\
I'(x) &= F(x)e^{\int F(x) \,\textrm{d}x} = F(x)I(x)
\end{split}
$$
By multiplying both sides of the original equation by $I(x)$:
$$
\begin{split}
\frac{\textrm{d}y}{\textrm{d}x} I(x) + I(x)F(x)y &= I(x)G(x) \\
\frac{\textrm{d}y}{\textrm{d}x} I(x) + I'(x)y &= I(x)G(x)
\end{split}
$$
Now, the left-hand side is a result of applying the **product rule**:
$$
\begin{split}
\frac{\textrm{d}}{\textrm{d}x}(I(x)y) &= I(x)G(x) \\
I(x)y &= \int I(x)G(x)\,\textrm{d}x + C \\
y &= \frac{1}{I(x)}\int I(x)G(x)\,\textrm{d}x + C
\end{split}
$$
Giving a solution to the original differential equation.

#### Second-order differential equations with constant coefficients
A **homogeneous second-order differential equation with constant coefficients** is of the form:
$$
a\frac{\textrm{d}^2y}{\textrm{d}x^2} + b\frac{\textrm{d}y}{\textrm{d}x} + cy = 0
$$
To solve this, an **auxiliary equation** is formed:
$$
a\lambda^2 + b\lambda + c = 0
$$
The **general solution** depends on the solutions to the auxiliary equation:
- If there are two real roots $\lambda_1$ and $\lambda_2$, the general solution is $Ae^{\lambda_1 x} + Be^{\lambda_2 x}$.
- If there is a repeated real root $\lambda$, the general solution is $Ae^{\lambda x} + Bxe^{\lambda x}$.
- If there are two complex roots $\alpha \pm \beta i$, the general solution is $e^{\alpha x}(A\sin\beta x + B\cos\beta x)$.

A **non-homogeneous second-order differential equation with constant coefficients** is of the form:
$$
a\frac{\textrm{d}^2y}{\textrm{d}x^2} + b\frac{\textrm{d}y}{\textrm{d}x} + cy = f(x)
$$
To solve equations of this form, first solve the homogeneous equation to obtain the **complementary function**. Then, find a **particular integral** using a **trial function**, by substituting in a trial function into the differential equation to find the coefficients. The **trial function** is of the form:
- $ax+b$ for a linear polynomial
- A general polynomial of the same order for any polynomial
- $ce^{bx}$ for $ae^{bx}$
- $a\sin kx + b\cos kx$ for either $p \sin kx$ or $p \cos kx$.
If the trial function is **already a part of the complementary function**, then **multiply the trial function by $x$**.
