## Cosmic distances and velocities
Several units are used to measure cosmic distances:
- The **light year** (ly), the distance light travels in one year.
	- $1\,\textrm{ly} \approx 9.46\times 10^{15} \textrm {m} \quad \left(\approx 1\times 10^{16} \textrm {m in formula booklet}\right)$
- The **astronomical unit** (au), the average distance between Earth and the Sun.
- The **parsec** (pc), the distance from the Sun for an object to have a parallax angle of one arcsecond.

#### Radar and lidar
**Radar** (radio detection and ranging) works by timing the delay between sending a radio pulse and receiving the reflected pulse. By using the speed of light, the total round-trip distance can be calculated, and halved to find the one-way distance. This method uses the **relativistic principle of the invariance of the speed of light**. **Lidar** works in a similar way, but using light waves made by lasers instead of radio waves.

#### Parallax
*NIS: Parallax is never explicitly mentioned in the specification.*
**Parallax** is the shift in an object's position when it is viewed from different locations. This causes nearby objects to appear to shift more (move faster) than distant objects. The **baseline** is the known distance (either 1 or 2 au). The **parallax angle** is the apparent angle that the near star has moved through, often measured in arcseconds.

A circle is divided into 360 **degrees** (360$\degree$), each of which is divided into 60 **arcminutes** (60$'$), each of which is divided into 60 **arcseconds** (60$''$). Thus, an arcsecond represents $\frac{1}{360 \times 60 \times 60} = \frac{1}{1296000}$ of a complete rotation.

```tikz
\usepackage{tikz}
\usetikzlibrary{arrows.meta, decorations.pathreplacing, calc}

\begin{document}
\begin{tikzpicture}[]

% coordinates
\coordinate (Sun) at (0,0);
\coordinate (EarthTop) at (0,2);
\coordinate (EarthBot) at (0,-2);
\coordinate (NearStar) at (5.5,0);
\coordinate (FarFromTop) at ({10 - 5 * cos(30) + 5*cos(asin(1.8/5))}, -1.8);
\coordinate (FarFromBot) at ({10 - 5 * cos(30) + 5*cos(asin(1.8/5))}, 1.8);

% earth's orbit and baseline
\draw[thick] (Sun) ellipse [x radius=0.6, y radius=2];
\draw[thin] (0, -2) -- (0, 2);

% sun
\filldraw[yellow!80!orange] (Sun) circle (0.13);
\draw[thin] (Sun) circle (0.13);

% sightlines (before earth so lines are under)
\draw[thin] (EarthTop) -- (FarFromTop);
\draw[thin] (Sun) -- ({10 - 5 * cos(30) + 5}, 0);

% earth positions
\filldraw[blue!70!black] (EarthTop) circle (0.11);
\filldraw[blue!70!black] (EarthBot) circle (0.11);

% 1 au
\draw[thick] (-0.85, 0) -- (-0.85, -2);
\draw[thick] (-0.98, 0) -- (-0.72, 0);
\draw[thick] (-0.98, -2) -- (-0.72, -2);
\node[left] at (-1, -1) {1 au};

% earth's motion label
\node[above=2pt, align=center] at (0, 2.4) {Earth's motion\\around Sun};

% near star
\filldraw[magenta] (NearStar) circle (0.13);
\node[above=30pt] at (NearStar) {Near star};

% distant stars
\draw[thick] (10, -2.5) arc[start angle=-30, end angle=30, radius=5];
% black dots along the arc
\foreach \angle in {-24, -18, -12, -6, 0, 6, 12, 18, 24} {
    \filldraw[black] ({10 - 5 * cos(30) + 5*cos(\angle)}, {5*sin(\angle)}) circle (0.07);
}

% apparent positions
\filldraw[magenta!40] (FarFromTop) circle (0.13);
\filldraw[magenta!40] (FarFromBot) circle (0.13);

% apparent parallax motion arrow
\def\distantArcXRight{10 - 5 * cos(30) + 5};
\draw[magenta, thick] ({\distantArcXRight + 0.6}, 1.8) -- ({\distantArcXRight + 0.6}, -1.8);
\draw[magenta, thick] ({\distantArcXRight + 0.2}, 1.8) -- ({\distantArcXRight + 0.8}, 1.8);
\draw[magenta, thick] ({\distantArcXRight + 0.2}, -1.8) -- ({\distantArcXRight + 0.8}, -1.8);
\node[magenta, align=left] at ({\distantArcXRight + 2.4}, 0) {Apparent parallax\\motion of near star};

% distant stars label
\node at ({\distantArcXRight-0.5}, 3) {Distant stars};

% parallax angle p
\pgfmathsetmacro{\pAngle}{atan(2/5.5)}
\draw[thin] ($(NearStar) + (1.2, 0)$) arc[start angle=0, end angle=-\pAngle, radius=1.2];
\node[font=\small] at (6.4, -0.2) {$\theta$};

% parallax angle label
\node[magenta, align=left] at (7.8, -2.5) 
    {Parallax angle $\theta$\\= 1 arc second};
\draw[->] (7.5, -2.1) -- ($(NearStar) + (1.0, -0.45)$);

% 1 parsec
\draw[thick] (0, -3.5) -- (5.5, -3.5);
\draw[thick] (0, -3.25) -- (0, -3.75);
\draw[thick] (5.5, -3.25) -- (5.5, -3.75);
\node[below=2pt] at (2.75, -3.75) {1 parsec};

\end{tikzpicture}
\end{document}
```

#### Standard candles
*NIS: Standard candles are never explicitly mentioned in the specification.*
Some stars, **Cepheid variables**, have a variation in brightness that depends on their absolute brightness. The longer the period of the variation in brightness, the brighter the star. By comparing the absolute brightness of the star with the apparent brightness, the distance to the star can be calculated using the inverse square law.

#### Doppler shifts
**Doppler shifts** occur when an observer moves relative to the emitter of a wave. Consider a wave with wavelength $\lambda$, wave speed $c$, and time period $T$, emitted at relative speed $v$ to an observer:
$$
\lambda = cT
$$
In the time between two peaks, the source moves a distance $vT$ away from the observer:
$$
\Delta \lambda = vT
$$
By considering the increase in wavelength:
$$
\frac{\Delta\lambda}{\lambda} =\frac{vT}{cT} = \frac{v}{c}
$$
The equation $\frac{\Delta\lambda}{\lambda} = \frac{v}{c}$  holds for non-relativistic speeds (speeds much lower than the speed of light).

The **Doppler effect** can be used to determine whether distant galaxies are moving towards or away from us. Atoms in distant stars absorb and emit light with specific wavelengths, which produces **absorption or emission spectra**. The wavelength of these spectra changes according to the Doppler effect:
- For a distant galaxy moving away from us, the relative speed $v \gt 0$, so by $\frac{\Delta\lambda}{\lambda} = \frac{v}{c}$ there will be an increase in wavelength. This is **redshift**, where receding stars have spectra shifted towards the red (longer wavelength) end of the spectrum.

- Similarly, for a distant galaxy moving towards us, the relative speed $v \lt 0$, so by $\frac{\Delta\lambda}{\lambda} = \frac{v}{c}$ there will be an decrease in wavelength. This is **blueshift**, where receding stars have spectra shifted towards the blue (shorter wavelength) end of the spectrum.

## The Big Bang model
#### Hubble's Law
Hubble found that the further away a galaxy was, the greater the speed at which it was receding:
$$
v = H_o r
$$
Where $v$ is the recession velocity, $H_0$ is the Hubble constant, and $r$ is the distance to the galaxy. $H_0$ has units of $\textrm{km}\,\textrm{s}^{-1}\,\textrm{mpc}^{-1}$ (kilometres per second per megaparsec).

**Hubble's Law** suggests that the Universe expanded from being smaller in the past to its current state. The age of the Universe can be estimated using the Hubble constant:
- If $v = H_0 r$, then the time to travel $r$ at constant speed $v$ would be $\frac{r}{v} = \frac{1}{H_0}$.
- Thus, the age of the Universe is approximately $\frac{1}{H_0}$. 

#### Cosmological redshift
**Cosmological redshift** explains the very large redshifts observed in distant galaxies. $z$ is the redshift, where $z = \frac{\Delta\lambda}{\lambda}$. In astronomy, redshifts of up to $z\approx14$ have been observed; the non-relativistic Doppler equation would imply that these galaxies are moving at $v \approx 14c$, which is clearly not possible.

Cosmological redshift is the redshift caused by the expansion of the Universe. As light travels through the expanding Universe, the wavelength of the light is stretched. 

```tikz
\begin{document}
\begin{tikzpicture}[
    galaxy/.style={circle, fill=black, inner sep=2pt},
    text_style/.style={font=\small}
]

% --- TOP SECTION ---
\node[text_style, anchor=west, align=left] at (-0.5, 9.5) {Light emitted at A travels towards B.};
\draw[blue, thick] plot[domain=1:4, samples=50] (\x, {8.5 + 0.3*sin(deg((\x-1)*10))});

\node[galaxy] at (1, 8.5) {};
\node[galaxy] at (6, 8.5) {};
\node at (1, 8.1) {A};
\node at (6, 8.1) {B};
\draw[dotted] (1, 8.5) -- (6, 8.5);

\draw (1, 7.65) -- (1, 7.95);
\draw (6, 7.65) -- (6, 7.95);
\draw (1, 7.8) -- (6, 7.8) node[midway, below] {$x_{\tiny\textrm{emitted}}$};

\node[text_style] at (2.5, 9.1) {$\lambda_{\tiny\textrm{emitted}}$};

% --- MIDDLE SECTION ---
\node[text_style, anchor=west, align=left] at (-0.5, 7) {As the light travels, the Universe expands.};
\draw[green, thick] plot[domain=2:6, samples=50] (\x, {6 + 0.3*sin(deg((\x-2)*5))});

\node[galaxy] at (0.5, 6) {};
\node[galaxy] at (7.5, 6) {};
\node at (0.5, 5.6) {A};
\node at (7.5, 5.6) {B};
\draw[dotted] (0.5, 6) -- (7.5, 6);


% --- BOTTOM SECTION ---
\node[text_style, anchor=west, align=left] at (-0.5, 4.5) {Light observed at B has an increased wavelength.};
\draw[red, thick] plot[domain=4:9, samples=50] (\x, {3.5 + 0.3*sin(deg((\x-3.67)*3))});

\node[galaxy] at (0, 3.5) {};
\node[galaxy] at (9, 3.5) {};
\node at (0, 3.1) {A};
\node at (9, 3.1) {B};
\draw[dotted] (0, 3.5) -- (9, 3.5);

\draw (0, 2.65) -- (0, 2.95);
\draw (9, 2.65) -- (9, 2.95);
\draw (0, 2.8) -- (9, 2.8) node[midway, below] {$x_{\tiny\textrm{observed}}$};

\node[text_style] at (6.5, 4.1) {$\lambda_{\tiny\textrm{observed}}$};

\end{tikzpicture}
\end{document}
```

For a wave with wavelength $\lambda$ and a distance $x$:
$$
\begin{split}
&\frac{x_{\tiny\textrm{observed}}}{x_{\tiny\textrm{emitted}}} = \frac{\lambda_{\tiny\textrm{observed}}}{\lambda_{\tiny\textrm{emitted}}}

\\\\\implies &\frac{x_{\tiny\textrm{observed}}}{x_{\tiny\textrm{emitted}}} = \frac{\lambda_{\tiny\textrm{emitted}} + \Delta\lambda}{\lambda_{\tiny\textrm{emitted}}}

\\\\\implies &\frac{x_{\tiny\textrm{observed}}}{x_{\tiny\textrm{emitted}}} = 1 + \frac{\Delta\lambda}{\lambda_{\tiny\textrm{emitted}}}

\\\\\implies &\frac{x_{\tiny\textrm{observed}}}{x_{\tiny\textrm{emitted}}} = 1 + z
\end{split}
$$
Thus for a red-shift of $z$, space has stretched by a factor of $1 + z$. Thus, when distant objects with $z=10$ are observed, we are looking at when the Universe was around one-eleventh the current size.

#### Cosmic microwave background radiation
The **cosmic microwave background** is leftover electromagnetic radiation from the Big Bang that has experienced redshift. It was first produced when the Universe was cool enough for atoms to form, emitting photons. These photons initially had a wavelength of around $1 \,\micro\textrm{m}$, but have since been redshifted to around $1 \,\textrm{mm}$, giving $z\approx1000$. 

This provides evidence for the **hot Big Bang model**; it shows that the Universe began in a hot, dense state, and has since expanded and cooled.

## Special relativity
**Special relativity** is a theory describing the relationship between space and time. Special relativity is based on two postulates:
- Physical laws are the same for all observers in inertial frames of reference.
- The speed of light, $c$, is a universal constant for all observers, regardless of the motion of the observer.

#### Space-time diagrams
**Space-time diagrams** show objects moving through space and time:
- Time is shown on the $y$-axis.
- Distance is shown on the $x$-axis, in units of $\frac{x}{c}$ (light-seconds). Only one spatial dimension is shown.
- The diagram is drawn from the point of view of an observer that moves up the time axis.
- The **worldline** of an object represents its path through time and space.
	- A light pulse travels at 1 light-second per second, so its worldline is at $45\degree$ across the diagram.
	- An object moving relative to the observer moves along a sloping worldline. The steeper the slope, the faster the object is moving.

```tikz
\usepackage{amsmath, amssymb }
\usetikzlibrary{arrows.meta, math}

\begin{document}
\begin{tikzpicture}[scale=0.8]

% --- LEFT DIAGRAM ---
\begin{scope}
    % axes
    \draw[lightgray!80, thin] (0,0) grid (6,10);
    \draw[->, thick] (0,0) -- (6.5,0) node[below=12pt] {distance $\left(\frac{x}{c}\right)$};
    \draw[->, thick] (0,0) -- (0,10.5) node[above left] {time $t$ ($s$)};
        \foreach \y in {0,2,4,6,8,10} {
        \draw (0.1, \y) -- (-0.1, \y) node[left] {\y};
    }
    \foreach \x in {2,4,6} {
        \draw (\x, 0.1) -- (\x, -0.1) node[below] {\x};
    }

    % observer worldline
    \draw[->, ultra thick, blue] (0,0) -- (0,10) node[left, align=right, xshift=3.3cm, yshift=-8.8cm] {$\blacksquare$ \normalcolor Observer \normalcolor worldline};
    
    % object worldline
    \draw[->, ultra thick,red] (4,0) -- (4,10) node[right, pos=0.2, align=left, xshift=2pt, yshift=3pt] {$\blacksquare$ \normalcolor Vertical \\ \normalcolor worldline of \\ \normalcolor object not\\ \normalcolor moving relative\\ \normalcolor to observer};
    
    % radar pulse
    \draw[orange, ultra thick] (0,2) -- (4,6) -- (0,10);
    \node[orange, rotate=45, anchor=south] at (2,4) {pulse out};
    \node[orange, rotate=-45, anchor=south] at (2,8) {pulse back};
    \node[orange, align=center] at (2, 2) {Radar pulse\\out and back};
    \draw[<->] (0,6) -- (4,6) node[midway, fill=white, inner sep=1pt] {4 light-seconds};
    \draw[<->] (-0.8, 2) -- (-0.8, 6) node[midway, left] {4s out};
    \draw[<->] (-0.8, 6) -- (-0.8, 10) node[midway, left] {4s back};
\end{scope}

% --- RIGHT DIAGRAM ---
\begin{scope}[xshift=10cm]
    % axes
    \draw[lightgray!80, thin] (0,0) grid (6,10);
    \draw[->, thick] (0,0) -- (6.5,0) node[below=12pt] {distance $\left(\frac{x}{c}\right)$};
    \draw[->, thick] (0,0) -- (0,10.5) node[above left] {time $t$ ($s$)};
        \foreach \y in {0,2,4,6,8,10} {
        \draw (0.1, \y) -- (-0.1, \y) node[left] {\y};
    }
    \foreach \x in {2,4,6} {
        \draw (\x, 0.1) -- (\x, -0.1) node[below] {\x};
    }

    % observer worldline
    \draw[->, ultra thick, blue] (0,0) -- (0,10);
    
    % object worldline
    \draw[->, ultra thick, red] (0.5,0) -- (5.5,10) node[right, pos=0.3, align=left, yshift=-1.0cm] {$\blacksquare$ \normalcolor Sloping worldline\\ \normalcolor of object moving\\ \normalcolor relative to observer};
    
    % radar pulse
    \draw[orange, ultra thick] (0,2) -- (3,5) -- (0,8);
    \node[orange, rotate=45, anchor=south, font=\small] at (1.5,3.5) {pulse out};
    \node[orange, rotate=-45, anchor=south, font=\small] at (1.5,6.5) {pulse back};
    \draw[<->] (0,5) -- (3,5) node[midway, fill=white, inner sep=1pt, align=left] {3 light-\\seconds};
    \draw[<->] (-0.8, 2) -- (-0.8, 5) node[midway, left] {3s out};
    \draw[<->] (-0.8, 5) -- (-0.8, 8) node[midway, left] {3s back};
\end{scope}

\end{tikzpicture}
\end{document}

```


#### The relativistic factor
In particle accelerators or cosmic rays, particles travel at a very high speed and experience **relativistic effects**. The **rest energy** of a particle is given by:
$$
E_\textrm{rest} = mc^2
$$
Where $m$ is rest mass, and $c$ is the speed of light.

The **total energy** is given by $E_\textrm{total}=\gamma E_\textrm{rest}=E_\textrm{rest} + E_\textrm{kinetic}$, where $\gamma$ is the relativistic or **Lorentz factor**, defined as:
$$
\gamma = \frac{1}{\sqrt{1-\frac{v^2}{c^2}}}
$$

A graph of total energy, $E$, against velocity, $v$, shows how as the total energy tends to infinity, the speed approaches $c$. Thus, no objects can reach the speed of light, as this would require infinite energy. A graph of $\gamma$ has the same shape.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=1]

  \begin{scope}[shift={(0,0)}]
	\draw[->] (-0.5,0) -- (6,0) node[right] {$v$};
	\draw[->] (0,-0.5) -- (0,3) node[above] {$E$};
	\draw[dashed] (5.9,0) -- (5.9,3.6);
	\draw[dashed] (0, 1) -- (5.9,1);
	\draw[thick,smooth,samples=100,domain=0:5.7]
	    plot(\x,{1/(sqrt(1 - (\x)^2/36)});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
	\node[align=left] at (2.8, -0.4) {Value of $E$ for varying values of $v$};
	\node[align=left] at (-0.5, 1) {$E_\textrm{rest}$};
	\node[align=left] at (5.9, -0.3) {$c$};
  \end{scope}
\end{tikzpicture}
\end{document}
```

The following formulae are all *given in the formula booklet*:
$$
\begin{split}
\textrm{mass-energy relationship:}\quad &E_\textrm{rest} = mc^2
\\ \textrm{relativistic factor:}\quad &\gamma = \frac{1}{\sqrt{1-\frac{v^2}{c^2}}}
\\ \textrm{relativistic energy:}\quad &E = \gamma\,E_\textrm{rest}
\end{split}
$$

#### Time dilation and length contraction
*IS: Time dilation is explicitly mentioned in the specification. The derivation, however, is very likely not required.*
For an observer, let **wristwatch time** $\tau$ be the time recorded by a clock travelling with that observer.

Consider a light clock - a pair of mirrors with a pulse of light bouncing back and forth. A thought experiment can be carried out to explain where length contraction and time dilation come from.

```tikz
\usepackage{amsmath}
\usetikzlibrary{arrows.meta}

\begin{document}
\begin{tikzpicture}

\tikzset{
	mirror/.style={draw=none, top color=gray!90, bottom color=gray!30, middle color=white}
}

\tikzset{
	unusedMirror/.style={draw=none, top color=gray!90, bottom color=gray!30, opacity=0.3}
}

% --- LEFT DIAGRAM ---
\begin{scope}
	\node[anchor=west] at (-2.5, 4.0) {\textbf{Observer moving with the clock}};

	\foreach \y in {0, 3} {
		\fill[mirror] (-0.7, \y) rectangle (+0.7, \y+0.2);
	}

	\draw[ultra thick, orange, -{Stealth[scale=1.2]}] (0.15, 0.2) -- (0.15, 3);
	\draw[ultra thick, orange, -{Stealth[scale=1.2]}] (-0.15, 3) -- (-0.15, 0.2);
	\node[anchor=west] at (0.3, 1.6) {$d = c\tau$};
\end{scope}


% --- RIGHT DIAGRAM ---
\begin{scope}[shift={(8,0)}]
	\node[anchor=west] at (-3.5, 4.0) {\textbf{Clock travelling past observer at speed $v$}};

    \foreach \x in {-2.5, 2.5} {
        \fill[unusedMirror] (\x-0.7, 3) rectangle (\x+0.7, 3.2);
    }
    \foreach \x in {-2.5, 2.5} {
        \fill[mirror] (\x-0.7, 0) rectangle (\x+0.7, 0.2);
    }
    \fill[mirror] (-0.7, 3.0) rectangle (0.7, 3.2);
    \fill[unusedMirror] (-0.7, 0) rectangle (0.7, 0.2);


    \draw[dashed, thick] (0, 3) -- (0, 0.2) node[midway, right, black] {$c\tau$};
    \draw[dashed, thick] (0, 3) -- (0, 0.2) node[midway, right, black] {$c\tau$};

    \draw[ultra thick, orange, -{Stealth[scale=1.2]}] (-2.1, 0.2) -- (-0.1, 3) node[midway, left=2pt, black] {$ct$};
    \draw[ultra thick, orange, -{Stealth[scale=1.2]}] (0.1, 3) -- (2.1, 0.2) node[midway, right=2pt, black] {$ct$};

    \node[] at (-1.05, 0.5) {$x = vt$};
    \draw[dashed, thick] (-1.8, 0.1) -- (-0.7, 0.1);
    \node[] at (1.05, 0.5) {$x = vt$};
    \draw[dashed, thick] (0.7, 0.1) -- (1.8, 0.1);
\end{scope}
\end{tikzpicture}
\end{document}
```

For an observer moving with the clock, the light takes $2\tau$ to make a round-trip.

For an observer watching the clock travel past at speed $v$, the Pythagorean theorem can be used (where $t$ is the time experienced by the clock):
$$
\begin{split}
(ct)^2 &= (c\tau)^2 + (vt)^2
\\ c^2t^2 &= c^2\tau^2 + v^2t^2
\\ c^2t^2 - v^2t^2 &= c^2\tau^2
\\ t^2(c^2-v^2) &= c^2\tau^2
\\ t^2 &= \frac{c^2\tau^2}{c^2-v^2}
\\ t^2 &= \tau^2 \frac{1}{1-\frac{v^2}{c^2}}
\\ t &= \tau \sqrt{\frac{1}{1-\frac{v^2}{c^2}}}
\\ t &= \tau \gamma
\end{split}
$$
So to the observer, the time taken per tick was $\tau$, while from the clock's frame of reference, the time taken per tick was $t = \tau\gamma$. As $\gamma \ge 1$, the clock ticks 'slower' from the clock's frame of reference.

In general, time passes more slowly for objects moving at high speeds, compared to stationary observers. The **time dilation** is given by $t = \gamma\tau$, which is *not on the formula booklet*.

*NIS: Length contraction is not explicitly mentioned on the specification.*
**Length contraction** is another consequence of special relativity.
- Consider a particle moving at speed $v$ relative to a stationary observer.
- A clock moving with the particle measures a time $\tau$ for the rod to travel a length $L$. So $v = \frac{L}{\tau}$
- The stationary observer measures the same time $\tau$ to be dilated, giving time $t = \gamma\tau$ for the particle to travel a length $L_0$. So $v = \frac{L_0}{\gamma\tau}$.
- The relative velocities in both frames must be identical, so $v = \frac{L}{\tau} = \frac{L_0}{\gamma\tau}$.
- Rearranging gives $L = \frac{L_0}{\gamma}$.

So to the particle, the length was $\frac{L_0}{\gamma}$, while from the stationary observer, the length was $L_0$. As $\gamma \ge 1$, the particle travels a smaller distance in its own frame of reference compared to a stationary observer.
