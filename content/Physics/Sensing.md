## Definitions
**Current** is defined as the rate of flow of charge.
$$
I = \frac{Q}{t}
$$

**Potential difference** is energy transferred per unit charge.
$$
V = \frac{E}{Q}
$$
Potential difference is the difference in energy per unit change from one point in a circuit to another. p.d. is measured in Volts ($\text{V}$) using a voltmeter. Conceptually, **p.d.** is the energy per unit charge transferred from electrical energy to other forms of energy, whilst **e.m.f** (electromotive force) is the energy per unit charge transferred into electrical energy from other forms of energy.

## Resistance
**Resistance** is opposition to the flow of charge. It is measured in Ohms ($\ohm$).
**Ohm's Law** states that:
$$
V = IR
​$$

**Power** is defined as energy over time:
$$
P = \frac{E}{t} = \frac{QV}{t} = IV = I^2R = \frac{V^2}{R}
$$

## Drift Velocity 
In a conductor carrying a current, the electrons will experience a force from negative to positive. This causes an average displacement over time, which causes **drift velocity**.
$$
I = nAve
$$
Where:
- $n$ is the charge carrier density (number of charge carriers per unit volume), in $\mathrm{m}^{-3}$
- $A$ is the cross-sectional area of the wire, in $\mathrm{m}^2$
- $v$ is the drift velocity, in $\mathrm{m}\,\mathrm{s}^{-1}$
- $e$ is the charge on each charge carrier, in $\mathrm{C}$.

## Conductance
**Conductance** is the amount of current that flows through a component for each volt of p.d. applied across it. It is the reciprocal of resistance, and is measured in **Siemens** ($\mathrm{S}$). 
#### Resistance and conductance rules
For components in parallel, the voltage across each component is the same:
$$
\begin{split}
G_1 &= \frac{I_1}{V_1},&&G_2 &&= \frac{I_2}{V_2},&&\cdots,\,\,\, G_n &&= \frac{I_n}{V_n} \\
I_1 &= V_1G_1,\,\,\,&& I_2 &&= V_2G_2,\,\,\,&&\cdots,\,\,\,I_n &&= V_nG_n \\
I_t &= V_1G_1 && &&+ V_2G_2 &&\cdots\,\,\,&&+ V_nG_n \\
I_t &= V(G_1 && &&+ G_2 &&\cdots\,\,\,&&+ G_n) \\
\end{split}
$$
Giving the general rule that **conductances in parallel sum**. As conductance is the reciprocal of resistance, this gives the $\frac{1}{R_t} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n}$ rule.

For components in series, the current through each component is the same:
$$
\begin{split}
G_1 &= \frac{I_1}{V_1},&&G_2 &&= \frac{I_2}{V_2},&&\cdots,\,\,\, G_n &&= \frac{I_n}{V_n} \\
V_1 &= \frac{I_1}{G_1},\,\,\,&& V_2 &&= \frac{I_2}{G_2},\,\,\,&&\cdots,\,\,\,V_n &&= \frac{I_n}{G_n} \\
V_T &= \frac{I_1}{G_1} &&&&+ \frac{I_2}{G_2}\,\,\,&&\cdots \,\,\,&&+ \frac{I_n}{G_n} \\
\end{split}
$$
Considering equal currents gives:
$$
V_T = I\left(\frac{1}{G_1} + \frac{1}{G_2}\,\,\,\cdots \,\,\, +\frac{1}{G_n}\right)
$$
By Ohm's law, this means the sum of reciprocals of conductances is equal to resistance. Thus, the conductance, which is the reciprocal of resistance, must be given by:
$$
\frac{1}{\frac{1}{G_1} + \frac{1}{G_2}\,\,\,\cdots \,\,\, +\frac{1}{G_n}}
$$
**Conductances in series act like resistances in parallel**. As conductance is the reciprocal of resistance, this gives the rule that resistances add in series.

## Resistivity and conductivity
**Resistivity** ($\rho$) is a property of a material that described the extent to which the material opposes the flow of electric current. The resistance of a piece of material depends on its resistivity, size and shape. The resistance $R$ of a wire with cross-sectional area $A$ and length $L$ made from a material with resistivity $\rho$ (in $\ohm\,\mathrm{m}$) is given by:
$$
R = \frac{\rho L}{A}
$$
**Conductivity** ($\sigma$) is a measure of a material's ability to conduct electricity. The unit of conductivity is $\mathrm{S}\,\mathrm{m}^{-1}$ (as conductivity is the reciprocal of resistivity). The conductance of a wire is given by:
$$
G = \frac{\sigma A}{L}
$$

## Internal Resistance
An ideal cell has no internal resistance, but a non-ideal cell can be modelled as an ideal cell and a resistor. The terminal difference of a cell is given by:
$$
V = \varepsilon - Ir
$$
Where:
- $V$ is the terminal potential difference, in $\mathrm{V}$
- $\varepsilon$ is the electromotive force, in $\mathrm{V}$
- $I$ is the current, in $\mathrm{A}$
- $r$ is the internal resistance of the cell, in $\ohm$.

## Kirchhoff's Laws
- **Kirchhoff's current law** (1st Law) states that the current flowing into a node must be equal to the current flowing out of it. This is a result of conservation of charge.
- **Kirchhoff's voltage law** (2nd Law) states that in any complete loop in a circuit, the directed sum of all voltages across components is zero, or alternatively the sum of e.m.f.s is equal to the sum of p.d.s. This is a result of conservation of charge and energy.

## Potential Dividers
In a **potential divider**, the ratio of voltages across each series component is equal to the ratio of resistances:
$$
\begin{split}
V_{\text{out}} &= \frac{R_2}{R_1 + R_2} \times V_{\text{in}} \\
\frac{V_1}{V_2} &= \frac{R_1}{R_2}
\end{split}
$$
