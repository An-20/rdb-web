## Proof by Induction
The principle of mathematical induction involves:
- Proving a statement is true for $n = 1$ (the basis case)
- Proving that if you assume the statement is true for $n = k$, then you can prove that it is also true for $n = k + 1$.

Much like dominoes falling, the proof for $n = 1$ causes the proofs for $n = 2, 3, 4, \dots$ to fall into place, proving the statement to be true for all positive integers $n$.

Series and induction are covered at Further Maths Pure. This builds on existing knowledge of [[Sequences and Series]] from single Maths, and is further developed in [[Further Sequences and Series]] in Further Maths Additional Pure.

## Standard series
The following formulae can be used without proof, where the second and third formulae are *given* in the formula book:
$$
\begin{split}
\sum_{r=1}^{n}{r} &= \frac{1}{2}n(n+1) \\
\sum_{r=1}^{n}{r^2} &= \frac{1}{6}n(2n+1)(n+1) \\
\sum_{r=1}^{n}{r^3} &= \frac{1}{4}n^2 (n+1)^2 \\
\end{split}
$$

Series can be manipulated in the following ways:
$$
\begin{split}
&\sum{u_r + v_r} = \sum{u_r} + \sum{v_r} \\
&\sum{cu_n} = c \sum{u_n} \\
&\sum_{r=1}^{n}{c} = nc
\end{split}
$$

## Method of differences
If the general term of a series can be written as $u_r = f(r+1) - f(r)$, then the **method of differences** can be applied:
$$
\sum_{r=1}^n u_r = f(n+1) - f(1)
$$
The series won't always take this exact form; sometimes cancellations can happen two terms apart. This form can often be obtained using **partial fractions**. When using the method of differences, make it clear what the cancellation pattern is.

###### Example
Find a formula for the $n^{\textsf{th}}$ term of the series:
$$
\sum_{r=1}^{n} \frac{1}{(r+1)(r+2)} = \sum_{r=1}^{n} \left(\frac{1}{r+1} - \frac{1}{r+2}\right)
$$
We start by writing out the first terms of the series to try and spot a pattern. Each term contains a negated element from the previous one:
$$
\begin{split}
\sum_{r=1}^{n} \left(\frac{1}{r+1} - \frac{1}{r+2}\right) &= \frac{1}{2} - \bcancel{\textcolor{red}{\frac{1}{3}}} \\

&+ \bcancel{\textcolor{red}{\frac{1}{3}}} - \bcancel{\textcolor{orange}{\frac{1}{4}}} \\

&+ \bcancel{\textcolor{orange}{\frac{1}{4}}} - \bcancel{\textcolor{yellowgreen}{\frac{1}{5}}} \\

&+ \bcancel{\textcolor{yellowgreen}{\frac{1}{5}}} - \bcancel{\textcolor{cyan}{\frac{1}{6}}} \\

&\hspace{0.5em} \vdots \\

&+ \bcancel{\textcolor{lavender}{\frac{1}{n}}} - \bcancel{\textcolor{violet}{\frac{1}{n+1}}} \\

&+ \bcancel{\textcolor{violet}{\frac{1}{n+1}}} - \frac{1}{n+2} \\

&= \frac{1}{2} - \frac{1}{n+2}
\end{split}
$$
When summing these terms, the matched pairs cancel, leaving only the terms in white, so $\sum_{r=1}^{n} \frac{1}{(r+1)(r+2)} = \frac{1}{2} - \frac{1}{n+2}$.
