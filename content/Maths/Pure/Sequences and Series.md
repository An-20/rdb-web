A **sequence** is a list of terms, while a **series** is the sum of the terms. A sequence can be defined in two ways:
- A position-to-term formula for the $n$th term e.g. $u_{n} = 3n + 4$ (for an arithmetic sequence).
- A recurrence relation, e.g. $x_{n+1} = f(x_n)$.

Sequences can be:
- **Periodic**, meaning that there are repeated terms, e.g. $1, 5, 4, 1, 5, 4, 1,\dots$. In this example, the **period** is 3.
- **Increasing**, meaning each term is greater than the one before it ($u_{n+1} > u_n$), e.g. $1,2,3,4,5$.
- **Decreasing**, meaning each term is term less than the one before it ($u_{n+1} < u_n$), e.g. $5, 4, 3, 2, 1$.

#### Sigma notation
**Sigma notation** is used to denote the sum of a sequence:
$$
\sum_{n=a}^{b}{u_n} = u_a + u_{a+1} + \cdots + u_b
$$
These terms are summed from $n = a$ to $n = b$ **inclusive**. This notation can also be used to denote infinite sums, for example:
$$
\begin{split}
\sum_{n=1}^{3} n^2 &= 1^2 + 2^2 + 3^2 \\\\
\sum_{n=1}^{\infty} \frac{1}{2^n} &= \frac{1}{2^1} + \frac{1}{2^2} + \frac{1}{2^3} + \cdots
\end{split}
$$
Sigma notation can also be manipulated in useful ways:
- $\sum(a_n + b_n) = \sum a_n + \sum b_n$. This is the associative property of addition.
- $\sum(ka_n) = k\sum a_n$. This is the distributive property of multiplication over addition.

## Arithmetic sequences
An **arithmetic sequence** (or progression) is defined by the first term, $a$, and the **common difference** between terms, $d$. The sequence is therefore:
$$
a, a+d, a+2d, a+3d, \dots
$$

The $n$th term is $a + (n - 1)d$. The sum of the first $n$ terms is therefore:
$$
S_n = a + (a + d) + (a + 2d) + \dots + (a + (n-1)d)
$$
To find the sum of the series, the series can be summed along with it the series written backwards, then summing the vertically aligned pairs.:
$$
\begin{alignat*}{5}
S_n &= a &+& a + d &+& \cdots &+& a + (n-2)d) &+& a + (n-1)d
\\ S_n &= a + (n-1)d &+& a + (n-2)d &+& \cdots &+& (a + d) &+& a
\\ 2S_n &= 2a + (n-1)d\,\,\,&+& 2a + (n-1)d \,\,\, &+& \dots \,\,\,&+& 2a + (n-1)d \,\,\,&+& 2a + (n-1)d
\end{alignat*}
$$
Where $2S_n$ has $n$ identical $2a + (n-1)d)$ terms. Therefore the **sum of an arithmetic sequence is given by**:
$$
\begin{aligned}
2S_n &= n(2a+(n-1)d)
\\
\\ S_n &= \frac{n}{2}(2a+(n-1)d)
\end{aligned}
$$

Also, note that the first term is $a$, and the last term is $a + (n-1)d$, so the bracketed part is the sum of the first and last terms. Thus, the formula can also be written as:
$$
S_n = \frac{n}{2}(\mathrm{first\,term}+\mathrm{last\,term})
$$

## Geometric sequences
A **geometric sequence** (or progression) is defined by the first term, $a$, and the **common ratio** $r$. The sequence is therefore:
$$
a, ar, ar^2, ar^3,\dots
$$

The $n$th term is $ar^{n-1}$. The sum of the first $n$ terms can be found using a method similar to that of the arithmetic series, subtracting $S_n r$ from $S_n$:
$$
\begin{alignedat}{6}
S_n &= a &&+ ar &&+ \cdots &&+ ar^{n-2} &&+ ar^{n-1} \\
S_n r &= && ar &&+ \cdots &&+ ar^{n-2} &&+ ar^{n-1} &&+ ar^n
\end{alignedat}
$$
Giving, for $r \ne 1$:
$$
\begin{aligned}
S_n - S_nr &= a - ar^n \\ 
S_n(1-r) &= a - ar^n \\
S_n &= \frac{a - ar^n}{1-r} &= \frac{a(1-r^n)}{1-r}
\end{aligned}
$$

#### Sum to infinity
A geometric sequence is **convergent** if $|r| \lt 1$, otherwise it is divergent. If it is convergent, then the sum to infinity is:
$$
S_\infty = \frac{a}{1-r}
$$

## Binomial expansion
The **binomial expansion** of $(a + b)^n$ can be found by using (for positive integer $n$):
$$
(a + b)^n = \begin{pmatrix}n\\0\end{pmatrix}a^nb^0 + \begin{pmatrix}n\\1\end{pmatrix}a^{n-1}b^1 + \begin{pmatrix}n\\2\end{pmatrix}a^{n-2}b^2 + \cdots + \begin{pmatrix}n\\n\end{pmatrix}a^0b^n
$$

The **binomial coefficient**, written $^n C_r$ or $\begin{pmatrix}n\\r\end{pmatrix}$ is given by:
$$\frac{n!}{r!(n-r)!}$$
Here, $n!$ denotes $n \times (n-1) \times (n-2) \cdots \times 1$. Note that $0! = 1$.

*IS*: The binomial coefficients are also given by Pascal's triangle, where the element of each row is found by summing the two elements immediately above. For example, the 4th row gives the coefficients in the expansion of $(a + b)^3$: $1, 3, 3, 1$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[x=0.8cm, y=0.8cm]
  \foreach \n in {0,...,4} {
    \foreach \k in {0,...,\n} {
      \node[font=\upshape] at (\k-\n/2, -\n) {
        \pgfmathparse{int(round(factorial(\n)/(factorial(\k)*factorial(\n-\k))))}\pgfmathresult
      };
    }
  }
  \node at (0, -4.8) {\vdots};
\end{tikzpicture}
\end{document}
```

#### General binomial expansion
The **general binomial expansion** works for any real value of $n$, and requires that $|x| \lt 1$ to be valid.
$$
(1+x)^n = 1 + nx + \frac{n(n-1)}{2!}x^2 + \frac{n(n-1)(n-2)}{3!}x^3 + \cdots

$$

To find the expansion of $(a + bx)^n$, factor out the $a^n$:
$$
(a + bx)^n = a^n\left(1 + \frac{b}{a}x\right)^n = a^n\left(1 + \frac{b}{a}x + \cdots\right)
$$
This expansion is valid for $\left|\frac{bx}{a}\right| \lt 1$.

