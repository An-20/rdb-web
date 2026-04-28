#### Definitions
**Current** is defined as the rate of flow of charge. It is caused by the flow of charged particles.
$$
I = \frac{Q}{t}
$$

**Potential difference** is energy transferred per unit charge.
$$
V = \frac{E}{Q}
$$
Potential difference is the difference in energy per unit change from one point in a circuit to another. p.d. is measured in Volts ($\text{V}$) using a voltmeter. Conceptually, **p.d.** is the energy per unit charge transferred from electrical energy to other forms of energy, whilst **e.m.f** (electromotive force) is the energy per unit charge transferred into electrical energy from other forms of energy.

#### Resistance
**Resistance** is opposition to the flow of charge. It is measured in Ohms ($\Omega$). **Ohm's Law** states that (for Ohmic components):
$$
V = IR
​$$

**Power** is defined as energy over time. It is measured in Watts ($\text{W}$).
$$
P = \frac{E}{t} = \frac{QV}{t} = IV = I^2R = \frac{V^2}{R}
$$
The movement of electrons down a wire is obstructed by metal ions. Work is done as energy is transferred to these metal ions, causing the wire to heat up. This process, often called **Joule heating**, causes power to be dissipated in components.

#### Drift velocity 
In a conductor carrying a current, the electrons will experience a force from negative to positive. This causes an average displacement over time, which causes **drift velocity**.
$$
I = nAve
$$
Where:
- $n$ is the charge carrier density (number of charge carriers per unit volume), in $\mathrm{m}^{-3}$
- $A$ is the cross-sectional area of the wire, in $\mathrm{m}^2$
- $v$ is the drift velocity, in $\mathrm{m}\,\mathrm{s}^{-1}$
- $e$ is the charge on each charge carrier, in $\mathrm{C}$.

#### Conductance
**Conductance** is the amount of current that flows through a component for each volt of p.d. applied across it. It is the reciprocal of resistance, and is measured in **Siemens** ($\mathrm{S}$). Ohm's law with conductance is given by:
$$
I = VG
$$

##### Resistance and conductance rules
For components in parallel, the voltage across each component is the same:
$$
\begin{aligned}
G_1 &= \frac{I_1}{V_1},&&G_2 &&= \frac{I_2}{V_2},&&\cdots, G_n &&= \frac{I_n}{V_n} \\
I_1 &= V_1G_1,&& I_2 &&= V_2G_2,&&\cdots,I_n &&= V_nG_n \\
I_t &= V_1G_1 && &&+ V_2G_2 &&\cdots&&+ V_nG_n \\
I_t &= V(G_1 && &&+ G_2 &&\cdots&&+ G_n) \\
\end{aligned}
$$

Giving the general rule that **conductances in parallel sum**. As conductance is the reciprocal of resistance, this gives the $\frac{1}{R_t} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n}$ rule.

For components in series, the current through each component is the same:
$$
\begin{aligned}
G_1 &= \frac{I_1}{V_1},&&G_2 &&= \frac{I_2}{V_2},&&\cdots,\,\,\, G_n &&= \frac{I_n}{V_n} \\
V_1 &= \frac{I_1}{G_1},\,\,\,&& V_2 &&= \frac{I_2}{G_2},\,\,\,&&\cdots,\,\,\,V_n &&= \frac{I_n}{G_n} \\
V_T &= \frac{I_1}{G_1} &&&&+ \frac{I_2}{G_2}\,\,\,&&\cdots \,\,\,&&+ \frac{I_n}{G_n} \\
\end{aligned}
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

#### Resistivity and conductivity
**Resistivity** ($\rho$) is a property of a material that describes the extent to which the material opposes the flow of electric current. The resistance of a piece of material depends on its resistivity, size and shape. The resistance $R$ of a wire with cross-sectional area $A$ and length $L$ made from a material with resistivity $\rho$ (in $\ohm\,\mathrm{m}$) is given by:
$$
R = \frac{\rho L}{A}
$$
**Conductivity** ($\sigma$) is a measure of a material's ability to conduct electricity. The unit of conductivity is $\mathrm{S}\,\mathrm{m}^{-1}$ (as conductivity is the reciprocal of resistivity). The conductance of a wire is given by:
$$
G = \frac{\sigma A}{L}
$$
Conductivity and resistivity are both bulk properties of a material that do not depend on the dimensions of a sample.

#### Internal Resistance
An **ideal cell** has no internal resistance, but a non-ideal cell can be modelled as an ideal cell and a resistor in series. The terminal difference of a cell is given by:
$$
V = \varepsilon - Ir
$$
Where:
- $V$ is the terminal potential difference, in $\mathrm{V}$
- $\varepsilon$ is the electromotive force, in $\mathrm{V}$
- $I$ is the current, in $\mathrm{A}$
- $r$ is the internal resistance of the cell, in $\ohm$.

The **internal resistance** is the negative gradient of a V-I graph:
```tikz
\begin{document}
\begin{tikzpicture}[scale=0.8]
    \draw[->, thick] (-0.2,0) -- (5.5,0) node[right] {$I$ (A)};
    \draw[->, thick] (0,-0.2) -- (0,4) node[above] {$V$ (V)};

    \draw[thick] (0,3) -- (5,0);
    \node at (5.5, 1.1) {$V = \varepsilon - Ir$};

    \draw (0, 3) node[left, black] {$\varepsilon$};

    \draw[dashed] (1, 2.4) -- (3, 2.4);
    \draw[dashed] (3, 2.4) -- (3, 1.2);
    \node at (2, 2.6) {$\Delta I$};
    \node[right] at (3, 1.8) {$\Delta V$};
    \node at (3.9, 2.6) {$m = -r$};
    
\end{tikzpicture}
\end{document}
```

#### Kirchhoff's Laws
- **Kirchhoff's current law** (1st Law) states that the current flowing into a node must be equal to the current flowing out of it. This is a result of conservation of charge.
- **Kirchhoff's voltage law** (2nd Law) states that in any complete loop in a circuit, the directed sum of all voltages across components is zero, or alternatively the sum of e.m.f.s is equal to the sum of p.d.s. This is a result of conservation of charge and energy (*IS*: conservation of energy).

#### Potential Dividers
In a **potential divider**, the ratio of voltages across each series component is equal to the ratio of resistances:
$$
\begin{split}
V_{\text{out}} &= \frac{R_2}{R_1 + R_2} \times V_{\text{in}} \\
\frac{V_1}{V_2} &= \frac{R_1}{R_2}
\end{split}
$$

Potential dividers are used in **sensing circuits**. By placing an LDR or thermistor in series with a fixed resistor, the output voltage changes in proportion to the sensor's resistance. Different situations require voltage to either decrease or increase according to conditions, which can be achieved by measuring the voltage across different sides of the potential divider.

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{tikzpicture}[font=\small]

\begin{scope}
  \draw (0,4) to[battery2] (0,0) -- (2,0);
  \draw (0,4) -- (2,4);
  
  % Connection through LDR (Top)
  \draw (2,4) -- (2,3.75);
  \begin{scope}[shift={(2,3)}, rotate=90]
    \draw (0,0) circle (0.45);
    \draw (-0.75,0) -- (-0.45,0);
    \draw (-0.35,-0.15) rectangle (0.35,0.15);
    \draw (0.35,0) -- (0.75,0);
    \draw[->] (0.55, 0.75) -- (0.2, 0.4);
    \draw[->] (0.75, 0.55) -- (0.4, 0.2);
  \end{scope}
  \draw (2,2.25) -- (2,1.75);

  \begin{scope}[shift={(2,1)}, rotate=90]
    \draw (-0.75,0) -- (-0.35,0);
    \draw (-0.35,-0.15) rectangle (0.35,0.15);
    \draw (0.35,0) -- (0.75,0);
  \end{scope}
  \draw (2,0.25) -- (2,0);

  \draw (2,2) -- (3.5,2) to[rmeter, t=V] (3.5,0) -- (2,0);
  
  \node at (1.1, 3) {LDR};
  \node at (1.5, 1) {$R$};
\end{scope}

\begin{scope}[shift={(5.5,0)}]
  \draw (0,4) to[battery2] (0,0) -- (2,0);
  \draw (0,4) -- (2,4);

  % Connection through Fixed Resistor (Top)
  \draw (2,4) -- (2,3.75);
  \begin{scope}[shift={(2,3)}, rotate=90]
    \draw (-0.75,0) -- (-0.35,0);
    \draw (-0.35,-0.15) rectangle (0.35,0.15);
    \draw (0.35,0) -- (0.75,0);
  \end{scope}
  \draw (2,2.25) -- (2,1.75);

  \begin{scope}[shift={(2,1)}, rotate=90]
    \draw (0,0) circle (0.45);
    \draw (-0.75,0) -- (-0.45,0);
    \draw (-0.35,-0.15) rectangle (0.35,0.15);
    \draw (0.35,0) -- (0.75,0);
    \draw[->] (0.55, 0.75) -- (0.2, 0.4);
    \draw[->] (0.75, 0.55) -- (0.4, 0.2);
  \end{scope}
  \draw (2,0.25) -- (2,0);

  \draw (2,2) -- (3.5,2) to[rmeter, t=V] (3.5,0) -- (2,0);
  
  \node at (1.5, 3) {$R$};
  \node at (1.1, 1) {LDR};
\end{scope}

\end{tikzpicture}
\end{document}
```

In the left circuit, as light intensity increases, the resistance of the LDR decreases, causing the measured voltage to increase. In contrast, in the right circuit, as light intensity increases, the measured voltage decreases.

These sensing circuits require **calibration** so a voltage can be converted to a temperature or light intensity reading. This can be done by testing the output voltage for a range of input conditions and plotting a calibration curve (e.g. voltage against light intensity or temperature).

The **sensitivity** is the ratio of output (voltage) change to input change. It is the gradient of a calibration curve. For most circuits. For the above circuits, this would be measured in $\text{V}\,\degree\text{C}^{-1}$. 

#### Circuit components
*IS*: recognise standard circuit symbols.
The below circuit symbols are provided as a guide. It is not entirely clear which of these symbols are actually required.

```tikz
\usepackage{circuitikz}
\ctikzset{resistor=european}

\begin{document}
\begin{tikzpicture}[font=\small]

\node[anchor=west] at (-1,  0) {Cell};
\draw (1.0, 0) to[battery2] (2.5, 0);

\node[anchor=west] at (4.5, 0) {Battery};
\draw (6.5, 0) to[battery] (8.0, 0);

\node[anchor=west] at (-1, -1.5) {Resistor};
\draw (1.0, -1.5) to[R] (2.5, -1.5);

\node[anchor=west, align=center] at (4.5, -1.5) {Variable\\resistor};
\draw (6.5,-1.5) to[vR, mirror] (8.0,-1.5);

\node[anchor=west] at (-1, -3.0) {Thermistor};
\draw (1.0, -3.0) to[thermistor] (2.5, -3.0);

\node[anchor=west] at (4.5, -3.0) {LDR};
\begin{scope}[shift={(7.25, -3.0)}]
  \draw (0,0) circle (0.45);
  \draw (-0.75,0) -- (-0.45,0);
  \draw (-0.35,-0.15) rectangle (0.35,0.15);
  \draw (0.35,0) -- (0.75,0);
  \draw[->] (0.55, 0.75) -- (0.2, 0.4);
  \draw[->] (0.75, 0.55) -- (0.4, 0.2);
\end{scope}

\node[anchor=west] at (-1, -4.5) {LED};
\draw (1.0, -4.5) to[leDo] (2.5, -4.5);

\node[anchor=west] at (4.5, -4.5) {Lamp};
\draw (6.5, -4.5) to[lamp] (8.0, -4.5);

\node[anchor=west] at (-1, -6.0) {Fuse};
\draw (1.0, -6.0) to[fuse] (2.5, -6.0);

\node[anchor=west] at (4.5, -6.0) {Switch};
\draw (6.5, -6.0) to[nos] (8.0, -6.0);

\node[anchor=west] at (-1, -7.5) {Capacitor};
\draw (1.0, -7.5) to[C] (2.5, -7.5);

\node[anchor=west] at (4.5, -7.5) {Inductor};
\draw (6.5, -7.5) to[cute inductor] (8.0, -7.5);

\node[anchor=west] at (-1, -9.0) {Ammeter};
\begin{scope}[shift={(1.75,-9.0)}]
  \draw (-0.75,0) -- (-0.45,0);
  \draw (0,0) circle (0.45);
  \node at (0,0) {A};
  \draw (0.45,0) -- (0.75,0);
\end{scope}

\node[anchor=west] at (4.5, -9.0) {Voltmeter};
\begin{scope}[shift={(7.25,-9.0)}]
  \draw (-0.75,0) -- (-0.45,0);
  \draw (0,0) circle (0.45);
  \node at (0,0) {V};
  \draw (0.45,0) -- (0.75,0);
\end{scope}

\end{tikzpicture}
\end{document}
```

**Light dependent resistors** (LDRs) are typically semiconductor devices. The energy provided by incident photons gives electrons sufficient activation energy to become mobile charge carriers, increasing conductivity. Thus, LDR resistance decreases as light intensity increases.

**Thermistors** can be either positive temperature coefficient (PTC) or negative temperature coefficient (NTC). These are described below in the section on I-V graphs. As temperature increases, PTC thermistors have increasing resistance, whilst NTC thermistors have decreasing resistance. 

##### I-V, resistance, and conductance graphs
*IS*: graphs of current against potential difference and graphs of resistance or conductance against temperature for ohmic and non-ohmic devices or components.

Graphs of current against potential difference are below (same as GCSE). The filament lamp and diode are **non-ohmic conductors**, as their resistance varies.

```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[font=\small]

% OHMIC RESISTOR
\begin{scope}[shift={(0,0)}]
    \draw[->] (-1.5,0) -- (1.5,0) node[right] {$V$};
    \draw[->] (0,-1.5) -- (0,1.5) node[above] {$I$};
    \draw[thick] (-1.2,-1.2) -- (1.2,1.2);
    \node[below] at (0,-1.7) {Ohmic resistor};
\end{scope}

% FILAMENT LAMP
\begin{scope}[shift={(4,0)}]
    \draw[->] (-1.5,0) -- (1.5,0) node[right] {$V$};
    \draw[->] (0,-1.5) -- (0,1.5) node[above] {$I$};
    \draw[thick, smooth, samples=100, domain=-1.2:1.2] 
        plot (\x, {1.4*tanh(\x)});
    \node[below] at (0,-1.7) {Filament lamp};
\end{scope}

% DIODE
\begin{scope}[shift={(8,0)}]
    \draw[->] (-1.5,0) -- (1.5,0) node[right] {$V$};
    \draw[->] (0,-1.5) -- (0,1.5) node[above] {$I$};
    \draw[thick, smooth, samples=100] 
        (-1.3,0) -- (0.4,0) .. controls (0.7,0.05) and (0.8,0.2) .. (1.1,1.3);
    \node[below] at (0,-1.7) {Diode};
\end{scope}

\end{tikzpicture}
\end{document}
```

The below graphs show how resistance and conductance vary against temperature for positive temperature coefficient and negative temperature coefficient materials.
- Most conductors, including metals (and filament bulbs) have **increasing resistance** as temperature increases (positive temperature coefficient). This is because of **Joule heating**.

- Some semiconductors have **decreasing resistance** as temperature increases. This is because increasing temperatures free more charge carriers, causing the conductivity to increase. Semiconductor conduction is an example of a process with an **activation energy** (described [[Simple Models of Matter and Boltzmann Factor#Boltzmann Factor|here]], (*IS*)).

```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[font=\small]

\begin{scope}[shift={(0,0)}]
    \draw[->] (0,0) -- (3,0) node[right] {$T$};
    \draw[->] (0,0) -- (0,3) node[above] {$R, G$};
    
    \draw[thick, red] (0.2,0.2) -- (2.5,2.5) node[right] {$R$};
    
    \draw[thick, blue, smooth, domain=0.4:2.5] plot (\x, {1/\x + 0.3}) node[right] {$G$};
    
    \node[below, align=center] at (1.5,-0.5) {Metal \\ Positive Temp. Coeff. (PTC)};
\end{scope}

\begin{scope}[shift={(5,0)}]
    \draw[->] (0,0) -- (3,0) node[right] {$T$};
    \draw[->] (0,0) -- (0,3) node[above] {$R, G$};
    \draw[thick, red, smooth, domain=0.2:2.8] plot (\x, {2.5*exp(-\x)}) node[above right] {$R$};
    \draw[thick, blue, smooth, domain=0.1:2.5] plot (\x, {0.3 + 0.8*exp(\x-1.5)}) node[right] {$G$};
    \node[below, align=center] at (1.5,-0.5) {Semiconductor \\ Negative Temp. Coeff. (NTC)};
\end{scope}

\end{tikzpicture}
\end{document}
```

##### Electrical behaviour of materials
- Metals are conductive and carry large currents for a given voltage, as they have a high number of mobile charge carriers.
- Insulators have few (or no) mobile charge carriers, so they are not conductive.
- Semiconductors have a varying number of mobile charge carriers, as described above.
