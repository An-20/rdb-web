#### Number bases
**Decimal** numbers are written in base 10: $2025 = 2 \times 10^3 + 0 \times 10^2 + 2 \times 10^1 + 5 \times 10^0$.
For an arbitrary base $n$, $2025_n = 2 \times n^3 + 0 \times n^2 + 2 \times n + 5 \times n^0$, where the subscript $n$ denotes the base of the number. **Binary** (base 2) numbers use digits 0 and 1, while **hexadecimal** (base 16) numbers use digits 0-9 and A-F.

#### Divisibility
The notation $a | b$ means that $a$ divides $b$, or $a$ is a factor of $b$, or $b$ is a multiple of $a$.
###### Standard divisibility tests
A number is divisible by **3** if the sum of its digits is divisible by 3.
A number is divisible by **4** if the last 2 digits are divisible by 4.
A number is divisible by **5** if the last digit is divisible by 5.
A number is divisible by **8** if the last 3 digits are divisible by 8.
A number is divisible by **9** if the sum of the digits is divisible by 9.
A number is divisible by **11** if the sum of digits with alternating signs is divisible by 11.
###### Prime divisibility algorithm
To test a large number $N$ for divisibility by prime $p$, let $N = 10a + b$ or $100a + b$.
Then, choose an $M$ and $k$ such $p\,|\,(N + kM)$. $k$ and $p$ must be coprime, so then $p\,|\,N \iff p\,|\,M$.
Set up iteration $M_0 = N$, $M_{n+1} = f(M_n)$, and iterate until $M$ is small enough to easily test for divisibility by $p$.
###### Division algorithm
The **division algorithm** (or **Euclid's division lemma**) states that for any pair of integers $a$ and $b$ with $0\lt b\le a$, $a$ can be uniquely expressed as:
$$
a = bq + r
$$
Where $q$ is the quotient and $r$ is the remainder, with $0\le r \lt b$.

#### Modular arithmetic
From the division algorithm, a number $a$ can be expressed as $a = bq + r$, where $q$ is the quotient and $r$ is the remainder. In modular arithmetic, this can be written as $a \equiv r \pmod n$. 

Two numbers $a$ and $b$ are **congruent** modulo $n$ ($a \equiv b \pmod n$) if they have the same remainder when divided by $n$. Equivalently, $a$ and $b$ are congruent modulo $n$ if their difference is divisible by $n$.
###### Rules
For $a \equiv  b \pmod m$ and $c \equiv d \pmod m$:
- $a + c \equiv b + d \pmod m$: **Adding** congruent values to both sides works
- $a - c \equiv b - d \pmod m$: **Subtracting** congruent values to both sides works
- $ac \equiv bd \pmod m$: **Multiplying** congruent values to both sides works
- $a^k \equiv b^k \pmod m$ for $k \in \mathbb{Z}$, $k \ge 0$: **Raising to a power** on both sides works
- If $f(x)$ is a polynomial in $x$ with integer coefficients, $f(a) \equiv f(b) \pmod m$.
- If $a \equiv b \pmod m$ and $a \equiv b \pmod n$ and $m$ and $n$ are coprime, $a \equiv b \pmod{mn}$

Note that **generally division does not work**. But, if $ka \equiv kb \pmod n$, and $hcf(k, n) = 1$, then $a \equiv b \pmod n$. That is, you can divide by a value coprime to the modulo.

###### Solving linear congruences
A **linear congruence** is an equation of the form $ax \equiv b \pmod n$. It has a solution if and only if $d | b$, where $d = \DeclareMathOperator{hcf}{hcf}\hcf(a, n)$. There are $d$ solutions given by:
$$x_1 + \frac{n}{d} \times r$$
Where $x_1$ is a solution found by inspection, and $r = 0,1,2,\dots,d-2$[^1].

The conditions for solutions are:
- If $\hcf(a,n) = 1$, then the congruence has **a unique solution**.
- If $\hcf(a,n) = d$ and $d$ does not divide $b$, the congruence has **no solutions**.
- If $\hcf(a,n) = d$ and $d$ does divide $b$, there are $d$ solutions.

To **find a solution** $x_1$:
- If $a \ge n$  or $b \ge n$, replace them with their remainder modulo $n$.
- To change the sign of either side, both sides can be multiplied by $-1$, or multiples of $n$ added to either side.
- If $a$ and $b$ have a common factor that is coprime to $n$, this can be cancelled.
- If $a$, $b$, and $n$ all have a common factor, this can be cancelled (changing the modulo of the congruence). This happens when $\hcf{a,n}|b$.
- Get the coefficient on $x$ to be 1.

###### Simultaneous linear congruences
**Simultaneous linear congruences** are under construction!

#### Prime numbers
###### Fundamental theorem of arithmetic
The **fundamental theorem of arithmetic** states that every integer greater than 1 is either prime or a unique product of primes.
###### Euclid's lemma
A pair of integers are **coprime** if they have no common factors other than 1.
**Euclid's lemma** states that:
- For any integers $r,a,b$, if $r|ab$ and $\hcf(r,a) = 1$, then $r|b$.
- Alternatively, if $p$ is a prime and $p|ab$, $p$ must divide at least one of $a$ or $b$.
###### Integer combinations
An **integer combination** of integers $b$ and $c$ is any integer of form $bx+cy$ for integer values of $m$ and $n$. If $a|b$ and $a|c$, then $a|(bx+cy)$:
- If $a|b$ then $b = k_1a$ for some $k_1$
- If $a|c$ then $c = k_2a$ for some $k_2$
- $bx+cy = k_1a+k_2a = a(k_1+k_2) \implies a|(bx+cy)$

Because $\hcf(b,c)$ is a factor of $b$ and $c$, any integer combination of $b$ and $c$ is a multiple of $\hcf(b,c)$. We can now use this result to prove coprimality.

If $bx+cy = 1$ for some $x$ and $y$, then $\hcf(b,c) = 1$, implying $b$ and $c$ are coprime if $bx+cy=1$. The converse is also true:
- Assume $b$ and $c$ are coprime.
- This means $bx\equiv1\pmod c$ has a unique solution. Suppose this solution is $n$.
- $bn\equiv1\pmod c \implies bn-1\equiv0\pmod c$. This means $bn-1 = kc$ for some $k$.
- Rearranging, we get $nb - kc = 1$ for some $n$ and $k$. Thus, there is some integer combination of $b$ and $c$ equal to 1.

These two results give us:
- Two integers $b$ and $b$ are **coprime if and only if** there are two integers $x$ and $y$ such that $bx + cy = 1$.
- The **highest common factor** of $b$ and $c$ can be found by finding the **smallest possible integer** written as $bx + cy$[^2].

**Footnotes**
[^1]: **Footnote on solving linear congruences**
	Once you have one solution $x_1$ the rest is fairly simple - the whole $\frac{n}{d} \times r$ thing just means adding multiples of $\frac{n}{d}$ to get the other solutions. Try it out a few times, and take a look at the exercises on Integral.
[^2]: **Footnote on finding highest common factor using $bx+cy$**
	No proof provided, but its kinda obvious? $bx+cy$ has to have a factor of $\hcf(a,b)$, so the smallest (nonnegative, integer) value of $bx+cy$ is going to be $\hcf(a,b)$ itself.
