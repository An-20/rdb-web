#### Reduction formulae
**Reduction formulae** can be used to evaluate integrals using **recursive techniques**. Often, they are useful for integrals with a function raised to a power, where integration by parts can then be applied.

#### Arc lengths
The **arc length** of a curve is shown below.
```tikz
\usetikzlibrary{arrows.meta}
\begin{document}
\begin{tikzpicture}[x=0.6cm, y=0.6cm] % Adjust scale of the whole diagram

    % --- Axis Ticks and Labels ---
    % X-axis ticks
    \foreach \x in {-2, -1, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
        \draw[thick] (\x, 0.15) -- (\x, -0.15) node[below, font=\small] {\x};
        
    % Y-axis ticks
    \foreach \y in {-1, 1, 2, 3, 4, 5, 6, 7, 8}
        \draw[thick] (0.15, \y) -- (-0.15, \y) node[left, font=\small] {\y};

    % Origin label
    \node[below left] at (0,0) {$O$};

    % --- Draw Axes ---
    \draw[very thick, -{Stealth[length=3mm]}] (-2.5, 0) -- (11, 0) node[right] {$x$};
    \draw[very thick, -{Stealth[length=3mm]}] (0, -1.5) -- (0, 9) node[above] {$y$};

    % --- Draw Parabola ---
    % Using a scaling factor (0.1*x^2) to match the visual "flatness" of the original image
    \draw[very thick, domain=-2:9.5, smooth, variable=\x] plot ({\x}, {0.1*\x*\x});
    \node[right] at (9, 8.1) {$y = x^2$};

    % --- Highlighted Arc Segment ---
    % Using a thicker line for the segment between x=4 and x=7.5
    \draw[line width=3pt, domain=4:7.5, smooth, variable=\x] plot ({\x}, {0.1*\x*\x});

    % --- Annotation ---
    \draw[thick, Stealth-] (5.8, 3.4) -- (8, 2.5) 
        node[below, align=center] {Arc length $s$};

\end{tikzpicture}
\end{document}
```

The arc length of $y = f(x)$ between $a$ and $b$ is given by:
$$
s = \int^a_b\sqrt{1+\left(\frac{\text{d}y}{\text{d}x}\right)^2}\text{d}x
$$
Or, alternatively, for a parametric curve where $\dot x$ and $\dot y$ are the derivatives of $x$ and $y$ with respect to $t$ (between $t = a$ and $t = b$):
$$
s = \int^a_b\sqrt{\dot x^2 + \dot y^2}\,\,\text{d}t = \int^a_b\sqrt{\left(\frac{\text{d}x}{\text{d}t}\right)^2 + \left(\frac{\text{d}y}{\text{d}t}\right)^2}\,\,\text{d}t
$$
The formulae for arc length are *given* in the formulae booklet.

#### Surface areas of revolution
The **surface area of revolution** for $y = f(x)$ resolved about the $x$-axis between $a$ and $b$ is given by:
$$
S_x = 2\pi \int_a^b y\,\sqrt{1+\left(\frac{\text{d}y}{\text{d}x}\right)^2}\text{d}x
$$
Or, alternatively, for a parametric curve in terms of $t$ resolved about the $x$-axis between $t = a$ and $t = b$:
$$
S_x = 2\pi \int_a^b y(t)\,\sqrt{\left(\frac{\text{d}x}{\text{d}t}\right)^2 + \left(\frac{\text{d}y}{\text{d}t}\right)^2}\,\text{d}t
$$


The surface area of revolution for $x = f(y)$ resolved about the $y$-axis between $a$ and $b$ is given by:
$$
S_y = 2\pi \int_a^b x\,\sqrt{1+\left(\frac{\text{d}x}{\text{d}y}\right)^2}\text{d}y
$$
Or, alternatively, for a parametric curve in terms of $t$ resolved about the $y$-axis between $t = a$ and $t = b$:
$$
S_y = 2\pi \int_a^b x(t)\,\sqrt{\left(\frac{\text{d}x}{\text{d}t}\right)^2 + \left(\frac{\text{d}y}{\text{d}t}\right)^2}\,\text{d}t
$$
The formulae for surface areas of revolution are *given* in the formulae booklet.
