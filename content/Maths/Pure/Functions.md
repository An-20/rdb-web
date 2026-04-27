## Overview
A **mapping** takes values from a given input set and maps each of them to one or more output values. For example, $y = \pm x$ is a mapping:
```tikz
\begin{document}
\begin{tikzpicture}[>=stealth]
    \draw[->] (-0.5,0) -- (3.5,0) node[right] {$x$};
    \draw[->] (0,-2.0) -- (0,2.0) node[above] {$y$};
    \draw[thick, domain=0.0:3, samples=100] 
        plot (\x, {sqrt(\x)}) 
        node[right] {$y = \pm \sqrt{x}$};
    \draw[thick, domain=0.0:3, samples=100] plot (\x, {-sqrt(\x)});
\end{tikzpicture}
\end{document}
```

A **function** is a mapping where every value maps to a single output value. Functions are defined by a rule from input to output, and a set for the domain. Functions can be **one-to-one**, or **many-to-one**. Functions can be shown by the vertical line test, while one-to-one functions are shown by the horizontal line test.

Definitions:
- The **image** of an input value $x$ is the corresponding output value of the function.
- The **domain** is the set of possible input values to the function.
- The **range** is the set of possible output values of the function.
- The **composite function** formed by applying $g$ to $x$ and then applying $f$ to the result is denoted $f(g(x)$, $fg(x)$, or $f\circ g(x)$.
- The notation $f^n(x)$ represents $f$ applied to $x$ $n$ times, e.g. $f^2(x) = f(f(x))$, apart from trig functions.

#### Inverse functions
The **inverse function** of $f(x)$ is $f^{-1}(x)$, such that:
$$
f(f^{-1}(x)) = x
$$
The inverse function only exists for one-to-one functions. To find the inverse function, start with $y = f(x)$, rearrange for $x$, and replace the $y$s with $x$.

The **domain** of $f^{-1}(x)$ is the same as the range of $f(x)$.  The **range** of $f^{-1}(x)$ is the same as the domain of $f(x)$. Graphically, the graph of $f^{-1}(x)$ is a reflection of $f(x)$ in the line $y = x$.


## Graph transformations
Combining graph transformations of the $x$ and $y$ axis can be done by considering each axis individually. However, combing graph transformations on the same axis is different for both axes.
#### $y$-axis translations and stretches
For the $y$-axis, $y = af(x) + b$ transforms the graph of $y = f(x)$ by first stretching it by scale factor $a$ parallel to the $y$-axis, then translating by $b$ units in the positive $y$ direction.
#### $x$-axis combined transformations
For the $x$-axis, $y = f(ax + b)$ transforms the graph of $y = f(x)$ by first translating by $b$ units in the negative $x$ direction, then stretching by scale factor $a$ parallel to the $x$ axis. This can be thought of as first replacing the $x$ with $x + b$ (translating), then replacing the $x$ in $x + b$ with $ax$ (stretching.)


## Modulus functions
The **modulus function** reflects parts of a graph below the $x$ axis to be above the axis. It is defined as: 
$$
|x| = 
\begin{cases} 
-x & \text{if } x < 0 \\ 
x & \text{otherwise} 
\end{cases}
$$

#### Graph
The graph of $y = |mx + c|$ has a 'V' shape, with a gradient of $\pm m$, $y$-intercept of $c$, and a vertex at $x = -\frac{c}{m}$.


## Partial fractions
A **rational function** cam be expressed as an algebraic fraction where both the numerator and denominator are polynomials e.g.$\frac{P(x)}{Q(x)}$. 

A **proper** rational function is where the degree of the numerator is strictly less than the degree of the denominator. To make an improper rational function proper, polynomial division can be used:
$$
\frac{P(x)}{ax + b} = Q(x) + \frac{r}{ax + b}
$$

A proper rational function can be decomposed into partial fractions:
$$
\begin{split}
\frac{ax+b}{(x+p)(x+q)} &= \frac{A}{x+p} + \frac{B}{x+q} \\\\
\frac{ax+b}{(x+p)(x+q)(x+r)} &= \frac{A}{x+p} + \frac{B}{x+q} + \frac{C}{x+r} \\\\
\frac{ax+b}{(x+p)(x+q)^2} &= \frac{A}{x+p} + \frac{B}{x+q} + \frac{C}{(x+q)^2}
\end{split}
$$
Note that repeated factors require a fraction with a denominator of the single factor, and a fraction with a denominator of the repeated factor.
