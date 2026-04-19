#### Overview
The defining feature of **simple harmonic motion** is when the **restoring force** of a system is proportional to its displacement from some equilibrium position:
$$
\frac{\text{d}^2 x}{\text{d}t^2} = -\frac{k}{m}x
$$

This equation describes a spring-mass system where $x$ is the displacement from **equilibrium position**, $k$ is the spring constant, and $m$ is the mass:
```tikz
\usetikzlibrary{patterns, decorations.pathmorphing}

\begin{document}
\begin{tikzpicture}[>=stealth]
    \fill [pattern = north east lines] (-0.5,0) rectangle (0.5,0.3);
    \draw (-0.5,0) -- (0.5,0);

    \draw [decoration={aspect=0.3, segment length=2mm, amplitude=3mm, coil}, decorate] (0,0) -- (0,-3.5) node[midway, right=10pt] {$k$};

    \node [draw, circle, minimum size=0.1cm, fill=black!20, inner sep=0pt] (mass) at (0,-3.65) {$m$};

    \draw [dashed] (-1.5, -2.5) -- (1.5, -2.5) node[right] {Equilibrium ($x=0$)};
    \draw [|-|] (1.2, -2.5) -- (1.2, -3.6) node[midway, right] {$x$};

    \draw [<-, ultra thick, red] (0, -3.05) -- (0, -3.65) node[below] {$F = -kx$};

    \draw [->] (-1.8, -1.5) -- (-1.8, -3.65) node[below] {$+x$};
\end{tikzpicture}
\end{document}
```
Note that in this case, $x$ is not the extension, but rather the displacement from equilibrium length, that is the $l$ such that $kl = mg$.

#### SHM Solutions
The differential equation $a = -\omega^2 x$ has two possible solutions:
$$
\begin{split}
x &= A \sin(\omega t) = A \sin(2\pi f t) \\ \\
x &= A \cos(\omega t) = A \cos(2\pi f t)
\end{split}
$$
(*NIS*): In general, there could be a phase offset of $\theta$, giving $x = A\sin(\omega t + \theta)$.

Where $A$ is the **amplitude** and $\omega$ is the **angular frequency**, such that $\omega = 2\pi f$. For systems such as a pendulum, $\omega$ is not the actual angular frequency of the pendulum itself, but rather the angular frequency of the phasor representing the system.

```tikz
\usetikzlibrary{calc}

\begin{document}
\begin{tikzpicture}[>=stealth]
\def\Amplitude{1.5}
\def\Period{4.0}
\def\Gap{1.5}
\def\PlotWidth{\Period + 0.7}
\def\ContinueLen{1.0}

\tikzstyle{axis} = [->, thick]
\tikzstyle{label} = []
\tikzstyle{curve} = [ultra thick, samples=50]
\tikzstyle{continue} = [thick, dashed, samples=50]

% sin
\begin{scope}
	\node[anchor=north] at (\Period/2, -\Amplitude - 1.6) {\textbf{$x = A \sin(\omega t)$}};

	\draw[axis] (0, 0) -- (\PlotWidth + \ContinueLen + 0.2, 0) node[right, label] {$t$};
	\draw[axis] (0, -\Amplitude - 0.2) -- (0, \Amplitude + 0.5) node[above, label] {$x$};

	\draw[curve, blue, domain=0:\Period] 
		plot (\x, {\Amplitude * sin(360/\Period * \x)});
	\draw[continue, blue, domain=\Period:\Period+\ContinueLen] 
		plot (\x, {\Amplitude * sin(360/\Period * \x)});

	\node[anchor=east, label] at (0, \Amplitude) {$A$};
	\node[anchor=east, label] at (0, -\Amplitude) {$-A$};
	\draw[dashed] (0, \Amplitude) -- (\Period/4, \Amplitude);
	\draw[dashed] (0, -\Amplitude) -- (3*\Period/4, -\Amplitude);

	\draw[thick] (\Period, 0.1) -- (\Period, -0.1) node[below=2pt, label] {$T$};
	\draw[thick] (\Period/2, 0.1) -- (\Period/2, -0.1) node[below=2pt, label] {$T/2$};

	\draw[|-|, thick] (0, -1.9) -- (\Period, -1.9) 
		node[midway, label, below] {$\displaystyle T = \frac{2\pi}{\omega} = \frac{1}{f}$};
\end{scope}

% cos
\begin{scope}[shift={(\PlotWidth + \Gap + \ContinueLen, 0)}]
	\node[anchor=north] at (\Period/2, -\Amplitude - 1.6) {\textbf{$x = A \cos(\omega t)$}};
	\draw[axis] (0, 0) -- (\PlotWidth + \ContinueLen + 0.2, 0) node[right, label] {$t$};
	\draw[axis] (0, -\Amplitude - 0.2) -- (0, \Amplitude + 0.5) node[above, label] {$x$};

	\draw[curve, red, domain=0:\Period] 
		plot (\x, {\Amplitude * cos(360/\Period * \x)});
	\draw[continue, red, domain=\Period:\Period+\ContinueLen] 
		plot (\x, {\Amplitude * cos(360/\Period * \x)});

	\node[anchor=east, label] at (0, \Amplitude) {$A$};
	\node[anchor=east, label] at (0, -\Amplitude) {$-A$};
	\draw[dashed] (0, \Amplitude) -- (\Period, \Amplitude);
	\draw[dashed] (0, -\Amplitude) -- (\Period/2, -\Amplitude);

	\draw[thick] (\Period, 0.1) -- (\Period, -0.1) node[below=2pt, label] {$T$};
	\draw[thick] (\Period/2, 0.1) -- (\Period/2, -0.1) node[below=2pt, label] {$T/2$};

	\draw[|-|, thick] (0, -1.9) -- (\Period, -1.9) 
		node[midway, label, below] {$\displaystyle T = \frac{2\pi}{\omega} = \frac{1}{f}$};

\end{scope}
\end{tikzpicture}
\end{document}
```

Whether to use the $\sin$ or $\cos$ solution depends on the **initial conditions**:
- If the system is initially at maximum displacement (and zero velocity), the solution will be $x = A \cos(\omega t)$
- If the system is initially at zero displacement (from equilibrium) and maximum velocity, the solution will be $x = A \sin(\omega t)$.

The relationships between $x$-$t$, $v$-$t$, and $a$-$t$ graphs are:
- The velocity, $v$, is given by differentiating the displacement, $x$. As all solutions can be written in the form $x = A\sin(\omega t + \theta)$, the velocity will take the form $v = A\omega \cos(\omega t + \theta)$, meaning that the phase of the velocity is $\frac{\pi}{2}$ radians or $90\degree$ ahead of the displacement.

- Similarly, the acceleration is given by differentiating the velocity to get $a = -\omega^2 A \sin(\omega t + \theta) = -\omega^2 x$, the defining SHM relationship. The acceleration is proportional to the negative of the displacement.

These relationships are shown on the graph below, where the left graph shows $x$ (blue) and $a$ (dashed red), and the right graph shows $v$.

```tikz
\usetikzlibrary{calc}

\begin{document}
\begin{tikzpicture}[>=stealth]
\def\Amplitude{1.5}
\def\Period{4.0}
\def\Gap{1.5}
\def\PlotWidth{\Period + 0.7}
\def\ContinueLen{1.0}

\tikzstyle{axis} = [->, thick]
\tikzstyle{label} = []
\tikzstyle{curve} = [ultra thick, samples=50]
\tikzstyle{continue} = [thick, dashed, samples=50]

% sin
\begin{scope}
	\node[anchor=north] at (\Period/2, -\Amplitude - 1.6) {\textbf{$x = A \sin(\omega t)$}};

	\draw[axis] (0, 0) -- (\PlotWidth + \ContinueLen + 0.2, 0) node[right, label] {$t$};
	\draw[axis] (0, -\Amplitude - 0.2) -- (0, \Amplitude + 0.5) node[above, label] {$x$};

	\draw[curve, blue, domain=0:\Period] 
		plot (\x, {\Amplitude * sin(360/\Period * \x)});
	\draw[continue, blue, domain=\Period:\Period+\ContinueLen] 
		plot (\x, {\Amplitude * sin(360/\Period * \x)});

	\draw[dashed, red, domain=0:\Period+\ContinueLen] 
		plot (\x, {-\Amplitude * 0.6 * sin(360/\Period * \x)});

	\node[anchor=east, label] at (0, \Amplitude) {$A$};
	\node[anchor=east, label] at (0, -\Amplitude) {$-A$};
	\draw[dashed] (0, \Amplitude) -- (\Period/4, \Amplitude);
	\draw[dashed] (0, -\Amplitude) -- (3*\Period/4, -\Amplitude);

	\draw[thick] (\Period, 0.1) -- (\Period, -0.1) node[below=2pt, label] {$T$};
	\draw[thick] (\Period/2, 0.1) -- (\Period/2, -0.1) node[below=2pt, label] {$T/2$};

	\draw[|-|, thick] (0, -1.9) -- (\Period, -1.9) 
		node[midway, label, below] {$\displaystyle T = \frac{2\pi}{\omega} = \frac{1}{f}$};
\end{scope}

% cos
\begin{scope}[shift={(\PlotWidth + \Gap + \ContinueLen, 0)}]
	\node[anchor=north] at (\Period/2, -\Amplitude - 1.6) {\textbf{$v = A \omega\cos(\omega t)$}};
	\draw[axis] (0, 0) -- (\PlotWidth + \ContinueLen + 0.2, 0) node[right, label] {$t$};
	\draw[axis] (0, -\Amplitude - 0.2) -- (0, \Amplitude + 0.5) node[above, label] {$x$};

	\draw[curve, red, domain=0:\Period] 
		plot (\x, {\Amplitude * cos(360/\Period * \x)});
	\draw[continue, red, domain=\Period:\Period+\ContinueLen] 
		plot (\x, {\Amplitude * cos(360/\Period * \x)});

	\node[anchor=east, label] at (0, \Amplitude) {$A\omega$};
	\node[anchor=east, label] at (0, -\Amplitude) {$-A\omega$};
	\draw[dashed] (0, \Amplitude) -- (\Period, \Amplitude);
	\draw[dashed] (0, -\Amplitude) -- (\Period/2, -\Amplitude);

	\draw[thick] (\Period, 0.1) -- (\Period, -0.1) node[below=2pt, label] {$T$};
	\draw[thick] (\Period/2, 0.1) -- (\Period/2, -0.1) node[below=2pt, label] {$T/2$};

	\draw[|-|, thick] (0, -1.9) -- (\Period, -1.9) 
		node[midway, label, below] {$\displaystyle T = \frac{2\pi}{\omega} = \frac{1}{f}$};

\end{scope}
\end{tikzpicture}
\end{document}
```

###### Time periods
The **time period** of an SHM system is $T = \frac{1}{f} = \frac{2\pi}{\omega}$. For a spring-mass system, $a = \frac{\text{d}^2 x}{\text{d}t^2} = -\frac{k}{m}x = -\omega^2$, giving $\omega = \sqrt\frac{k}{m}$:
$$
T = 2\pi\sqrt{\frac{m}{k}}
$$

For a simple pendulum, $a = \frac{\text{d}^2 x}{\text{d}t^2} \approx -\frac{g}{L}x = -\omega^2$ (small angle approximation), giving $\omega = \sqrt{\frac{g}{L}}$:
$$
T = 2\pi\sqrt{\frac{L}{g}}
$$

#### Energy changes
In the ideal SHM situations described above, energy is conserved. Thus, kinetic energy is transferred to and from potential energy (e.g. elastic potential, gravitational potential). 

For a force of $F = kx$, the work done against it can be found by integrating with respect to $x$, giving:
$$
E = \frac{1}{2}kx^2
$$

#### Free, forced, and damped vibrations
**Free oscillations** have constant amplitude, when a system oscillates at its **natural frequency**. When an external **periodic driving force** is added, **forced oscillations** occur.

**Resonance** occurs when the driving frequency is close to the natural frequency of the system. This creates large amplitude oscillations, which store energy. The amplitude of oscillations increases until the energy provided by the driving force each cycle equals the energy lost to damping.

**Damping** is when an oscillator loses energy because of forces such as friction or air resistance. This causes real-world oscillations to decrease in amplitude.
```tikz
\begin{document}
\begin{tikzpicture}[>=stealth]
    \def\Amplitude{1.0}
    \def\Damping{0.5}
    \def\Omega{4.0}
    \def\EndTime{6.0}

    \tikzstyle{axis} = [->, thick]
    \tikzstyle{label} = [black]

    \begin{scope}
        \draw[axis] (0, 0) -- (\EndTime + 0.3, 0) node[right, label] {$t$};
        \draw[axis] (0, -\Amplitude - 0.2) -- (0, \Amplitude + 0.5) node[above, label] {$x$};
        \draw[thick, samples=80, domain=0:\EndTime] 
            plot (\x, {\Amplitude * exp(-\Damping * \x) * cos(\Omega * \x r)});
    \end{scope}
\end{tikzpicture}
\end{document}
```

The degree of damping affects how much resonance is observed. Generally, the resonance is greatest when the frequency of the driving force $f$ is close to the natural frequency $f_0$.

```tikz
\usepackage{amsmath}
\usetikzlibrary{calc}

\begin{document}
\begin{tikzpicture}[>=stealth]
\tikzset{
	axis/.style={->, thick},
	label_text/.style={black, font=\small},
	curve/.style={thick, samples=100},
	guide/.style={dashed, thin},
	peak_arr/.style={<->, thick}
}
\def\PlotW{4}
\def\PlotH{2.5} 

% left
\begin{scope}
	\node[anchor=south west, font=\footnotesize, align=center] at (0, -1.5) {
		\textbf{Low damping}\\
		Large max response, sharp peak.
	};

	\draw[axis] (0,0) -- (0, \PlotH + 0.5) node[above, label_text] {$A/A_0$};
	\draw[axis] (0,0) -- (\PlotW + 0.5, 0) node[right, label_text] {$f/f_0$};

	\draw[curve, domain=0:\PlotW] plot (\x, {\PlotH / (1 + 15*((\x/2)-1)^2)});
	\draw[guide] (2,0) -- (2, \PlotH);
    \draw[guide] (0, \PlotH) -- (2, \PlotH);
	\draw (2, 0.1) -- (2, -0.1) node[below] {1.0};
	\draw (0.1, \PlotH) -- (-0.1, \PlotH) node[left] {4};
\end{scope}

% right
\begin{scope}[xshift=7cm]
	\node[anchor=south west, font=\footnotesize, align=center] at (0, -1.5) {
		\textbf{High damping}\\
		Smaller response, broader peak.
	};

	\draw[axis] (0,0) -- (0, \PlotH + 0.5) node[above, label_text] {$A/A_0$};
	\draw[axis] (0,0) -- (\PlotW + 0.5, 0) node[right, label_text] {$f/f_0$};

	\draw[curve, domain=0:\PlotW] plot (\x, {(\PlotH/2) / (1 + 4*((\x/2)-1)^2)});
	\draw[guide] (2,0) -- (2, \PlotH/2);
    \draw[guide] (0, \PlotH/2) -- (2, \PlotH/2);
	\draw (2, 0.1) -- (2, -0.1) node[below] {1.0};
	\draw (0.1, \PlotH/2) -- (-0.1, \PlotH/2) node[left] {2};
\end{scope}
\end{tikzpicture}
\end{document}
```

(*IS*): qualitative treatment of free and forced vibrations, damping and resonance, and graphs of amplitude of a resonator against driving frequency.
