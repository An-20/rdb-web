In 3D, a **surface** can be described by all the points such that $z = \text{f}(x,y)$ or $c = \text{f}(x,y,z)$ for some constant $c$. The $x-y$ plane is horizontal and the $z$-axis is vertical. 

A visualisation of $z = x^2-y^2$:
```tikz
\usepackage{tikz}
\usepackage{amsmath}
\usepackage{pgfplots}
\pgfplotsset{compat=newest}
\pgfplotsset{
            layers/my layer set/.define layer set={
            background,
            main,
            foreground
        }{
           },
           set layers=my layer set,
    }
\begin{document}
    \begin{tikzpicture}
        \begin{axis}[
	        view={25}{30},
	        xlabel={$x$},
			ylabel={$y$},
			zlabel={$z$},
			zlabel style={rotate=-90}
        ]

            \addplot3 [color=white, draw=none, mark=*, mark size=2]
                table[row sep=crcr] {%
                0 0 15\\
                0 0 -15\\
                };

            \addplot3 [
                surf,
                shader=faceted,
                fill opacity=0.75,
                samples=12,
                domain=-4:4,
                y domain=-4:4,
                on layer=foreground,
                ] {x^2-y^2};

        \end{axis}
   \end{tikzpicture} 
\end{document}
```

###### Sections
A **section** is a cross-section of the surface for specific values of $x$ or $y$: $z = \text{f}(a,y)$ or $z = \text{f}(x,b)$ for constants $a$ or $b$.
A visualisation of sections through $z = x^2-y^2$:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\begin{tikzpicture}[scale=0.8]

  \begin{scope}[shift={(0,0)}]
	  \draw[->] (-3, 0) -- (3, 0) node[right] {$y$};
	  \draw[->] (0, -3) -- (0, 3) node[above] {$z$};
	  \draw[scale=0.5, domain=-5:5, smooth, variable=\x, black] plot ({\x}, {-0.2*\x*\x});
	  \node[align=left] at (0, -3.5) {$x=0$};
  \end{scope}
  
  \begin{scope}[shift={(8,0)}]
	  \draw[->] (-3, 0) -- (3, 0) node[right] {$x$};
	  \draw[->] (0, -3) -- (0, 3) node[above] {$z$};
	  \draw[scale=0.5, domain=-5:5, smooth, variable=\x, black] plot ({\x}, {0.2*\x*\x});
	  \node[align=left] at (0, -3.5) {$y=0$};
  \end{scope}

\end{tikzpicture}
\end{document}
```

###### Contours
A **contour** is a curve where the value of $z$ is fixed: $\text{f}(x,y)=c$ for some constant $c$.
A visualisation of contours of $z=4x^2+y^2=c$, with $c=1,4,9,16$:
```tikz 
\usepackage{tikz}
\usepackage{amssymb,amsfonts,amsmath}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\usepackage{pgfplots}
\pgfplotsset{compat=newest}
\pgfplotsset{
            layers/my layer set/.define layer set={
            background,
            main,
            foreground
        }{
           },
           set layers=my layer set,
    }
\begin{document}
\begin{tikzpicture}[scale=0.8]

  \begin{scope}[shift={(0,-12)}]
        \begin{axis}[
	        view={25}{30},
	        xlabel={$x$},
			ylabel={$y$},
			zlabel={$z$},
			zlabel style={rotate=-90}
        ]

            \addplot3 [color=white, draw=none, mark=*, mark size=2]
                table[row sep=crcr] {%
                0 0 5\\
                0 0 0\\
                };

            \addplot3 [
                surf,
                shader=faceted,
                fill opacity=0.75,
                samples=12,
                domain=-3:3,
                y domain=-3:3,
                on layer=foreground,
                ] {4*x^2+y^2};

        \end{axis}
    \end{scope}

  \begin{scope}[shift={(12,0)}]
	  \draw[->] (-3, 0) -- (3, 0) node[right] {$y$};
	  \draw[->] (0, -3) -- (0, 3) node[above] {$z$};
	  \draw[scale=0.5, domain=-0.5:0.5, smooth, variable=\x, black] plot ({\x}, {sqrt(1 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-0.5:0.5, smooth, variable=\x, black] plot ({\x}, {-sqrt(1 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-1:1, smooth, variable=\x, black] plot ({\x}, {sqrt(4 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-1:1, smooth, variable=\x, black] plot ({\x}, {-sqrt(4 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-1.5:1.5, smooth, variable=\x, black] plot ({\x}, {sqrt(9 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-1.5:1.5, smooth, variable=\x, black] plot ({\x}, {-sqrt(9 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-2:2, smooth, variable=\x, black] plot ({\x}, {sqrt(16 - 4*\x*\x)});
	  \draw[scale=0.5, domain=-2:2, smooth, variable=\x, black] plot ({\x}, {-sqrt(16 - 4*\x*\x)});
	  \node[align=left] at (0, -3.5) {$x=0$};
	\end{scope}
\end{tikzpicture}
\end{document}
```
#### Partial differentiation
For a surface defined as:
$$
z = \text{f} = \text{f}(x, y)
$$
The **partial derivatives** of $\text{f}$ are denoted as:
- $\text{f}_{x}= \frac{\partial \text{f}}{\partial x}$: differentiate $\text{f}$ with respect to $x$, treating $y$ as constant.
- $\text{f}_{y}= \frac{\partial \text{f}}{\partial y}$: differentiate $\text{f}$ with respect to $y$, treating $x$ as constant.

**Higher-order** partial derivatives are denoted as:
- $\text{f}_{xx} = \frac{\partial}{\partial x} \left(\frac{\partial \text{f}}{\partial x}\right) = \frac{\partial^2 \text{f}}{\partial x^2}$: partially differentiate $\text{f}$ with respect to $x$ twice
- $\text{f}_{yy} = \frac{\partial}{\partial y} \left(\frac{\partial \text{f}}{\partial y}\right) = \frac{\partial^2 \text{f}}{\partial y^2}$: partially differentiate $\text{f}$ with respect to $y$ twice
- $\text{f}_{xy} = \frac{\partial}{\partial x} \left(\frac{\partial \text{f}}{\partial y}\right) = \frac{\partial^2 \text{f}}{\partial x \partial y}$: partially differentiate $\text{f}$ with respect to $y$, then $x$[^1]
- $\text{f}_{yx} = \frac{\partial}{\partial y} \left(\frac{\partial \text{f}}{\partial x}\right) = \frac{\partial^2 \text{f}}{\partial y \partial x}$: partially differentiate $\text{f}$ with respect to $x$, then $y$[^1]

The **mixed derivative theorem** states that for most well-behaved continuous functions:
$$
\text{f}_{xy} = \text{f}_{yx} \implies \frac{\partial^2\text{f}}{\partial x \partial y} = \frac{\partial^2 \text{f}}{\partial y \partial x}
$$
###### Stationary points
When $\text{f}_{x}= 0$ and $\text{f}_{y} = 0$ there is a stationary point. A stationary point can be a minimum, maximum, or a saddle point (classification of stationary points is A-level content).

[^1]: **Footnote on order of mixed derivatives**
	This is the order that the textbook insists is correct, whilst the rest of the Internet disagrees. Practically, it doesn't matter as on this course, all functions will likely satisfy the mixed derivative theorem. This may be corrected soon pending further investigation (The author is severely sleep deprived).
