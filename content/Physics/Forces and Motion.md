## Displacement and Velocity
**Displacement** is a vector quantity that represents an object's distance and direction away from its starting point. The related scalar is distance.

**Velocity** is a vector quantity that represents how fast and in what direction an object is moving. The related scalar is speed.

The gradient of a displacement-time graph gives velocity.
The gradient of a velocity-time graph gives acceleration.
The area under a velocity-time graph gives displacement.

Vectors can be resolved into components:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\coordinate[label=below:$$](A) at (0, 0);
	\coordinate[label=below:$$](B) at (4, 0);
	\coordinate[label=right:$$](C) at (4, 2);
	\coordinate[label=above left:$v$](D) at (2, 1);
	\draw[thick, dotted] (A) -- (B);
	\draw[thick, dotted] (B) -- (C);
	\draw[very thick, ->] (A) -> (C);
	\draw (3.8,0) rectangle (4.0,.2);
	
	\node at (2, -0.2) {$v\cos\theta$};
	\node at (4.6, 1) {$v\sin\theta$};
	\node at (0.75, 0.15) {$\theta$};
\end{tikzpicture}
\end{document}
```

## Iterative Models
Iterative models work by going step-by-step, simulating the behaviour of an object.
The advantage is that they can be used for when there are many variables e.g. air resistance increases as velocity increases.
The disadvantage is that they do not accurately model reality, as they work in discrete steps. The accuracy of an iterative model can be increased by reducing the time step.

## SUVAT
There are 4 **SUVAT** equations:
$$
\begin{split}
v &= u + at
\\ s &= ut + \frac{1}{2}at^2
\\ s &= \frac{1}{2}(u+v)t
\\ 2as &= v^2-u^2
\end{split}
$$
Where $u$ is initial velocity, $v$ is final velocity, $s$ is displacement, $t$ is time, and $a$ is acceleration (all given in the formula booklet).

#### Projectile motion
For **projectile motion**, the idea is to apply SUVAT separately for both the horizontal and vertical directions, and noting that the two times are equal; when an object reaches the ground vertically, it stops moving horizontally.

For projectile motion, the time to maximum height (where the vertical velocity is zero) is exactly half the total time of flight. Alternatively, the parabolic trajectory is symmetrical about the midpoint at maximum height.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]

  \coordinate[label=below:$A$](A) at (-2.5, -1.25);
  \coordinate[label=below:$B$](B) at (2.5, -1.25);
  \coordinate[label=below:$M$](M) at (0, -1.25);
  \draw[scale=0.5, domain=-5:5, smooth, variable=\x, black] plot ({\x}, {-0.1*\x*\x});
  \draw[scale=0.5, domain=-5:0, smooth, variable=\x, red] plot ({\x}, {0-2.5});
  \draw[scale=0.5, domain=0:5, smooth, variable=\x, black] plot ({\x}, {0-2.5});
  \draw[dotted, thick](0, 0) -- (0, -1.25);

\end{tikzpicture}
\end{document}
```

## Momentum
**Momentum** is a vector quantity. It is the product of mass ($m$) and velocity ($v$).
$$
p = mv
$$
For any interaction in a closed system, the principle of conservation of momentum holds: the total momentum before an interaction is equal to the total momentum after.

In **elastic** collisions, kinetic energy is conserved, whilst in **inelastic** collisions, kinetic energy is not conserved, and some kinetic energy is transferred to heat, sound, or deformation.

## Newton's Laws of Motion
Newton's laws of motion are:
- An object at rest will remain at rest, and an object in motion will remain in motion, unless acted on by an external force.
- $F = \frac{\Delta p}{\Delta t} = \frac{\Delta(mv)}{\Delta t} = m\frac{\Delta(v)}{\Delta t} = MA$
- For every action, there is an opposite and equal reaction. This is equivalent to the principle of conservation of momentum.

**Impulse**, $\Delta p$, is change in momentum. It has units of $\text{N}\,\text{s}$ (newton seconds), or $\text{kg}\,\text{m}\,\text{s}^{-1}$ (kilogram metres per second). By $F = \frac{\Delta p}{\Delta t}$, $\Delta P = F \Delta t$.

For a force-time graph, the area under the graph gives impulse.

## Work
**Work** is the result of applying a force over a distance (in the line of action of the force):
$$
W = F \Delta s = F s\cos \theta
$$
Where the $\cos\theta$ term corrects for distance not in the line of action of the force. 

**Energy** is the capacity to do work. For motion, there are two energy equations:
$$
E = mgh = \frac{1}{2}mv^2
$$
**Power** is the rate at which work is done, or the rate at which energy is transferred:
$$
P = \frac{\Delta E}{\Delta t} = \frac{Fs}{t} = Fv
$$
