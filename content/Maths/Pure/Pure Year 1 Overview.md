## Proof
#### Logical connectives
The three logical connectives are:
- If P, then Q ($P \implies Q$)
- If and only if P, then Q ($P \iff Q$)
- P is implied by Q ($P \impliedby Q$) (not in spec)

#### Disproof by counter example
Disproof by counter example involves disproving an "if $P$ then $Q$" statement by finding an example where $P$ is true but $Q$ is not. 

#### Identities
An identity is a relation that is true for all values of the variable. An identity uses the symbol $\equiv$, and the two sides of the identity are congruent expressions.

#### Sets of numbers
##### Integers
$\mathbb{Z}$ - whole numbers.
##### Real numbers
$\mathbb{R}$ - any number on the real number line, including all rational and irrational numbers.
##### Rational numbers
$\mathbb{Q}$ - any number than can be represented as $\frac{p}{q}$, where p and q are integers, and $q$ is nonzero.
##### Irrational numbers
Any real number that is not rational, e.g. $\pi$ or $\sqrt{2}$.

#### Inequality notation
##### Interval notation
A round bracket $($ or $)$ means the number is not included, e.g. $(3, 5)$ is the interval from 3 to 5, non-inclusive. A  square bracket $[$ or $]$ means the number is included, e.g. $[3, 5]$ means the interval from 3 to 5, inclusive.
##### Equivalent interval notation
-  $x \gt a$: $x \in (a, \infty)$
-  $x \lt a$: $x \in (-\infty, a)$
-  $x \ge a$: $x \in [a, \infty)$
-  $x \le a$: $x \in (-\infty, a]$
-  $a \lt x \lt b$: $x \in (a, b)$
-  $a \lt x \le b$: $x \in (a, b]$
-  $x \lt a$ or $x \ge b$: $x \in (-\infty, a) \cup [b, \infty)$


## Indices
#### Laws of indices
- Multiplication: $x^a \times x^b = x^{a+b}$
- Division: $x^a \div x^b = x^{a-b}$
- Exponentiation: $(x^a)^b = x^{ab}$
- Fractional exponents: $x^{1/a} = \root{a}\of{x}$
- Negative exponents$x^{-a} = \frac{1}{x^a}$
#### Rationalising the denominator
To rationalise the denominator of a fraction, multiply by the conjugate radical of the denominator (e.g. $a - b\sqrt{c}$ for $a + b\sqrt{c}$) to create a difference of two squares.


## Quadratics
#### Quadratic formula
$$
x = \frac{-b \pm \sqrt{b^2-4ac}}{2a}
$$
###### Derivation
The quadratic formula can be derived by completing the square on a general quadratic $ax^2 + bx + c = 0$.
##### Discriminant
The discriminant of a quadratic equation $ax^2 + bx + c = 0$ is $b^2 - 4ac$.
###### Meaning
$Δ \gt 0$ has two distinct real roots.
$Δ=0$ has one repeated real root.
$Δ \lt 0$ has no real roots.
##### Line of symmetry
The line of symmetry is at $x = \frac{-b}{2a} = \frac{x_1 + x_2}{2}$.


## Polynomials
#### Factor theorem
$(ax-b)$ is a factor of $f(x)$ if and only if $f(\frac{b}{a}) = 0$.
#### Graph sketching
Consider:
- The basic shape based on the degree and the lead coefficient.
- The y-intercept.
- The x-intercepts (roots).
- How the curve meets each root (e.g. repeated roots, point of inflection).


## Graph transformations
###### Translation vertically by $\begin{pmatrix}0\\a\end{pmatrix}$
$f(x) + a$
###### Translation horizontally by $\begin{pmatrix}a\\0\end{pmatrix}$
$f(x - a)$
###### Vertical stretch, scale factor a, relative to the $x$-axis
$af(x)$
###### Horizontal stretch, scale factor $\frac{1}{a}$, relative to the $y$-axis
$f(ax)$
###### Reflection in the $x$-axis
$-f(x)$
###### Reflection in the $y$-axis
$f(-x)$


## Coordinate geometry
#### Straight line equations
$y = mx + c$
$y - y_1 = m(x - x_1)$
$ax + by + c = 0$
#### Midpoint of two points
$(\frac{x_1 + x_2}{2}, \frac{y_1 + y_2}{2})$
#### Distance between two points
$\sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}$
#### Perpendicular lines
Perpendicular lines have gradients that multiply to -1.
#### Circle equation
$(x-a)^2 + (y-b)^2 = r^2$ for a circle centred at $(a, b)$ with radius $r$.
#### Circle theorems
- The angle in a semicircle is a right angle.
- The perpendicular from the centre of a circle to a chord bisects the chord.
- The radius of a circle is perpendicular to a tangent at the circumference.
#### Intersections of circles
There are 5 cases (where $r_1 \gt r_2$):
- $d \gt r_1 + r_2$: The two circles do not intersect, with the smaller circle outside the larger circle.
- $d = r_1 + r_2$: The two circles intersect in one place, where they are tangent, with the smaller circle outside the larger circle (externally tangent).
- $r_1 - r_2 \lt d \lt r_1 + r_2$: The two circles intersect in two places.
- $d = r_1 - r_2$: The two circles intersect in one place, where they are tangent, with the smaller circle inside the larger circle (internally tangent).
- $d \lt r_1 - r_2$: The two circles do not intersect, with the smaller circle inside the larger circle.


## Logarithms
#### Rules of logarithms
- Converting: $a^b = c \iff \log_a(c) = b$
- Multiplication$\log_b(xy) = \log_b(x) + \log_b(y)$
- Division: $\log_b(\frac{x}{y}) = \log_b(x) - \log_b(y)$
- Exponentiation: $\log_b(x^y) = y\log_b(x)$
#### Specific bases
###### Base $e$
Logarithms in base $e$ are written as $\ln x$.
###### Base 10
Logarithms in base 10 are written as $\log x$.
#### Graph sketching
A logarithmic function of the form $y = \log_b(x)$ has:
- An $x$-intercept of $(1, 0)$
- The $y$-axis as an asymptote.


## Exponentials
#### Graph sketching
An exponential of the form $y = a^x$ has:
- A $y$-intercept of $(0, 1)$
- All $y \gt 0$
- The $x$-axis as an asymptote.
#### Growth and decay
For an exponential of the form $y = a^x$:
- If $a \gt 1$, then $y$ increases as $x$ increases - exponential growth.
- If $0 \lt a \lt 1$, then $y$ decreases as $x$ increases - exponential decay.
#### Modelling
Exponential functions are used to model situations where the rate of growth or decay is proportional to the current amount. This is because the derivative of $e^{kx}$ is $ke^{kx}$.
###### Equation
A model with equation $y = Ae^{kt}$ has:
- Initial value ($t=0$) of $y = A$
- A rate of change of $ky$.
##### Straightening graphs
###### Exponential
For a graph $y = Ab^x$, taking $\ln$ on both sides gives:
$$
\ln y = x\ln b + \ln A
$$
Thus when plotting $\ln y$ against $x$, the gradient is $\ln b$ and $y$-intercept is $\ln A$.
###### Polynomial
For a graph $y = Ax^b$, taking $\ln$ on both sides gives:
$$
\ln y = b\ln x + \ln A 
$$
Thus when plotting $\ln y$ against $\ln x$, the gradient is $b$ and the $y$-intercept is $\ln A$.


## Binomial expansion
The expansion of $(a + b)^n$ can be found by using the expansion:
$$
(a + b)^n = \begin{pmatrix}n\\0\end{pmatrix}a^nb^0 + \begin{pmatrix}n\\1\end{pmatrix}a^{n-1}b^1 + \begin{pmatrix}n\\2\end{pmatrix}a^{n-2}b^2 + \cdots + \begin{pmatrix}n\\n\end{pmatrix}a^0b^n
$$
#### Binomial coefficient
The binomial coefficient, written $^n C_r$ or $\begin{pmatrix}n\\r\end{pmatrix}$ is given by:
$$\frac{n!}{r!(n-r)!}$$


## Trigonometry
#### Trig identities
$$
\begin{split}
\sin^2\theta + \cos^2\theta = 1\\\\
\tan\theta = \frac{\sin\theta}{\cos\theta}
\end{split}
$$
#### Sine rule
$$
\frac{a}{\sin A} = \frac{b}{\sin B} = \frac{c}{\sin C}
$$
When using the sine rule to find angles, sometimes there may be two possible answers, $A$ and $180\degree - A$.
#### Cosine rule
$$
a^2 = b^2 + c^2 - 2bc\cos A
$$
#### Area of a triangle
$$
\frac{1}{2}ab\sin C
$$


## Vectors
A vector has both magnitude and direction. 
###### Magnitude
The magnitude of a vector is denoted $|\boldsymbol{a}|$ and can be found using the Pythagorean theorem.
###### Direction
The direction of a vector is measured anticlockwise from the positive $x$ axis and can be found using $\tan^{-1}$.
###### Unit vector
A unit vector has a magnitude of 1.
###### Operations
Vectors can be, added, subtracted, and multiplied by a scalar.
###### Parallel vectors
If vectors $\boldsymbol{a}$ and $\boldsymbol{b}$ are parallel then for some scalar $k$, $\boldsymbol{a} = k\boldsymbol{b}$.

#### Position vectors
Vectors can represent positions of points or the displacement between two points. The position vector of a point is a vector from the origin to that point.
###### Displacement vector
For two points $A$ and $B$ with position vectors $\boldsymbol{a}$ and $\boldsymbol{b}$, the displacement vector from $A$ to $B$, $\overrightarrow{AB}$, is given by $\boldsymbol{b} - \boldsymbol{a}$.
###### Distance
The distance between two points $A$ and $B$ with position vectors $\boldsymbol{a}$ and $\boldsymbol{b}$ is the magnitude of the displacement vector: $AB = |\overrightarrow{AB}| = |\boldsymbol{b} - \boldsymbol{a}$.

#### Geometric properties
###### Midpoint
The midpoint of the line segment of two points $A$ and $B$ with position vectors $\boldsymbol{a}$ and $\boldsymbol{b}$ is $\frac{1}{2}(\boldsymbol{a} + \boldsymbol{b})$.
###### Parallelograms
Parallelograms have vectors for opposite sides with equal magnitude.
###### Rhombuses
Rhombuses have vectors for all four sides with equal magnitude.

## Differentiation
#### First principles
$$
f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$
#### Rules
###### Derivative of $y = x^n$
$\frac{\text{d}y}{\text{d}x} = nx^{n-1}$
###### Derivative of $y = kf(x)$, where $k$ is a constant:
$\frac{\text{d}y}{\text{d}x} = kf'(x)$
###### Derivative of $y = f(x) + g(x)$
$\frac{\text{d}y}{\text{d}x} = f'(x) + g'(x)$

#### Increasing and decreasing functions
The sign of the derivative at a point shows whether the function is increasing or decreasing:
- If $\frac{\text{d}y}{\text{d}x} \gt 0$, the function is increasing.
- If $\frac{\text{d}y}{\text{d}x} \lt 0$, the function is decreasing.

#### Higher derivatives
The second derivative is denoted $\frac{\text{d}^2y}{\text{d}x^2}$ or $f''(x)$. It measures the gradient of the gradient, or the rate of change of the gradient with respect to $x$.

#### Tangents and normals
For a point on $y = f(x)$:
- The gradient of the tangent is $f'(x)$,
- The gradient of the normal is $-\frac{1}{f'(x)}$

#### Stationary points
At the local maxima and minima, $\frac{dy}{dx} = 0$. This can be used for optimisation questions.
###### Nature
Given a stationary point:
- If $\frac{d^2x}{dy^2} \lt 0$ at that point, then it is a local maximum.
- If $\frac{d^2x}{dy^2} \gt 0$ at that point, then it is a local minimum.
- If $\frac{d^2x}{dy^2} = 0$ at that point, then no conclusion can be reached.

## Integration
#### Fundamental theorem of calculus
$$
\intop f(x)\,dx = F(x) + c \iff f(x) = \frac{d}{dx}F(x)
$$
Integration is the opposite of differentiation.

#### Integral of polynomials
For all rational $n \neq 1$:
$$
\intop x^n dx = \frac{1}{n + 1}x^{n+1} + C
$$

#### Definite integrals
The definite integral $\intop^b_a f(x) dx$ is found by evaluating the integrated expression at the upper limit $b$ and subtracting the integrated expression evaluated at the lower limit $a$. This gives the signed area.

If the integrand changes sign between the two limits, then the interval needs to be split to find the total area.
