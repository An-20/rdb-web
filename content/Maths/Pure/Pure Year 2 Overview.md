## Proof by contradiction
Proof by contraction is where a statement is assumed to be false, then a contradiction is found, showing that the original statement must be true.

#### Proof of the irrationality of $\sqrt{2}$
- Assume that $\sqrt{2}$ is rational, so $\sqrt{2} = \frac{a}{b}$ for some integers $a$, $b$, where $a$ and $b$ are coprime.
- Squaring gives $2 = \frac{a^2}{b^2}$, so $2b^2 = a^2$.
- Because $a^2 = 2b^2$, $a^2$ is even, so $a$ itself is even.
- If $a$ is even, then $a = 2k$ for some integer $k$.
- Then, $2b^2 = a^2 \implies 2b^2 = (2k)^2 = 4k^2$, so $b^2 = 2k^2$.
- Because $b^2 = 2k^2$, $b^2$ is even, so $b$ itself is even.
- $a$ and $b$ are both even, but this contradicts the assumption that $a$ and $b$ are coprime, as they both share a factor of 2. Thus, the assumption must be false, so $\sqrt{2}$ is irrational.

#### Proof of the infinity of primes
- Assume that there is a finite list of primes, so there is a largest prime number $p_n$.
- Consider multiplying all the prime numbers together, $Q = p_1\times p_2\times\cdots\times p_n$.
- Consider $Q + 1$. As it is 1 more than a multiple of every prime, it is not divisible by any prime (dividing by any prime leaves a remainder of 1).
- Thus, $Q + 1$ is either prime, or divisible by a prime larger than $p_n$ (all numbers are either prime or have prime factors).
- This contradicts the assumption that there are a finite number of primes, as there is some prime number larger than $p_n$. Thus, the assumption must be false, so there are an infinite number of primes.

