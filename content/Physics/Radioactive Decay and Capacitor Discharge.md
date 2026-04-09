## Radioactive Decay
The **activity** $A$ (in Becquerel $\text{Bq}$) of a sample of a radioactive material is proportional to the amount of nuclei $N$, and the **decay constant** $\lambda$ (in $\text{s}^{-1}$). One Becquerel represents one decay per second. The decay constant represents the probability per unit time that any given nucleus will decay.
$$
A = \lambda N
$$
As each decay reduces the number of remaining unstable nuclei, the differential equation $\frac{\text{d} N}{\text{d} t} = -\lambda N$ is formed, which can be solved:
$$
\begin{split}
\frac{\text{d} N}{\text{d} t} &= -\lambda N
\\ \int \frac{\text{d} N}{N} &= \int -\lambda \text{d}t
\\ \ln|N| &= -\lambda t + C_1
\\ N &= e^{-\lambda t} \times e^{C_1}
\end{split}
$$
Considering the initial condition $t=0,\,N=N_0$ gives:
$$
N = N_0 e^{-\lambda t}
$$
$N$ is proportional to $A$, therefore:
$$
A = A_0e^{-\lambda t}
$$

The **half-life** of a radioactive sample can be defined as:
- The time taken for the number of radioactive particles present, $N$, to halve from an original value.
- The time taken for the activity, $A$, of a source to halve from an original value.

$N = N_0$ at time $t = 0$. After one half-life, $N = \frac{1}{2}N_0$ at $T = T_{1/2}$. 
$N = N_0 e^{-\lambda t}$ therefore becomes $\frac{1}{2}N_0 = N_0e^{-\lambda T_{1/2}}$.
Solving for $T_{1/2}$, we obtain:
$$
T_{1/2} = \frac{\ln2}{\lambda} 
$$

## Capacitors
A **capacitor** is a passive electronic device which stores energy. They consist of two or more conducting plates separated by an insulating material (the **dielectric**). Placing an insulator between the plates increases the charge stored on the plates. When connected to a battery:
- The plate connected to the positive side of the battery loses electrons to the battery.
- The other plate gains electrons from the negative side of the battery.

For a **charging** capacitor:
- The current decreases exponentially with time.
- The rate of flow of electrons is greatest at the start, and decreases to zero when the capacitor is fully charged.
- The potential difference of the capacitor and battery are equal.

When a capacitor is charged, the capacitor remains neutral. There is no net charge stored. However, the charge difference has created an electric field that is capable of moving (doing work on) any other charged particle that is placed between the capacitor plates. The capacitor stores electric potential energy.
 
The **capacitance** ($C$) of an object, measured in farads ($\text{F}$), is the amount of charge it is able to store per unit potential difference across it:
$$
C = \frac{Q}{V}
$$
Where $C$ is capacitance ($\text{F}$), $Q$ is charge ($\text{C}$), and $V$ is potential difference ($\text{V}$).

The energy stored in a capacitor is given by:
$$
E = \frac{1}{2}QV = \frac{1}{2}CV^2
$$

#### Dielectric breakdown
The capacitance of a set of charged parallel plates increases by the insertion of a dielectric material. The capacitance is inversely proportional to the electric field between the plates, and the presence of the dielectric reduces the electric field.

*NIS: The equation below is not on the specification.*
The **capacitance** of a capacitor is given by:
$$
C = \frac{\varepsilon_r\varepsilon_0A}{d}
$$
Where:
- $\varepsilon_r$ is the relative permittivity of the dielectric
- $\varepsilon_0$ is the permittivity of free space
- $A$ is the cross-sectional area
- $d$ is the distance between the plates

As the p.d increases, the stored energy increases. When the charge is large enough, the dielectric will break down and the charge will start to flow between the plates.

#### Capacitor Discharge
When a charged capacitor is allowed to **discharge** through a resistor:
- Current decreases with time, approaching zero when the capacitor is fully discharged.
- A graph of current against time shows exponential decay. Current reduces by the same factor in equal time intervals.
If a quantity decreases at a rate a which is proportional to the quantity remaining, then the decay is exponential.

The charge in one small time period $\Delta t$ decreases from $Q$ to $Q - \Delta Q$, and is proportional to the charge remaining:
$$
\frac{dQ}{dt} = -\frac{Q}{RC}
$$

For a **discharging** capacitor with circuit resistance $R$, capacitance $C$, and initial charge, p.d., and current $Q_0$, $V_0$, and $I_0$.
$$
\begin{split}
Q &= Q_0 e^{-\frac{t}{RC}} \\
V &= V_0e^{-\frac{t}{RC}} \\
I &= I_0e^{-\frac{t}{RC}}
\end{split}
$$
This gives the below graph:
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[xscale=1.2, yscale=3]
	\draw[->] (-0.2,0) -- (5.5,0) node[right] {$t$};
	\draw[->] (0,-0.1) -- (0,1.2) node[above] {$Q, V, I$};
	\node[left] at (0,1) {$Q_0, V_0, I_0$};
	
	\draw[thick, domain=0:5, samples=100, smooth] 
	plot (\x, {exp(-\x)});
	
	\def\yval{0.368} 
	\draw[dashed, gray] (1, 0) -- (1, \yval) -- (0, \yval);
	\draw (1, 0.05) -- (1, -0.05) node[below] {$\tau = RC$};
	\node[left, font=\small] at (0, \yval) {$0.37 y_0$};
	
	\node[anchor=west] at (2, 0.8) {$Q(t) = Q_0 e^{-t/RC}$};
	\node[anchor=west] at (2, 0.65) {$V(t) = V_0 e^{-t/RC}$};
	\node[anchor=west] at (2, 0.5) {$I(t) = I_0 e^{-t/RC}$};
\end{tikzpicture}
\end{document}
```

The product $RC = \tau$ is the **time constant**, and gives an indication of how long the capacitor takes to discharge. $\text{F} \times \ohm = \frac{\text{C}}{V} \times \frac{V}{A} = \frac{C}{A} = \frac{A\,s}{A} = s$, so $RC$ has unit of seconds. It is the time for the initial charge / voltage / current to fall to $\frac{1}{e} \approx 0.37$ of the initial value when discharging.

The **half-life** (the time taken for the current / voltage /current to fall to half its initial value) is given by:
$$
T_{1/2} = \ln(2)RC
$$

#### Capacitor Charging
For a **charging** capacitor with circuit resistance $R$, capacitance $C$, and final charge, p.d., and initial current $Q_0$, $V_0$, and $I_0$.
$$
\begin{split}
Q &= Q_0 (1-e^{-\frac{t}{RC}}) \\
V &= V_0 (1-e^{-\frac{t}{RC}}) \\
I &= I_0e^{-\frac{t}{RC}}
\end{split}
$$
This gives the below graphs:
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[xscale=1, yscale=3]
\begin{scope}[shift={(0,0)}]
	\draw[->] (-0.2,0) -- (5.5,0) node[right] {$t$};
	\draw[->] (0,-0.1) -- (0,1.2) node[above] {$Q, V$};
	\node[left] at (0,1) {$Q_0, V_0$};
	
	\draw[thick, domain=0:5, samples=100, smooth] 
	plot (\x, {1 - exp(-\x)});
	
	\def\yval{0.632} 
	\draw[dashed, gray] (1, 0) -- (1, \yval) -- (0, \yval);
	\draw (1, 0.05) -- (1, -0.05) node[below] {$\tau = RC$};
	\node[left, font=\small] at (0, \yval) {$0.63 y_0$};
	
	\node[anchor=west] at (2, 0.8) {$Q(t) = Q_0 e^{-t/RC}$};
	\node[anchor=west] at (2, 0.65) {$V(t) = V_0 e^{-t/RC}$};
\end{scope}

\begin{scope}[shift={(7.5,0)}]
	\draw[->] (-0.2,0) -- (5.5,0) node[right] {$t$};
	\draw[->] (0,-0.1) -- (0,1.2) node[above] {$I$};
	\node[left] at (0,1) {$I_0$};
	
	\draw[thick, domain=0:5, samples=100, smooth] 
	plot (\x, {exp(-\x)});
	
	\def\yval{0.368} 
	\draw[dashed, gray] (1, 0) -- (1, \yval) -- (0, \yval);
	\draw (1, 0.05) -- (1, -0.05) node[below] {$\tau = RC$};
	\node[left, font=\small] at (0, \yval) {$0.37 y_0$};

	\node[anchor=west] at (2, 0.5) {$I(t) = I_0 e^{-t/RC}$};
\end{scope}
\end{tikzpicture}
\end{document}
```

For charge and p.d., the **time constant** $RC$ now represents the time to charge to $1 - \frac{1}{e}$ of the final value, or 63%. The equation for current is the same for a charging or discharging capacitor.
 