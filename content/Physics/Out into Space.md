#### Circular Motion
An object moving in a circle is constantly accelerating towards the centre due to a **centripetal force**, which acts at right angles to the motion of the object. For an object moving in a **horizontal circular** path of radius $r$ m, and at a constant angular velocity of $\omega\,\text{rad\,s}^{-1}$:
- The **linear speed** is given by $v = r\omega$
- The **acceleration towards the centre** is given by $a = v\omega = r\omega^2 = \frac{v^2}{r}$

```tikz
\usepackage{tikz}
\usepackage{amsmath}
\begin{document}

\begin{tikzpicture}[scale=2, >=latex]

  % Draw the circular path
  \draw[thick] (0,0) circle(1);

  % Label the center
  \fill (0,0) circle(0.5pt) node[below left] {Center};

  % Draw the object on the path
  \filldraw[black] (1,0) circle (1pt) node[below right] {Object};

  % Draw velocity vector (tangent)
  \draw[->, thick] (1,0) -- (1,0.5) node[right] {$v$};

  % Draw centripetal force vector (toward center)
  \draw[->, thick, red] (1,0) -- (0.5,0) node[above right] {$\vec{F}_c$};

  % Optional: show radius
  \draw[dashed] (0,0) -- (1,0) node[midway, below] {$r$};

\end{tikzpicture}

\end{document}

```

The **angular velocity** is the angle the object rotates through each second, in $\text{rad}\,\text{s}^{-1}$. Angular velocity is given by:
$$
\omega = 2\pi f = \frac{2\pi}{t}
$$

Applying $F = ma$, we get: $F = m\omega^2r = \frac{mv^2}{r} = mv\omega$.

#### Gravity
**Newton's Law of Gravitation** states that all particles with mass attract all other particles with a gravity force. The force is given by:
$$
F_{\text{grav}} = -\frac{GMm}{r^2}
$$
Where:
- $G$ is the gravitational constant, $6.67 \times 10^{-11}\, \text{N}\,\text{m}^2\,\text{kg}^{-2}$ 
- $M$ and $m$ are the masses of the two bodies
- $r$ is the distance between the two bodies
- The $-$ sign indicates this is an attractive force[^1].

A **gravitational field** is the region where a body's force of gravity is experience by other bodies. **Gravitational field strength**, $g$, is measured in $\text{N}\,\text{kg}^{-1}$, and is the force per unit mass felt by the object:
$$
g = \frac{F_\text{grav}}{m} = - \frac{GM}{r^2}
$$

**Gravitational potential energy**, $E_\text{grav}$, is measured in $J$, and is given by integrating the work done against gravity over a distance:
$$
E_\text{grav} = \int -F_\text{grav}\,\text{d}r = \int \frac{GMm}{r^2}\,\text{d}r = -\frac{GMm}{r}
$$

**Gravitational potential**, $V_\text{grav}$, is measured in $\text{J}\,\text{kg}^{-1}$, and is the energy per unit mass of the object:
$$
V_\text{grav} = \frac{E_\text{grav}}{m} = -\frac{GM}{r}
$$

###### Relationships
- $F = mg$, similarly $E_\text{grav} = mV_\text{grav}$.
- $F = -\frac{\text{d}E_\text{grav}}{\text{d}x}$: force is given by gradient of tangent to GPE-distance graph.
- $g = -\frac{\text{d}V_\text{grav}}{\text{d}x}$: field strength is given by gradient of tangent to potential-distance graph.
- $E_\text{grav} = \int F_\text{grav}\,\text{d}{r}$: energy is given by area under force-distance graph between two distances.
- $V_\text{grav} = \int g\,\text{d}{r}$: potential is given by area under field strength-distance graph between two distances.

###### Uniform gravitational fields
A **uniform gravitational field** is a region where the gravitational force is constant in both magnitude and direction at all points. This can be used to approximate a gravitational field near the surface of a large body e.g. Earth, where the field is almost constant over small distances.

For a uniform gravitational field $g$, the change in gravitational potential energy in raising an object with mass $m$ over a height $h$ is $E = mgh$.

###### Equipotentials
**Equipotentials** are regions in which field lines are parallel, meaning there is a constant gravitational potential. These are found in a uniform field. Equipotential lines have the same gravitational potential along their length, and run perpendicular to field lines.

Gravitational potential energy does not change when moving along equipotential lines lines, because by $E = Fs$, **no work is done when the force is perpendicular to the displacement**, resulting in **no work being done whilst moving along equipotential lines**.

#### Footnotes
[^1]: **Footnote on signs of forces and potential energies**
	Typically, it makes more sense to define the sign of a potential energy (for gravity potential energy is 0 at $\infty$ and thus sign is negative), then find the sign of the force using $F = -\frac{\text{d}U}{\text{d}x}$ if the potential energy $U$ is some function of position $x$ (work must be done against the force in the field, so there is a negative sign).
