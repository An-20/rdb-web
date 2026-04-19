## Mechanical behaviour
To change the shape of an object, two equal and opposite forces are required. **Tensile** forces stretch an object, causing extension, while **compressive** forces act towards the centre of an object.

In **elastic deformation**, a material temporarily changes shape, and regains its original shape after deforming forces are removed. In **plastic deformation**, a material permanently changes shape, and does not regain its original shape after deforming forces are removed.

#### Force-extension graphs
Below is a **force-extension graph** showing **Hooke's Law** ($F = kx$) up to the limit of proportionality.
```tikz
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}

\draw[->, thick] (0,0) -- (6,0) node[below] {Extension, $x$ (m)};
\draw[->, thick] (0,0) -- (0,5) node[left] {Force, $F$ (N)};
\node[below left] at (0,0) {0};

\draw[very thick] (0,0) -- (4,4);
\draw[very thick, dashed] (4,4) .. controls (4.5,4.3) and (5,4.5) .. (5.5,4.6);

\fill[opacity=0.2] (0,0) -- (4,4) -- (4,0) -- cycle;
\node[right, align=left] at (4, 2) {Area under graph = \\ Elastic potential energy \\ $E_e = \frac{1}{2} kx^2$};

\filldraw[black] (4,4) circle (2pt) node[above left] {$P$};
\draw[<-, thick] (4.1, 4.1) -- (5.2, 5.2);
\node[right, align=left] at (5.2, 5.2) {Limit of \\ proportionality};

\draw[thick] (1, 1) -- (2.5, 1) node[midway, below] {$\Delta x$};
\draw[thick] (2.5, 1) -- (2.5, 2.5) node[midway, right] {$\Delta F$};
\draw[thick] (1.1, 1.1) -- (2.4, 2.4);

\draw[<-, thick] (1.8, 1.8) -- (-0.8, 3);
\node[left, align=left] at (-0.8, 3) {Gradient $= \frac{\Delta F}{\Delta x} = k$ \\ Spring constant / \\ stiffness (N m$^{-1}$)};

\end{tikzpicture}
\end{document}
```

Note that for an extension-force graph (other way round), the spring constant is the reciprocal of gradient.

For a material up to the **limit of proportionality**, the extension of the material is **directly proportional** to the force applied. Past the limit of proportionality, the behaviour no longer conforms to Hooke's law. 

###### Work done
When a material is deformed elastically, work is done and stored as elastic potential energy. The energy is equal to the area under a force-extension graph. If plastic deformation occurs, work is done to achieve the deformation by rearranging atoms into new permanent positions.

The **hysteresis** loop in a loading-unloading force-extension graph has an area bound by two curves, which represents the work being done transferred to thermal energy, and not recovered through elastic potential energy. Materials such as rubber exhibit this behaviour (shown on the graph below).

```tikz
\usepackage{tikz}

\begin{document}
\begin{tikzpicture}

\draw[->, thick] (0,0) -- (6,0) node[below] {Extension, $x$ (m)};
\draw[->, thick] (0,0) -- (0,5) node[left] {Force, $F$ (N)};
\node[below left] at (0,0) {0};

% loading curve
\draw[very thick, red, smooth, samples=50] plot[domain=0:6.2] (\x, {4.5/(1+exp(-2*(\x-3)))});
\draw[->, red, thick] (2.4, 2) -- (2.9, 2.8) node[midway, left=2pt] {Loading};

% unloading curve
\draw[very thick, blue, smooth, samples=50] plot[domain=0:6.2] (\x, {4.5/(1+exp(-1.8*(\x-3.5))) - 4.5/(1+exp(1.8*3.5))});
\draw[->, blue, thick] (4.2, 2.8) -- (3.7, 2) node[midway, right=2pt] {Unloading};

% hysteresis loop
\fill[gray, opacity=0.2, samples=50, domain=0:6.2] 
    plot (\x, {4.5/(1+exp(-2*(\x-3)))}) -- 
    plot[domain=6.2:0] (\x, {4.5/(1+exp(-1.8*(\x-3.5))) - 5.5/(1+exp(1.8*3.5))}) -- cycle;

\draw[<-, thick] (3.2, 2.3) -- (4.0, 1.3);
\filldraw (6.2, 4.5) circle (1.5pt);
\node[right, align=left] at (4.0, 0.8) {Hysteresis loop \\ energy dissipated as heat};

\end{tikzpicture}
\end{document}
```

#### Stress-strain graphs
Below is a **stress-strain graph** for a typical ductile metal. The stress decreases as strain increases due to necking, where the deformation causes a reduction in cross sectional area (*NIS*).

```tikz
\usepackage{tikz}
\usepackage{amsmath}

\begin{document}
\begin{tikzpicture}[font=\small, scale=1.2]

\draw[->, thick] (0,0) -- (7.5,0) node[below, align=left] {Strain, $\varepsilon$\\ (dimensionless)};
\draw[->, thick] (0,0) -- (0,5.5) node[left] {Stress, $\sigma$ (Pa)};

\draw[very thick] (0,0) 
    -- (1.5,3)                         % linear to limit of prop
    .. controls (1.7,3.3) .. (1.9,3.4) % to yield strength
    .. controls (3.5,5.5) and (5,5.5) .. (6,5) % to UTS
    .. controls (6.5,4.7) .. (7,4);    % to fracture point

% limit of proportionality
\filldraw[black] (1.5,3) circle (1.5pt) node[left=2pt] {P};
\draw[<-] (1.55,3) -- (2,2.5) node[right] {Limit of proportionality};

% elastic limit / yield stress
\filldraw[black] (1.8,3.35) circle (1.5pt) node[above left] {E};
\draw[dashed] (0,3.35) -- (2.1,3.35);
\node[left] at (0,3.35) {Yield stress};
\draw[<-] (1.8,3.35) -- (2,3.2) node[right] {Elastic limit};

% ultimate tensile stress)
\filldraw[black] (4.8,5.28) circle (1.5pt);
\draw[dashed] (0,5.27) -- (4.8,5.27);
\node[left] at (0,5.25) {UTS};
\node[above] at (4.8,5.27) {UTS};

% fracture point
\filldraw[black] (7,4) circle (1.5pt) node[right, align=left] {Fracture \\ point};
\draw[dashed] (0,4) -- (7,4);
\node[left] at (0,4) {$\sigma_b$ (Fracture stress)};

% young's modulus
\draw[thick] (0.5,1) -- (1,1) node[midway, below] {$\Delta\varepsilon$};
\draw[thick] (1,1) -- (1,2) node[midway, right] {$\Delta\sigma$};
\draw[<-, thick] (0.7,1.5) -- (-0.5,2.5) node[left, align=left] {Gradient = \\ Young modulus, \\ $E$ (Pa)};

% area
\fill[black, opacity=0.2] (0,0) -- (1.5,3) .. controls (1.7,3.3) .. (1.9,3.4) 
    .. controls (3.5,5.5) and (5,5.5) .. (6,5) .. controls (6.5,4.7) .. (7,4) -- (7,0) -- cycle;

\node[left, align=left] at (7, 1) {Area under graph \\ = Strain energy per \\ unit volume / toughness \\ (J m$^{-3}$ or Pa)};

\draw[|-|] (0,-0.8) -- (1.8,-0.8) node[midway, below] {Elastic};
\draw[|-|] (1.8,-0.8) -- (7,-0.8) node[midway, below] {Plastic};

\end{tikzpicture}
\end{document}
```

Past the limit of proportionality, there is the **elastic limit**, a point beyond which the material will no longer return to its original shape once the force is removed. There will be plastic (permanent) deformation. The **yield stress** is the stress at the elastic limit[^1].

**Ultimate tensile stress** is the maximum stress experienced by a sample before breaking. **Fracture stress** is the stress experienced by a sample when the material actually breaks, at the fracture point.

##### Stress
**Stress** is the force applied per unit cross-sectional area. It is measured in pascal ($\text{Pa}$). Where $F$ is force, and $A$ is cross-sectional area:
$$\mathrm{Stress,\,\sigma} = \frac{F}{A}$$
##### Strain
**Strain** is the extension or compression of a material per unit of its original length. It has no units, and is sometimes written as a percentage. Where $x$ is change in length, and $L$ is original length:
$$\mathrm{Strain,\,\varepsilon} = \frac{x}{L}$$
##### Young modulus
The **Young modulus** of a material is the ratio of stress to strain. It is the gradient of a stress-strain graph, and is a measure of stiffness. It is measured in Pascal ($\text{Pa}$).
$$E = \frac{\mathrm{stress}}{\mathrm{strain}}=\frac{\sigma}{\epsilon} = \frac{FL}{ax}$$

#### Spring combinations
Springs in **parallel** share the load and have the same extension as a single spring with a combined spring constant:
$$k_p = k_1 + k_2$$
This can be derived by considering that the springs have a common extension:
$$F_p = F_1 + F_2 \implies k_px = k_1x + k_2x \implies k_p = k_1 + k_2$$


Springs in **series** have the same force. The extensions add, giving the same extension as a single spring with a combined spring constant:
$$\frac{1}{k_s} = \frac{1}{k_1} + \frac{1}{k_2}$$
This can be derived by considering that the springs have a common force:
$$
x_s = x_1 + x_2 \implies \frac{F}{k_s} = \frac{F}{k_1} + \frac{F}{k_1} \implies k_s = \frac{1}{k_1} + \frac{1}{k_2}
$$


#### Materials definitions
- **Stiff**: Small extension per unit force (high Young modulus).
- **Elastic**: Returns to unstretched form when stresses are removed.
- **Plastic**: Permanent deformation. 
- **Ductile**: Can be drawn into wires.
- **Hard**: Resists indentation on impact.
- **Brittle**: Undergoes little/no plastic deformation before fracture.
- **Tough**: Absorbs a lot of energy (deforms plastically) before fracture.
- **Strong**: Can withstand high stresses.

## Material structure
There are three general types of material structure:
- **Crystalline** structures have regular, ordered particles.
- **Amorphous** structures have random and disordered arrangements. This includes
- **Polycrystalline** structures have regular crystalline fragments (grains), but the grains are arranged in a disordered way.

Bonds in **ceramics** are **directional**, making it harder for them to deform plastically, while bonds in **metals** are **non-directional**.

#### Metals
Metals have a **crystalline** or **polycrystalline** structure. Metals behave elastically for small strains. Up to the elastic limit, the spacing between positive ions increases. When the tensile force is removed, the metal returns to its original shape.

Metals are **malleable** and **ductile**. There are mobile **dislocations** - missing ions in the regular lattice arrangement. These allow atoms to move along one at a time, causing the dislocation to move through the metal, causing ductility and plastic behaviour. As dislocations move, **slips** can occur, where some layers require less force to move.

In alloys, there are other metals, and these ions are different sizes, **pinning** dislocations, making slips more difficult.

#### Ceramics
Ceramics have a **lack of mobile dislocations**, causing them to be brittle, as slip does not occur. Additionally, their directional (typically covalent) bonds are very strong and require high stresses to overcome.

#### Polymers
**Polymers** are long chains of repeating monomers. Chains are **entangled** and when stresses are applied, they **rotate** and **unravel** around each other. **Crosslinks** between chains can reduce the rotation and unravelling of chains.

#### Amorphous materials
*Possibly NIS.*
**Amorphous** materials such as glass are brittle. This is because cracks can easily propagate. Two atoms are pulled apart at a crack, followed by the next two atoms. The atoms cannot move relative to each other - they are pinned in place, and the crack area is small, producing high stresses. This causes the crack to quickly grow.

#### Atomic diameter
**Rayleigh's oil drop experiment** compares the diameter of an oil drop to the diameter of the oil layer floating on water. The assumptions are:
- The oil spreads out as far as possible.
- The thickness of the layer is equal to the length of one oil molecule.

For an oil layer of radius $R$ and oil drop of radius $r$, the length of one oil molecule $h$ is given by:
$$\frac{4}{3}\pi r^3 = \pi R^2 h \implies h = \frac{4r^3}{3R^2}$$

Direct evidence of the size of particles and their spacing is also provided by STM (scanning tunnelling microscope) images.


[^1]: **Footnote on yield stress**
Technically not true (yield stress is at the yield point, but that isn't on the spec. Yield stress is when elastic deformation ends and plastic begins though.
