### Derivatives of inverse trigonometric functions
To **differentiate inverse trigonometric functions**, use **implicit differentiation**. For example, to differentiate $y = \sin^{-1}(x)$ for $|x| \lt 1$:
$$
\begin{split}
y &= \sin^{-1}(x) \\
\sin(y) &= x \\
\frac{\textrm{d}y}{\textrm{d}x}\,\cos(y) &= 1 \\
\frac{\textrm{d}y}{\textrm{d}x} &= \frac{1}{\cos(y)} \\
\frac{\textrm{d}y}{\textrm{d}x} &= \frac{1}{\sqrt{1 - \sin^2y}} \\
\frac{\textrm{d}y}{\textrm{d}x} &= \frac{1}{\sqrt{1 - x^2}}
\end{split}
$$
This derivation has two important details to consider:
- $\sin^{-1}(x)$ is defined for all $|x| \le 1$. However, the derivative of $\sin^{-1}(x)$ at $x = \pm 1$ does not exist (the graph goes infinitely steep), which is shown by $\frac{\textrm{d}y}{\textrm{d}x}$ being undefined for $x = \pm 1$.
- When rewriting $\cos y$ in terms of $x$ by using $\sin^2 x + \cos^2 x = 1$, we took the positive square root. This is because $\sin^{-1} x$ has a range of $\arcsin x \in [-\frac{\pi}{2}, \frac{\pi}{2}]$, and $\cos$ is positive over this domain, so we take the positive root.

Similar methods can be used to find all three inverse trigonometric function derivatives. *All of the following are given in the formula book*:
- $\frac{\textrm{d}}{\textrm{d}x}(\sin^{-1}(x)) = \frac{1}{\sqrt{1-x^2}}$ for $|x| \lt 1$ ($\sin^{-1}$ is defined for $|x| \le 1$).
- $\frac{\textrm{d}}{\textrm{d}x}(\cos^{-1}(x)) = \frac{-1}{\sqrt{1-x^2}}$ for $|x| \lt 1$ ($\cos^{-1}$ is defined for $|x| \le 1$).
- $\frac{\textrm{d}}{\textrm{d}x}(\tan^{-1}(x)) = \frac{-1}{\sqrt{1+x^2}}$ ($\tan^{-1}$ is defined for all $x \in \mathbb{R}$ and so is the derivative)

### Derivatives of inverse hyperbolic functions
To **differentiate inverse inverse functions**, again use **implicit differentiation**. For example, to differentiate $y = \sinh^{-1}(x)$ for $|x| \lt 1$:
$$
\begin{split}
y &= \sinh^{-1}(x) \\
\sinh(y) &= x \\
\frac{\textrm{d}y}{\textrm{d}x}\,\cosh(y) &= 1 \\
\frac{\textrm{d}y}{\textrm{d}x} &= \frac{1}{\cosh(y)} \\
\frac{\textrm{d}y}{\textrm{d}x} &= \frac{1}{\sqrt{1 + \sinh^2y}} \\
\frac{\textrm{d}y}{\textrm{d}x} &= \frac{1}{\sqrt{1 + x^2}}
\end{split}
$$
Note that here, the derivative of $\sinh^{-1}x$ exists for all $x$, but for $\cosh^{-1}x$, the derivative does not exist for $x=1$ as the [[6 - Hyperbolic Functions#Inverse hyperbolic functions|graph]] becomes infinitely steep.

Similar methods can be used to find all three inverse hyperbolic function derivatives. *All of the following are given in the formula book*:
- $\frac{\textrm{d}}{\textrm{d}x}(\sinh^{-1}(x)) = \frac{1}{\sqrt{x^2 + 1}}$ ($\sinh^{-1}$ is defined for all $x \in \mathbb{R}$).
- $\frac{\textrm{d}}{\textrm{d}x}(\cosh^{-1}(x)) = \frac{1}{\sqrt{x^2 - 1}}$ for $x \gt 1$ ($\cosh^{-1}$ is defined for $x \ge 1$).
- $\frac{\textrm{d}}{\textrm{d}x}(\tanh^{-1}(x)) = \frac{1}{1-x^2}$ for $|x| \lt 1$ ($\tanh^{-1}$ is defined for $|x| \lt 1$).

### Inverse trigonometric and hyperbolic functions for integration
By applying the **fundamental theorem of calculus**, we can reverse the results for differentiating the inverse functions to get new integration results:
$$
\begin{split}
\int \frac{1}{\sqrt{1 - x^2}}\,\textrm{d}x &= \sin^{-1}x + C \\
\int \frac{1}{x^2 + 1}\,\textrm{d}x &= \tan^{-1}x + C \\
\int \frac{1}{\sqrt{x^2 + 1}}\,\textrm{d}x &= \sinh^{-1}x + C \\
\int \frac{1}{\sqrt{x^2 - 1}}\,\textrm{d}x &= \cosh^{-1}x + C \\
\end{split}
$$

These results can be generalised by making a linear substitution $\frac{x}{a}$. *All the following results are given in the formula book*:
- $\int \frac{1}{\sqrt{a^2 - x^2}}\,\textrm{d}x = \sin^{-1}\left(\frac{x}{a}\right) + C$ for $|x| \lt a$
- $\int \frac{1}{x^2 + a^2}\,\textrm{d}x = \frac{1}{a}\tan^{-1}\left(\frac{x}{a}\right) + C$
- $\int \frac{1}{\sqrt{x^2+a^2}}\,\textrm{d}x = \sinh^{-1}\left(\frac{x}{a}\right) + C$
- $\int \frac{1}{\sqrt{x^2 - a^2}}\,\textrm{d}x = \cosh^{-1}\left(\frac{x}{a}\right) + C$ for $x > a$

Note that the $\cos^{-1}$ and $\tanh^{-1}$ results are not included:
- $\int \frac{-1}{\sqrt{1-x^2}}\,\textrm{d}x$ is just the negative of $\sin^{-1}$, giving $-\sin^{-1}x + C$ or $\cos^{-1} x + C$, which can be shown on a graph as $\sin^{-1}$ is a reflection of $\cos^{-1}$ in $y=\frac{\pi}{4}$.
- $\int \frac{1}{x^2 -1}\,\textrm{d}x = \tanh^{-1}x + C$ can just be done by partial fractions, which gives the same result as the logarithmic form of $\tanh^{-1}$.

#### Integrating forms with manipulation
Leading coefficients on the $x^2$ can be dealt with using reverse chain rule:
$$
\begin{split}
\int \frac{1}{\sqrt{3 - 5x^2}}\,\textrm{d}x &= \int \frac{1}{\sqrt{(\sqrt{3})^2 - (\sqrt{5}x) ^2}}\,\textrm{d}x \\ &= \frac{1}{\sqrt{5}}\sin^{-1}\left(\frac{\sqrt{5}x}{\sqrt{3}}\right) + C \\
\end{split}
$$
Or alternatively by factoring out the coefficient on $x$:
$$
\begin{split}
\int \frac{1}{\sqrt{3 - 5x^2}}\,\textrm{d}x 
&= \frac{1}{\sqrt5} \int \frac{1}{\sqrt{\frac{3}{5} - x^2}}\,\textrm{d}x \\ &= \frac{1}{\sqrt5} \int \frac{1}{\sqrt{\left(\frac{\sqrt3}{\sqrt5}\right)^2 - x^2}}\,\textrm{d}x \\
&= \frac{1}{\sqrt{5}}\sin^{-1}\left(\frac{\sqrt{5}}{\sqrt{3}}x\right) + C \\
\end{split}
$$

Other integrands may require **completing the square**:
$$
\begin{split}
\int \frac{1}{3x^2 + 8x + 6}\,\textrm{d}x 
&= \int \frac{1}{3\left(x + \frac{4}{3}\right)^2 + \frac{2}{3}}\,\textrm{d}x \\ &= \int \frac{1}{\left(\sqrt3\left(x + \frac{4}{3}\right)\right)^2 + \left(\frac{\sqrt2}{\sqrt3}\right)^2}\,\textrm{d}x 
\\ &= \frac{1}{\sqrt{3}} \times \frac{\sqrt3}{\sqrt2} \times\tan^{-1}\left(\frac{\sqrt{3}\,(x+\frac{4}{3})}{\frac{\sqrt2}{\sqrt3}}\right) + C
\\ &= \frac{\sqrt2}{2}\, \tan^{-1}\left(\frac{3\sqrt{2}\,(x+\frac{4}{3})}{2}\right) + C
\\ &= \frac{\sqrt2}{2}\, \tan^{-1}\left(\frac{\sqrt2}{2}(3x + 4)\right) + C
\end{split}
$$
These integrals often require very careful applications of the reverse chain rule.

#### Integrating using partial fractions
When there is a quadratic factor in the denominator of a rational expression, there are three different possibilities:
- The quadratic factors into two different linear factors, $(x-p)(x-q)$, giving partial fractions of $\frac{A}{x-p} + \frac{B}{x-q}$.
- The quadratic is a perfect square, $(x-p)^2$, giving partial fractions of $\frac{A}{x-p} + \frac{B}{(x-p)^2}$.
- The quadratic does not factorise (it is irreducible), giving a fraction of the form $\frac{Dx + E}{Ax^2 + Bx + C}$. This can be integrated using $\tan^{-1}$, but could require completing the square first.

#### Derivations
The derivations of the 4 given results could be tested. Below are the full derivations. All of the derivations follow the same basic pattern:
- Substitute $x = a\,f(u)$
- Apply $\sin^2x + \cos^2x = 1$ or $\cosh^2x - \sinh^2x = 1$
- Simplify and integrate
- Substitute back for $u$ to get the desired answer.
##### Inverse sine
Working towards $I = \int \frac{1}{\sqrt{a^2 - x^2}}\,\textrm{d}x = \sin^{-1}\left(\frac{x}{a}\right) + C$
- Apply the substitution $x = a\sin u$ with $\textrm{d}x = a\cos u \,\textrm{d}u$
- The substitution gives $I = \int\frac{a\cos u}{\sqrt{a^2 - a^2\sin^2u}}\,\textrm{d}u$
- Cancel the common factor of $a$ to get $I = \int\frac{\cos u}{\sqrt{1 - \sin^2u}}\,\textrm{d}u$
- Apply $\sin^2 u + \cos^2 u = 1$ to get $I = \int\frac{\cos u}{\cos u}\,\textrm{d}u = \int1\,\textrm{d}u$
- Integrate to get $I = u + C$
- Substitute $u$ with $\sin^{-1}\left(\frac{x}{a}\right)$ to get $I = \sin^{-1}\left(\frac{x}{a}\right) + C$

##### Inverse tangent
Working towards $I = \int \frac{1}{x^2 + a^2}\,\textrm{d}x = \frac{1}{a}\tan^{-1}\left(\frac{x}{a}\right) + C$
- Apply the substitution $x = a\tan u$ with $\textrm{d}x = a\sec^2 u \,\textrm{d}u$
- The substitution gives $I = \int\frac{a\sec^2 u}{a^2\tan^2 u + a^2}\,\textrm{d}u$
- Cancel the common factor of $a$ to get $I = \frac{1}{a} \int\frac{\sec^2 u}{\tan^2 u + 1}\,\textrm{d}u$
- Apply $\tan^2 u + 1 = \sec^2 u$ to get $I = \frac{1}{a} \int\frac{\sec^2 u}{\sec^2 u + 1}\,\textrm{d}u = \frac{1}{a} \int1\,\textrm{d}u$
- Integrate to get $I = \frac{u}{a} + C$
- Substitute $u$ with $\tan^{-1}\left(\frac{x}{a}\right)$ to get $I = \frac{1}{a}\tan^{-1}\left(\frac{x}{a}\right) + C$

##### Inverse hyperbolic sine
Working towards $I = \int \frac{1}{\sqrt{x^2 + a^2}}\,\textrm{d}x = \sinh^{-1}\left(\frac{x}{a}\right) + C$
- Apply the substitution $x = a\sinh u$ with $\textrm{d}x = a\cosh u \,\textrm{d}u$
- The substitution gives $I = \int\frac{a\cosh u}{\sqrt{a^2\sinh^2 u + a^2}}\,\textrm{d}u$
- Cancel the common factor of $a$ to get $I = \int\frac{\cosh u}{\sqrt{\sinh^2 u + 1}}\,\textrm{d}u$
- Apply $\cosh^2 u = \sinh^2 u + 1$ to get $I = \int\frac{\cosh u}{\cosh u}\,\textrm{d}u = \int1\,\textrm{d}u$
- Integrate to get $I = u + C$
- Substitute $u$ with $\sinh^{-1}\left(\frac{x}{a}\right)$ to get $I = \sinh^{-1}\left(\frac{x}{a}\right) + C$

##### Inverse hyperbolic cosine
Working towards $I = \int \frac{1}{\sqrt{x^2 - a^2}}\,\textrm{d}x = \cosh^{-1}\left(\frac{x}{a}\right) + C$
- Apply the substitution $x = a\cosh u$ with $\textrm{d}x = a\sinh u \,\textrm{d}u$
- The substitution gives $I = \int\frac{a\sinh u}{\sqrt{a^2\cosh^2 u - a^2}}\,\textrm{d}u$
- Cancel the common factor of $a$ to get $I = \int\frac{\sinh u}{\sqrt{\cosh^2 u - 1}}\,\textrm{d}u$
- Apply $\sinh^2 u = \cosh^2 u - 1$ to get $I = \int\frac{\sinh u}{\sinh u}\,\textrm{d}u = \int1\,\textrm{d}u$
- Integrate to get $I = u + C$
- Substitute $u$ with $\cosh^{-1}\left(\frac{x}{a}\right)$ to get $I = \cosh^{-1}\left(\frac{x}{a}\right) + C$
