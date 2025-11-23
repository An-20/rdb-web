#### Gas Laws
When describing an **ideal gas**, the following assumptions are made:
- **Gas particles take up negligible volume**
- **All collisions between particles and the walls of the container and each other are completely elastic**
- **There are negligible forces between particles except during collisions**
- All particles of a particular gas are identical
- The internal energy of the gas is entirely kinetic
- Newton's laws of motion apply
- Gravitational, electrostatic and Van de Waals forces can be ignored
- The motion of all molecules is random
- All molecules travel in straight lines
*The top three assumptions in bold are given explicitly in the specification.*

**Boyle's Law** states that for a constant temperature, the volume of a fixed mass of gas is inversely proportional to its pressure:
$$
pV = \text{constant}\quad p\propto\frac{1}{V}
$$
**Avogadro's Law** states that for a constant pressure and temperature, the volume of a gas is directly proportional to the number of moles:
$$
V \propto n
$$

**Temperature** is a measure of the average kinetic energy of the particles in a substance. Due to the random nature of collisions between particles in a gas, there is a distribution of speeds, and therefore kinetic energies of particles. The range of speeds are represented by the **Maxwell Boltzmann** distribution.

**Charles' Law** states that for a constant pressure, the volume of a fixed mass of gas is directly proportional to its absolute temperature:
$$
V\propto T
$$
For $T$ in Kelvin (K).

By combining these laws, we get:
$$PV \propto Tn \implies PV = nRT$$
Where $R$ is the **ideal gas constant**, with a value of $8.314\, \textrm{J}\,\textrm{mol}^{-1}\,\textrm{K}^{-1}$.

The **Boltzmann Constant** is similar to the gas constant, $R$, but only for one particle. It is equal to the gas constant divided by $N_a$, the Avogadro constant:
$$
k = \frac{R}{N_a} = 1.38\times10^{-23}\,\textrm{J}\,\textrm{K}^{-1}
$$
By combining $N = n N_a$ with $k = \frac{R}{N_a}$, we get: $nR = Nk$, so we can rewrite the ideal gas equation as:
$$
pV = NkT
$$

At a constant temperature, the distribution of speeds will remain the same, as well as the average speed. The **root mean square** speed is:
$$
c_{rms} = \sqrt{\frac{c_1^2 + c_2^2 + \cdots + c_N^2}{N}} = \sqrt{\bar{(c^2)}}
$$

$$
pV = \frac{1}{3}N\,m\,{c_{rms}}^2
$$

Temperature of a gas is proportional to the average kinetic energy of its particles:
$$
\begin{split}
\mathrm{Average\,KE} &= \frac{3}{2}kT \\
\mathrm{Total\,KE} &= \frac{3}{2}nRT
\end{split}
$$

For monatomic particles (and one dimension), a simple estimation is often used:
$$
E_k \approx kT
$$

#### Gas Law Derivation
Consider a particle of mass $m$ moving at velocity $v$ in a cubic box with side length $x$.
- Assume that the particle is moving only perpendicular to a given wall. In general, one third of the total kinetic energy is in each perpendicular direction[^1].
- When the particle collides with a wall, it applies an impulse of $2mv$. 
- For a given wall, this happens every $\frac{2x}{v}$ seconds, so there are $\frac{v}{2x}$ collisions with a given wall per second.
- The force exerted on this wall is equal to the rate of change of impulse, so $F = \frac{1}{3} \times 2mv \times \frac{v}{2x} = \frac{mv^2}{3x}$
- The pressure is equal to force per unit area, so $p=\frac{mv^2}{3x} \div x^2 = \frac{mv^2}{3x^3}$
- Rearranging, we find $px^3 = \frac{1}{3}mv^2$
- $x^3$ is just the volume, so $pV = \frac{1}{3}mv^2$ for a single particle
- Considering $N$ particles each with mean squared speed $\bar{c^2}$, we get $pV = \frac{1}{3}Nm\bar{c^2}$.

Equating $pV = \frac{1}{3}Nm\bar{c^2} = NkT$, we find:
- $\frac{1}{3}m\bar{c^2} = kT$ (cancelling $N$ from both sides)
- $\frac{2}{3}(\frac{1}{2}m\bar{c^2}) = kT$ (pulling out a factor of $\frac{1}{2}$ for KE)
- $\textrm{KE}=\frac{3}{2}kT$

#### Specific Heat Capacity
**Specific heat capacity** is a measure of the energy needed to raise the temperature of $1 \textrm{kg}$ of a substance by $1 \degree\textrm{C}$. The equation for SHC is:
$$
\Delta E = mc\Delta\theta
$$

#### Brownian Motion
Particles in a liquid or gas undergo **random motion** because fast free-moving molecules move around and collide with each other. The **mean free path** is the average distance a particle travels before colliding (the size of a 'step'). If a particles takes $N$ steps, on average its end point is $\sqrt{N}$ steps away from its starting point. 

#### Boltzmann Factor
For many physical processes, a certain amount of energy is needed for the process to take place. This is the **activation energy** E; for example, in chemistry, reagents are often heated so they have enough kinetic energy to react. Other physical processes requiring an activation energy are:
- Changes of state
- Thermionic emission, where electrons are emitted from a heated metal surface
- Ionisation, where electrons are removed from an atom
	- Conduction in semiconductors
- Viscous flow
- Nuclear fusion
*The first five of these processes are given explicitly in the specification.*

```tikz
\usepackage{tikz}
\usepackage{pgfplots}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[scale=1, >=latex]
    \pgfplotsset{width=14cm,compat=1.6}
    \begin{loglogaxis}[
            width=14cm,
            height=16cm,
            xmin=0.1, xmax=1e10,
            ymin=1e-4, ymax=1e6,
            axis y line*=left,
            xlabel={Temperature $T$ / K},
            ylabel={Energy / eV},
            ytick={1e-4,1e-3,1e-2,1e-1,1e0,1e1,1e2,1e3,1e4,1e5,1e6},
            yticklabels={$10^{-4}$,$10^{-3}$,$10^{-2}$,$10^{-1}$,$10^{0}$,$10^{1}$,$10^{2}$,$10^{3}$,$10^{4}$,$10^{5}$,$10^{6}$},
            xtick={1e-1,1e0,1e1,1e2,1e3,1e4,1e5,1e6,1e7,1e8,1e9,1e10},
            xticklabels={$10^{-1}$,$10^{0}$,$10^{1}$,$10^{2}$,$10^{3}$,$10^{4}$,$10^{5}$,$10^{6}$,$10^{7}$,$10^{8}$,$10^{9}$,$10^{10}$},
            grid=both,
            grid style={line width=.08pt, draw=gray!18},
            major grid style={line width=.16pt,draw=gray!28},
            minor tick num=9,
            xtick pos=left,
            tick align=outside,
            axis line style={->},
            font=\small
        ]

        % Nuclear fusion and fission energies: ~1e5 - 1e6 eV
        \addplot[fill=orange!20, draw=none, opacity=0.5] coordinates
            {(0.1,1e5) (1e10,1e5) (1e10,1e6) (0.1,1e6)} \closedcycle;
        \node[font=\small, text width=8cm] at (axis cs:5e2,3.2e5) {Nuclear fusion and fission};

        % Inner-shell ionization / plasma / X-rays: ~300 - 30000 eV
        \addplot[fill=green!20, draw=none, opacity=0.5] coordinates
            {(0.1,3e2) (1e10, 3e2) (1e10,3e4) (0.1,3e4)} \closedcycle;
        \node[font=\small, text width=8cm] at (axis cs:5e2,3.2e3) {Inner-shell ionization \\ / plasma};

        % Covalent / ionic / metallic bond, outer-shell ionization: ~1 - 30 eV
        \addplot[fill=cyan!20, draw=none, opacity=0.5] coordinates
            {(0.1,1) (1e10,1) (1e10,3e1) (0.1,3e1)} \closedcycle;
        \node[font=\small, text width=8cm] at (axis cs:5e2,1e1) {Outer-shell ionization};
        \node[font=\small, text width=8cm] at (axis cs:5e2,3) {Covalent, ionic, metallic \\bonds broken};

        % Hydrogen bonds: ~0.1 - 0.3 eV
        \addplot[fill=blue!20, draw=none, opacity=0.6] coordinates
            {(0.1,2e-1) (1e10,2e-1) (1e10,4.5e-1) (0.1,4.5e-1)} \closedcycle;
        \node[font=\small, text width=8cm] at (axis cs:5e2,3.5e-1) {Hydrogen bonds};

        % van der Waals: energy band ~ 0.01 - 0.1 eV
        \addplot[fill=purple!20, draw=none, opacity=0.65] coordinates
            {(0.1,1e-2) (1e10,1e-2) (1e10,1e-1) (0.1,1e-1)} \closedcycle;
        \node[font=\small, text width=8cm] at (axis cs:5e2,5.5e-2) {van der Waals\\ forces};

        % Diagonal band
        \addplot[fill=red!12, draw=none, opacity=0.8] coordinates
            {(1e-1, 2.59e-4) (1e-1, 1e-4) (1e0, 1e-4) (1e10,1e6) (3.8e8, 1e6) (1e-1, 2.59e-4)};

        % Boltzmann constant in eV/K
        \def\kB{8.617333262e-5}

        % kT at room temperature ~ 300 K (vertical dashed)
        \pgfmathsetmacro{\kTroom}{\kB * 293}
        \addplot [very thin, dashed, blue] coordinates {(293,1e-4) (293,1e6)};
        \node[anchor=east, font=\small, blue, right] at (axis cs:293,1.5e-4) {293 K};
        \node[anchor=east, font=\small, blue, right] at (axis cs:1e7,1.5e-2) {$E = k_B T,\,T=293 K$};

        % Horizontal line for k_B T at room temperature
        \draw[very thick, blue] (axis cs: 0.1, 0.0253) -- (axis cs:1e10,0.0253) node[right] {};

        % Thermal energy line E = k_B * T
        \draw[very thick, red] (axis cs: 1, 1e-4) -- (axis cs: 1e10,1e6) node[right] {};
        \node[font=\large,red, right] at (axis cs:1e5,8) {$E = k_\mathrm{B}T$};
        % lines for E = 15 kB T and E = 30 kB T
        \draw[thick, red, dashed] (axis cs: 1e-1, 1.29e-4) -- (axis cs: 7.7e8, 1e6) node[right] {};
        \draw[thick, red, dashed] (axis cs: 1e-1, 2.59e-4) -- (axis cs: 3.8e8, 1e6) node[right] {};
        \node[font=\small, red, right, text width=4cm] at (axis cs:2.7e2,1.5e2) {$E = 15\,k_\mathrm{B}T\,\textrm{and}$};
        \node[font=\small, red, right, text width=4cm] at (axis cs:2.7e2,8e1) {$E = 30\,k_\mathrm{B}T$};
    \end{loglogaxis}

    % Secondary right-hand y-axis for kJ/mol (conversion 1 eV = 96.485 kJ/mol)
    \begin{loglogaxis}[
            height=16cm,
            xmin=0.1, xmax=1e10,
            ymin=1e-4, ymax=1e6,
            axis y line*=right,
            axis x line=none,
            ytick={1.036e-4,1.036e-3,1.036e-2,1.036e-1,1.036e0,1.036e1,1.036e2,1.036e3,1.036e4,1.036e5},
            yticklabels={
                    $10^{-2}$,
                    $10^{-1}$,
                    $1$,
                    $10^{1}$,
                    $10^{2}$,
                    $10^{3}$,
                    $10^{4}$,
                    $10^{5}$,
                    $10^{6}$,
                    $10^{7}$
                },
            ylabel={Energy / kJ mol$^{-1}$},
            yticklabel style={font=\small},
            hide x axis,
            z buffer=sort,
            minor tick style={draw=none},
        ]
    \end{loglogaxis}

\end{tikzpicture}
\end{document}
```
>**Hope you like this diagram because we used up our entire yearly Tikz diagram budget on it.**

Many physical processes require energies between $15kT$ and $30kT$, for example water evaporation requires around $18kT$ at freezing.

The Boltzmann factor, $f$ is defined as:
$$
f = e^{-\frac{E}{kT}} = \exp\left(-\frac{E}{kT}\right)
$$

[^1]: **Footnote on kinetic energies in perpendicular directions**
	Kinetic energies in perpendicular directions add (by the Pythagorean theorem), so on average a third of the total kinetic energy is in any given direction.
