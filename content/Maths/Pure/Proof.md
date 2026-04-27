#### Overview
**Mathematical proofs** can use logical connectives to reach conclusions:
- $A \implies B$  means that $A$ implies $B$ - if $A$ is true, then $B$ is true.
- $A \iff B$ means that $A$ if and only if (iff) $B$ - $A$ implies $B$ and $B$ implies $A$.
- $\equiv$ (congruence) means that two expressions are exactly equal.

Proofs may involve sets of numbers (*NIS*: the symbol for each set):
- The **integers**, $\mathbb{Z}$, are whole numbers.
- The **natural numbers**, $\mathbb{N}$, are counting numbers (nonnegative integers). In maths, these are $1, 2, 3\dots$. In computer science, these are $0, 1, 2\dots$.
- The **rational numbers**, $\mathbb{Q}$, are numbers that can be represented as a fraction $\frac{p}{q}$, where $p$ and $q$ are integers.
- The **irrational** numbers are numbers that cannot be represented as a fraction $\frac{p}{q}$, where $p$ and $q$ are integers. This includes numbers such as $\sqrt{2}$ and $\pi$.
- The **real numbers**, $\mathbb{R}$, include both rational and irrational numbers.

Proofs may also use interval notation to represent sets of numbers:
-  $x \gt a$: $x \in (a, \infty)$
-  $x \lt a$: $x \in (-\infty, a)$
-  $x \ge a$: $x \in [a, \infty)$
-  $x \le a$: $x \in (-\infty, a]$
-  $a \lt x \lt b$: $x \in (a, b)$
-  $a \lt x \le b$: $x \in (a, b]$
-  $x \lt a$ or $x \ge b$: $x \in (-\infty, a) \cup [b, \infty)$

#### Proof methods
###### Disproof by counter-example
**Disproof by counter-example** is where a statement is shown to be false generally by having one specific counter-example where it is not false. Consider a statement:
$$\textrm{if P($x$) is true then Q($x$) is true}$$
This can be disproved by finding a single $x$ for which $\textrm{P}(x)$ is true but $\textrm{Q}(x)$ is not.

##### Proof by deduction
**Proof by deduction** is where a logical mathematical argument is used to show that a statement is true. A proof may start by representing general numbers:
- An even integer is $2n$, for some integer $n$.
- An odd number is $2n+1$, for some integer $n$.
- A multiple of $n$ is $nk$, for some integer $k$.

##### Proof by exhaustion
**Proof by exhaustion** is where a statement is shown to be true by testing every possible case.

##### Proof by contradiction
Proof by contraction is where a statement is assumed to be false, then a contradiction is found, showing that the original statement must be true. The two following proofs are required (*IS*):

- **Proof of the irrationality of $\sqrt{2}$**:
	- Assume that $\sqrt{2}$ is rational, so $\sqrt{2} = \frac{a}{b}$ for some integers $a$, $b$, where $a$ and $b$ are coprime.
	- Squaring gives $2 = \frac{a^2}{b^2}$, so $2b^2 = a^2$.
	- Because $a^2 = 2b^2$, $a^2$ is even, so $a$ itself is even.
	- If $a$ is even, then $a = 2k$ for some integer $k$.
	- Then, $2b^2 = a^2 \implies 2b^2 = (2k)^2 = 4k^2$, so $b^2 = 2k^2$.
	- Because $b^2 = 2k^2$, $b^2$ is even, so $b$ itself is even.
	- $a$ and $b$ are both even, but this contradicts the assumption that $a$ and $b$ are coprime, as they both share a factor of 2. Thus, the assumption must be false, so $\sqrt{2}$ is irrational.

- **Proof of the infinity of primes**:
	- Assume that there is a finite list of primes, so there is a largest prime number $p_n$.
	- Consider multiplying all the prime numbers together, $Q = p_1\times p_2\times\cdots\times p_n$.
	- Consider $Q + 1$. As it is 1 more than a multiple of every prime, it is not divisible by any prime (dividing by any prime leaves a remainder of 1).
	- Thus, $Q + 1$ is either prime, or divisible by a prime larger than $p_n$ (all numbers are either prime or have prime factors).
	- This contradicts the assumption that there are a finite number of primes, as there is some prime number larger than $p_n$. Thus, the assumption must be false, so there are an infinite number of primes.
