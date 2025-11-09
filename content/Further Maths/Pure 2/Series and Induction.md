#### Proof by Induction
The principle of mathematical induction involves:
- Proving a statement is true for $n = 1$ (the basis case)
- Proving that if you assume the statement is true for $n = k$, then you can prove that it is also true for $n = k + 1$. 

Much like dominoes falling, the proof for $n = 1$ causes the proofs for $n = 2, 3, 4, \dots$ to fall into place, proving the statement to be true for all positive integers $n$.

#### Standard series
The following formulae can be used without proof:
- $\sum_{r=1}^n r = \frac{1}{2}n(n+1)$
- $\sum_{r=1}^n r^2 = \frac{1}{6}n(n+1)(2n+1)$
- $\sum_{r=1}^n r^3 = \frac{1}{2}n^2(n+1)^2$
The second and third formulae are given in the formula book.

Series can be manipulated in the following ways:
- $\sum{u_r + v_r} = \sum u_r + \sum v_r$
- $\sum c u_r = c \sum u_r$.
- $\sum_{r=1}^{n}c = cn$

#### Method of differences
If the general term of a series can be written as $u_r = f(r+1) - f(r)$, then:
$$
\sum_{r=1}^n u_r = f(n+1) - f(1)
$$
The series won't always take this exact form; sometimes cancellations can happen two terms apart. When using the method of differences, make it clear what the cancellation pattern is.
