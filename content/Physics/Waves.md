## Definitions
- **Wavelength** is the distance between equivalent points on two consecutive waves e.g. peak to peak.
- **Amplitude** is the maximum displacement of a point on the wave from its undisturbed (equilibrium) position.
- **Frequency** is the number of complete waves passing a given point per second (in $\text{Hz}$).
- **Time period** is the time taken for a complete wave cycle to pass through a point. This is the reciprocal of frequency.
- **Phase** of a wave refers to the stage of the wave cycle. Two waves are in phase when they have $0\,\text{rad}$ phase difference. They are in antiphase when they have $\pi\,\text{rad}$ phase difference.
- **Coherence** is where waves have the same frequency and a constant phase difference.
- **Path difference** is the difference between the distance travelled by two waves when they meet. A path difference of $n\lambda$ produces waves meeting in phase, while a path difference of $(n + \frac{1}{2})\lambda$ produces waves meeting in antiphase.

## Standing waves
**Formation** of a standing wave involves:
- A **progressive wave** travelling through a medium
- The progressive wave **reflects** off a boundary e.g. the end of the medium
- The two progressive waves travelling in opposite directions **interfere** to produce a standing wave pattern
- Where waves meet in phase, **constructive interference** occurs, causing **antinodes** of maximum displacement to form
- Where waves meet in antiphase, **destructive interference** occurs, causing **nodes** of minimum displacement to form.

When standing waves form in tubes and strings, **antinodes** always form at open ends, and **nodes** always form at closed ends (or where a string is held down).

#### Practical
To find the speed of sound:
- Use a resonance tube partially submerged in water and a tuning fork (which produces a fixed frequency sound wave)
- Hold a tuning fork over the top and move the tube until resonance occurs.
- Measure the length for the first and second resonance frequencies.
- $\lambda = 2(L_2 - L_1)$
- Using $v = f\lambda$, the speed of sound can be calculated.

## Refraction
**Refraction** occurs when waves move between two media that have different wave speeds, causing the wave to change speed and bend. If the wave travels faster in the new medium, it bends away from the normal, else if it travels slower, it bends towards the normal.

Refraction can be explained by wavefronts, where the part of the wavefront that first enters the new medium experiences a change in speed first. As the wave must travel perpendicular to the wavefront, the wave must change direction.

The **refractive index** is the ratio of the speed of light in two media. The absolute refractive index is the ratio of speed of light in a vacuum to that of the material. The absolute refractive index is always $\ge$ 1.
$$\text{refractive index} = \frac{\text{speed in medium 1}}{\text{speed in medium 2}}$$

**Snell's Law** describes how waves refract when changing media.
$$n_1\sin\theta_i = n_2\sin\theta_r$$

## Diffraction
**Diffraction** is the spreading out of waves as they pass through an aperture with a width on the same order of magnitude as their wavelength.
#### Double slit diffraction
When **coherent** waves pass through two slits, they **diffract** and **interfere** with each other, producing a pattern of bright and dark fringes. 
- The coherent waves superpose.
- At places where the waves arrive in phase, constructive interference occurs, forming bright fringes. 
- At places where the waves arrive in antiphase, destructive interference occurs, forming dark fringes. 
This can also be explained using path difference instead of phase difference.

For constructive interference, $n\lambda = d \sin\theta$. This can be shown graphically:
```tikz
\begin{document}
\begin{tikzpicture}[font=\small]

\draw[ultra thick] (0, 2.5)  -- (0, 1.2);
\draw[ultra thick] (0, 0.6)  -- (0,-0.6);
\draw[ultra thick] (0,-1.2)  -- (0,-2.5);
\draw[|-|] (-0.6, 0.9) -- (-0.6,-0.9);
\node[anchor=east] at (-0.65, 0) {$d$};

\coordinate (S1) at (0,  0.9);
\coordinate (S2) at (0, -0.9);
\coordinate (P)  at (5,  1.8);
\draw (S1) -- (P);
\draw (S2) -- (P);

\draw[dashed] (0, 0.9) -- (0.75, -0.49);
\draw[thick, red] (0, -0.9) -- (0.75, -0.49) node[midway, right, below, red, yshift=-3.8] {$n\lambda$};

\node at (0.2, 0.17) {$\theta$};
\draw (0.574, -0.585) -- (0.479, -0.409) -- (0.655, -0.314);

\draw[dashed] (S2) -- (3.5, -0.9);
\draw[-, thick] (1.5,-0.9) arc[start angle=0, end angle={atan2(2.7,5)}, radius=1.5];
\node at (2.2, -0.4) {$\theta$};

\draw[ultra thick] (5,-2.5) -- (5, 2.5);
\filldraw (P) circle (2pt) node[anchor=west] {$P$};

\end{tikzpicture}
\end{document}
```
Thus, for the path difference to be $n\lambda$, by considering the small right-angled triangle, we get:
$$
\sin\theta = \frac{n\lambda}{d}
$$
Where $\theta$ is the angle to the maximum, $n$ is the order of the maximum, $\lambda$ is the wavelength, and $d$ is the slit distance.

##### Diffraction gratings
For a **diffraction grating** and a **distant screen**, the small angle approximation can be applied to find the fringe separation. By applying $\sin\theta \approx \theta \approx \tan\theta$, we get:
$$\frac{n\lambda}{d} = \frac{x}{L}$$

##### Huygen's wavelet model
*Possibly NIS.*
A wave of light is made up of many smaller wavelets. For diffraction, as the wave reaches a boundary at an angle, the wavelets which reach first, slow down first, causing the wave to bend towards the slower wavelets. This model can also describe why spherical wavefronts are formed at slits, causing diffraction (where the wave 'spreads out').
