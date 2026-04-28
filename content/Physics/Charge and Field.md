An **electric field** is a region in space where a charged particle experiences an electric force. Electric field lines show the direction that a small positive test charge would experience a force if it were placed in the field. The greater the density of field lines, the greater the force.

#### Force and field strength
The **force** due to the electric field, $F$ is given by:
$$
F = \frac{kQq}{r^2}\quad\textrm{where}\,k=\frac{1}{4\pi\varepsilon_0}
$$
The force has an inverse-square relationship with distance. The electric force is different from gravity in that it can be either attractive or repulsive depending on the charges of the particles.

The **field strength**, $E$, is the force per unit charge, and is given by:
$$
E = \frac{F}{q} = \frac{kQ}{r^2}
$$

In a **uniform electric field**, the field strength throughout the field is constant, similar to how the field strength in a uniform gravitational field is constant. The force on an object in a uniform field is also constant. In a uniform field:
$$
E = \frac{-\textrm{d}V}{\textrm{d}r} = \frac{V}{d}
$$

The electric force and field are both **vector quantities**, whereas energy and potential are both **scalar quantities**.

#### Energy and potential
The **electric potential energy**, $U$, is given by the negative integral of force with respect to distance:
$$
U = \frac{kQq}{r}
$$
Again, this is similar to $U = \frac{GMm}{r}$ for gravitational potential energy. The potential energy has an inverse proportional relationship with distance.

The **electric potential**, $V$, is the energy per unit charge, and is given by:
$$
V = \frac{U}{q} = \frac{kQ}{r}
$$
Electric potential $V$ and field strength $E$ are both properties of the field itself (as they are per unit charge), whereas potential energy $U$ and force $F$ act on a specific object within the field.

**Graphically**, the electric potential energy is the area under a force-distance graph between two points (by $W = Fs$) (possibly requiring a negative sign). Thus, the force is related to the gradient of a energy-distance graph.

Similarly, the potential is the area under a field strength against distance graph, and the field-strength is related to the gradient of a potential-distance graph.

The below graphs show the four different field values.
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[>=stealth]

\def\HSPACE{7}
\def\VSPACE{5}
\def\W{5.5}
\def\YMAX{2}
\def\YMIN{-2}

\tikzset{
    mainplot/.style={very thick, red!80!black, line cap=round},
    axisline/.style={->},
    eqnode/.style={anchor=north east}
}

\begin{scope}[shift={(0,0)}]
    \draw[axisline] (-0.25,0) -- (\W,0) node[right] {$r$};
    \draw[axisline] (0,\YMIN) -- (0,\YMAX) node[above] {$F_g$};
    
    \draw[mainplot, domain=0.77:5, samples=100] plot (\x, {1.2/(\x*\x)});
    \node[eqnode] at (\W, \YMAX) {$F = \frac{kQq}{r^2} = \frac{Qq}{4\pi\varepsilon_0 r^2}$};
\end{scope}

\begin{scope}[shift={(\HSPACE,0)}]
    \draw[axisline] (-0.25,0) -- (\W,0) node[right] {$r$};
    \draw[axisline] (0,\YMIN) -- (0,\YMAX) node[above] {$U$};
    
    \draw[mainplot, domain=0.5:5, samples=100] plot (\x, {1/\x});
    \node[eqnode] at (\W, \YMAX) {$U = \frac{kQq}{r} = \frac{Qq}{4\pi\varepsilon_0 r}$};
\end{scope}

\begin{scope}[shift={(0,-\VSPACE)}]
    \draw[axisline] (-0.25,0) -- (\W,0) node[right] {$r$};
    \draw[axisline] (0,\YMIN) -- (0,\YMAX) node[above] {$V$};
    
    \draw[mainplot, domain=0.77:5, samples=100] plot (\x, {1.2/(\x*\x)});
    \node[eqnode] at (\W, \YMAX) {$E = \frac{kQ}{r^2} = \frac{Q}{4\pi\varepsilon_0 r^2}$};
\end{scope}

\begin{scope}[shift={(\HSPACE,-\VSPACE)}]
    \draw[axisline] (-0.25,0) -- (\W,0) node[right] {$r$};
    \draw[axisline] (0,\YMIN) -- (0,\YMAX) node[above] {$V$};
    
    \draw[mainplot, domain=0.5:5, samples=100] plot (\x, {1/\x});
    \node[eqnode] at (\W, \YMAX) {$V = \frac{kQ}{r} = \frac{Q}{4\pi\varepsilon_0 r}$};
\end{scope}

\end{tikzpicture}
\end{document}
```

#### Equipotential surfaces
**Equipotential surfaces** are surfaces along which all points have the same potential. They are always perpendicular to the direction of field lines. In a uniform field, equipotential surfaces are equally spaced.

#### Force on a moving charge
Consider a particle moving with charge $q$ moving through a magnetic field $B$ at velocity $v$. The 'current' produced by this particle in a time $\Delta t$ is $\frac{\Delta q}{\delta T}$, and substituting into $F = BIL$ gives:
$$
F = BIL = B \left(\frac{\Delta q}{\Delta t}\right)L = Bq\left(\frac{\Delta L}{\Delta t}\right) = Bqv
$$
For a **charged particle moving in a magnetic field**, $F = Bqv$. The left-hand rule can be used to find the direction of the force (taking care that current in the left-hand rule is conventional current, i.e. the direction of flow of positive charge).

Equating this force with the centripetal force in circular motion, $F = \frac{mv^2}{r}$, can be used to find the radius of circular motion for a charged particle moving perpendicular to a uniform magnetic field:
$$
\begin{aligned}
\frac{mv^2}{r} &= Bqv \\\\
r &= \frac{mv}{Bq}
\end{aligned}
$$

#### Electron charge
The charge on the electron is discrete; all charged particles^[^1] have charge equal to some integer multiple of the elementary charge, $1.60\times10^{-19}\,\textrm{C}$.

This was first shown in **Millikan's oil drop experiment**. In the experiment:
- An atomiser creates a mist with small droplets of oil.
- The droplets are ionised by X-rays, causing the droplets to become charged. 
- A potential difference is applied across two metal plates, creating an electric field.
- The oil droplets are observed as they fall, and balancing forces allows for the calculation of the charge on the oil droplets.


**Footnotes**
[^1]: **Footnote on elementary charge**: Other than quarks (which don't exist by themselves)
