## Work
**Propulsive forces** such as tension, thrust, or a driving force promote movement, whilst **resistive forces** such as friction, braking, and resistance resist movement. Work is done by a force when the object a force is applied to moves. Work is measured in Joules ($\text{J}$), with one Joule equal to one Newton applied over one metre.

For a force acting in the direction of motion:
$$
\text{work done} = \text{force} \times \text{distance}
$$

If a force $F$ is applied at an angle $\theta$ to the direction of motion, the component of the force that actually does work is $F \cos\theta$:
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text, decorations.markings, backgrounds}
\usetikzlibrary{positioning, angles, quotes}
\begin{document}

\begin{tikzpicture}[thick, background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\begin{scope}[very thick,decoration={
		markings,
		mark=at position 0.5 with {\arrow{>}}}
		] 
		\draw[postaction={decorate}] (0, 0) coordinate (o) -- (4, 0);
		\draw[postaction={decorate}] (0, 0) -- (4, 2);
	\end{scope}
	
	\coordinate[label=above left:\large$F$](a) at (2, 1);
	\coordinate[label=below:\large$F\cos\theta$](b) at (2, 0);
	
	\draw[very thick, dotted] (4, 0) -- (4, 2);
	\node[circle,fill=black,inner sep=0pt,minimum size=5pt] (o) at (0,0) {};

	\pic [draw, -, "$\theta$", angle eccentricity=1.5] {angle = b--o--a};
	\draw [very thick, ->] (1.5, -0.8) -- (2.5, -0.8);
	\node[label=above:$\mathrm{direction\,of\,motion}$] () at (2.0, -1.5) {};
	
\end{tikzpicture}
\end{document}
```
For a force acting at an angle $\theta$ to the direction of motion[^1]:
$$
\text{work done} = \text{force} \times \text{distance} \times \cos\theta
$$

## Kinetic energy
**Kinetic energy** is the energy an object has because it is moving. An object of mass $m$ (in $\text{kg}$) and speed $v$ (in $\text{ms}^{-1}$) has kinetic energy (in $\text{J}$) given by:
$$
E = \frac{1}{2}mv^2
$$

The **work–energy principle** states that the net work done by all the forces acting on a particle is equal to the change in kinetic energy of the particle:
$$
\text{work done} = \frac{1}{2}mv^{2}- \frac{1}{2}mu^2
$$

## Potential energy
**Gravitational potential energy (GPE)** is the energy an object has because of its position above ground level. An object of weight $mg$ (in $\text{N}$) and height above ground level $h$ (in $\text{m}$) has GPE (in $\text{J}$) given by:
$$
E=mgh
$$

The principle of the **conservation of mechanical energy** states that if there are no forces other than gravity doing work on an object during its motion, then the **mechanical energy** (sum of kinetic energy and GPE) is constant.
$$
\text{GPE} + \text{KE} = \frac{1}{2}mv^{2} + mgh = \text{constant}
$$

The work-energy principle and conservation of mechanical energy can be combined, by considering that any change in the mechanical energy of a system is the result of work done by external forces:
$$
\begin{split}
(\text{GPE}_{1} + \text{KE}_{1}) + \text{work done by external forces} &= (\text{GPE}_{2} + \text{KE}_{2}) \\
\text{change in mechanical energy of an object} &= \text{work done by external forces}
\end{split}
$$

## Power
**Power** is the rate at which work is done. Power is measured in watts ($\text{W}$), with one watt equal to one joule per second.
$$
\begin{split}
\text{average power} &= \frac{\text{work done}}{\text{time taken}} \\
\text{power} &= \text{tractive force} \times \text{speed}
\end{split}
$$


[^1]: **Footnote on work done by a force at an angle to the direction of motion**
	$\text{work done} = \text{force} \times \text{distance} \times \cos\theta = \boldsymbol{F} \cdot \boldsymbol{x}$ (by the dot product), but this is A-level content.
