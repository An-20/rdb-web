## Sequences and series
A **sequence** is a list of terms, while a **series** is the sum of the terms. A sequence can be defined in two ways:
- A recurrence relation, e.g. $u_{n+2} = u_{n+1} + u_{n}$ (for the Fibonacci numbers)
- A position-to-term formula, e.g. $u_{n} = 3n + 4$ (for an arithmetic sequence). A sequence with a position-to-term formula can be denoted as $\{u_{n}\}$, e.g. $\{3n+4\} = 7, 10, 13, 16, 19$.

Sequences can be:
- **Periodic**, meaning that there are repeated terms, e.g. $1, 5, 4, 1, 5, 4, 1,\dots$. In this example, the **period** is 3.
- **Oscillating**, meaning they are periodic with just two terms, e.g. $1,0,1,0,1\dots$.
- **Convergent**, meaning the terms of the sequence get closer to a limiting value, e.g. the terms in $1, \frac{1}{2},\frac{1}{4},\frac{1}{8}\dots$ converge to 0. A series can also be convergent, meaning the sum to infinity of the sequence has a finite value[^1]. For example, the sum of $1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \dots$ converges to 2.
- **Divergent**, meaning the terms of the sequence are not convergent, e.g. $1,2,3,4,5$
  A series can also be divergent, meaning the sum to infinity of the sequence does not have a finite value.
- **Monotonically increasing**, meaning each term is greater than the one before it ($u_{n+1} > u_n$), e.g. $1,2,3,4,5$. A **monotonically decreasing** sequence has each term less than the one before it ($u_{n+1} < u_n$).

The sequence of **Fibonacci numbers** is defined by the recurrence relation $u_{n+2} = u_{n+1} + u_{n}$, $u_{1}=1$, $u_{2}=1$, giving the first 5 terms as $1, 1, 2, 3, 5$. The ratio of each term to the previous one converges to $\phi = \frac{1 + \sqrt{5}}{2}$, the **golden ratio**.

The sequence of **Lucas numbers**[^2] is defined by the same recurrence relation as the Fibonacci numbers (each term is the sum of the two immediately before it), but $u_{1} = 1$ and $u_{2} = 3$, giving the first 5 terms as $1,3,4,7,11$.

## First-order recurrence relations
A **linear recurrence relation** is where each term in a sequence is a linear function of previous terms, e.g. $u_{n+2} = 3u_{n+1} + 2u_n + 3$. A **first-order** recurrence relation is where each term only depends on the previous term and some function of $n$, e.g. $u_{n+1} = 3u_n + 2$. For the AS content, only first-order recurrence relations will be considered.

A **homogenous** recurrence relation has the form $u_{n+1} = ku_n$, for some constant $k$. In contrast, a **non-homogenous** recurrence relation has the form $u_{n+1} = ku_n + f(n)$, where $f(n)$ is some function of $n$ (in this course, a polynomial in $n$ or $a\times b^n$).

A recurrence system is defined by the recurrence relation (e.g. $u_{n+1} = 3u_n + 2$) and the initial conditions, e.g. $u_1 = 1$. Our goal is typically to find a **closed-form solution** to the system: a position-to-term rule that only depends on $n$. For the previous example, $u_n = 2\times3^{n-1} - 1$ (you can verify this for $n=1,2,3$).

For a relation of form $u_{n+1} = ku_n + f(n)$, the solution will take the form: $c(n) + p(n)$, where $c(n)$ is the **complementary function** and $p(n)$ is the **particular solution**.

We start by finding the **complementary function** $c(n)$, which is related to the homogenous part of the recurrence relation ($ku_n$):
- Start with the reduced equation $u_{n+1} = ku_n$
- Replace $u_n$ with $r^n$ ($r \not= 0$), giving the **auxiliary equation**
- Solve for $r$, giving a complementary function of the form $c(n) = Ar^n$
- In the AS course, $c(n)$ is always of the form $Ak^n$. Note that if $k = 1$, this will always be a failure case.

We then find the **particular solution** $p(n)$, which is related to the non-homogenous part of the recurrence relation ($f(n)$):
Choose a form for $p(n)$ based off $f(n)$:
- If $f(n$) is a number, $p(n) = a$
- If $f(n$) is linear, $p(n) = an + b$
- If $f(n$) is quadratic, $p(n) = an^2 + bn + c$
- If $f(n$) is an exponential $a\times b^n$ (some constants $a$ and $b$), $p(n) = a \times b^n$
- If the form of $p(n)$ is the same as for $c(n)$, then this is a failure case. Multiply $p(n)$ by $n$.
Substitute the appropriate form for $p(n)$ into both sides of the relation and solve for $a$, $b$, and $c$.

Then, apply the initial conditions to find remaining constants from the complementary function.


[^1]: **Footnote on convergence (outside of specification)**
	There are sequences where the terms converge to 0 that do not sum to a convergent series. For example, the harmonic sequence $1, \frac{1}{2}, \frac{1}{3},\frac{1}{4},\dots$ is convergent because the terms tend to 0. However, the harmonic series $1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \dots$ is not convergent.

[^2]: **Footnote on the Fibonacci and Lucas numbers**
	$\varphi$ is more commonly used to denote the golden ratio than $\phi$, but the specification uses $\phi$. 
	Some definitions of the Fibonacci and Lucas numbers start from $n=0$ instead of $n=1$ (as an extra sidenote, Fibonacci himself started from 1 and 2).
