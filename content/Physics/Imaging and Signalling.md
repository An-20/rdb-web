## Imaging
#### Converging lenses
Light can be modelled using **rays** or **wavefronts**. which are perpendicular to the direction of wave motion. Wavefronts have curvature, unless they come from a very distant source, in which case they are **plane wavefronts**.

Curvature is given by:
$$
\text{curvature} = \frac{1}{\text{radius}}
$$
As the radius approaches infinity, the curvature approaches zero.

Converging lenses focus light onto a point behind them, called the **principal focus**. The principal focus lies a distance $f$, the **focal length**, away from the lens. A converging lens has a **power** (measured in Dioptres, $\text{D}$) of $\frac{1}{f}$, which means the lens adds a curvature of $\frac{1}{f}$ to wavefronts passing through it.

```tikz
\usetikzlibrary{arrows.meta, decorations.markings}

\begin{document}
\begin{tikzpicture}[
    ray/.style={thick, black, decoration={markings, mark=at position 0.5 with {\arrow{Stealth}}}, postaction={decorate}},
    wavefront/.style={thin, lightgray},
    lens/.style={fill=cyan!20, draw=cyan!40, semithick}
]
    \def\focal{4}
    \def\height{2.5}
    \def\lensW{0.4}

    \draw[dashed] (-5,0) -- (6,0) node[right] {Optical Axis};
    \draw[lens] (0,\height) .. controls (\lensW,0) .. (0,-\height)
                .. controls (-\lensW,0) .. (0,\height) -- cycle;
    \node at (0, \height+0.5) {Converging Lens};

    \filldraw (\focal,0) circle (2pt) node[below right] {$F$};

    \foreach \y in {-1.5, -0.75, 0, 0.75, 1.5} {
        \draw[ray] (-4.5, \y) -- (0, \y);
        \draw[ray] (0, \y) -- (\focal, 0);
        \draw[] (\focal, 0) -- (\focal + 1, {-\y*1/ \focal});
    }

    \foreach \x in {-4, -3, -2, -1} {
        \draw[wavefront] (\x, -\height*0.7) -- (\x, \height*0.7);
    }
    \node at (-2.5, -2) {Planar wavefronts};

    \foreach \r in {1, 2, 3} {
        \draw[wavefront] (\focal-\r, 0) arc (180:150:\r) (\focal-\r, 0) arc (180:210:\r);
    }
    \node at (2, -2) {Curved wavefronts};

    \draw[|-|, thick] (0, -2.8) -- node[below] {Focal length $f$} (\focal, -2.8);

\end{tikzpicture}
\end{document}
```

The **Lensmaker's Equation** shows how a converging lens works:
$$
\begin{split}
\text{curvature of waves leaving lens} &= \text{curvature of waves entering} + \text{power of lens} \\
\frac{1}{v} &= \frac{1}{u} + \frac{1}{f}
\end{split}
$$
Where $v$ is image distance, $u$ is object distance, and $f$ is the focal length. By the **Cartesian sign convention**[^1], $u$ is negative, while $v$ and $f$ are positive.

Lenses can also magnify objects. Linear magnification is given by:
$$
\text{linear magnification} = \frac{\text{image height}}{\text{object height}} = \frac{\text{image distance}}{\text{object distance}} = \frac{v}{u}
$$

#### Images
Digital cameras contain a microchip called a **CCD (charge-coupled device)**. The CCD has a screen with millions of **pixels**, which store charge when light falls on them, storing an amount of charge proportional to the intensity of incident light. A pixel is the smallest unit of a single image, with a single colour. The charges are converted to an **array of numbers** which represents an image.

Information is stored in **binary**, using **bits** with one of two values: 0 and 1. The number of bits, $b$ needed to represent $N$ different alternatives are related by:
$$
N = 2^b\,\,\,\,\,\,\,\,\,b=\log_2N
$$

The **resolution** of an image is the smallest distance between two points which can be distinguished:
$$
\text{resolution} = \frac{\text{width / height of image}}{\text{number of pixels}}
$$

The **amount of information** in an image (in bits) is given by:
$$
\text{amount of information in image} = \text{no. of pixels} \times \text{bits per pixel}
$$
###### Manipulating images
Computer images are stored as an array of numbers. They can be manipulated
in the following ways to enhance the image:
- **Varying brightness**: adding a fixed number to the value of each pixel.
- **Increasing contrast**: multiplying the value of each pixel by a fixed number so the range of pixel values is greater.
- **Removing noise**: replacing the value of each pixel with the mean / median of the 8 pixels immediately around it.
- **Edge detection**: subtracting the average value of the 8 pixels around a pixel from the pixel value.
- **False colour**: assigning colours different from the true colours, commonly used for displaying images captured with parts of the electromagnetic spectrum outside visible light.

## Digital and analogue signals
**Analogue** signals continuously vary between values, whereas **digital** signals can only take discrete values. Analogue signals are converted to digital signals by **sampling**. The signal is sampled at regular intervals, with a measurement of the amplitude taken and rounded to the nearest **quantisation level**. This produces a **quantisation error** equal to the difference between the actual value and the quantisation level.

**Advantages of digital signals**:
- More resistant to noise
- Easier to send / store / receive with digital systems
- Faster transmission
- Can be compressed easily.

**Disadvantages of digital signals**:
- Quantisation error causes loss of detail.

The maximum number of useful quantisation levels is given by:
$$
\text{Maximum no. of useful quantisation levels} = \frac{V_\text{total}}{V_\text{noise}}
$$
The number of bits required is given by:
$$
b = \log_2\left(\frac{V_\text{total}}{V_\text{noise}}\right)
$$

When sampling, the **minimum sampling rate** must be **at least twice the highest frequency** in the signal (Nyquist's Theorem), otherwise aliasing will occur, producing spurious low frequency signals.

**Bit rate** is the rate of transmission of digital information. It is given by:
$$
\text{Rate of transmission of information} = \text{samples per second} \times \text{bits per sample}
$$

## Polarisation
**Electromagnetic waves** are transverse waves, consisting of oscillating **magnetic** and **electric fields** at **right angles** to each other. Unpolarised waves have oscillations in all perpendicular directions[^2]. A polarising filter can be used to **polarise** transverse waves, which makes them only oscillate in one plane.

```tikz
\usetikzlibrary{arrows.meta}

\begin{document}
\begin{tikzpicture}[
    >=Stealth,
    osc/.style={->, thin, opacity=0.8},
    main/.style={thick, ->},
    label font/.style={align=left}
]
\def\len{0.7cm}

\begin{scope}[shift={(0,0)}]
	\draw[main] (-3, 1.2) -- (0, 0);

	\begin{scope}[shift={(-1.5, 0.6)}]
	    \foreach \angle in {0, 45, 90, 135, 180, 225, 270, 315} {
	        \draw[osc] (0,0) -- +(\angle:\len);
	    }
	\end{scope}
	\node[label font, anchor=center, align=center] at (-1.5, 1.8) {Transverse oscillations\\in all planes};
	\node[label font, anchor=center] at (-1.5, -0.6) {Unpolarised wave};
\end{scope}

\begin{scope}[shift={(6,0)}]
	\draw[main] (-3, 1.2) -- (0, 0);
	\begin{scope}[shift={(-1.5, 0.6)}]
	    \foreach \angle in {45, 225} {
	        \draw[osc] (0,0) -- +(\angle:\len);
	    }
	\end{scope}
	\node[label font, anchor=center, align=center] at (-1.5, 1.8) {Transverse oscillations\\in one plane};
	\node[label font, anchor=center] at (-1.5, -0.6) {Polarised wave};
\end{scope}

\end{tikzpicture}
\end{document}
```

To test if a wave is polarised, it can be observed through a polarising filter. For an unpolarised wave, the intensity should remain constant as the polariser is rotated, whereas for a polarised wave, the intensity will vary sinusoidally. There is $90\degree$ between the maximum and minimum intensity.

*NIS*: The received intensity is given by $I = I_0 \cos^2\theta$, where $I_0$ is the incident intensity and $\theta$ is the angle between the polariser and the incident polarisation direction. This means $I$ is at a maximum for $\theta = 0\degree,\,180\degree$, and at a minimum for $\theta = 90\degree,\,270\degree$. Intuitively, this can be thought of as the bars of the polarising 'blocking' the oscillations.
```tikz
\begin{document}
\begin{tikzpicture}[xscale=0.025, yscale=2]
    \draw[->] (-10,0) -- (380,0) node[right] {$\theta^\circ$};
    \draw[->] (0,-0.1) -- (0,1.3) node[above] {$I$};
    \draw[dashed] (360,1) -- (0,1) node[left] {\small $I_0$};

    \foreach \x in {0, 90, 180, 270, 360}
        \draw (\x, 0.05) -- (\x, -0.05) node[below] {\small \x};
    \draw[samples=100, domain=0:360] plot (\x, {cos(\x)*cos(\x)});
    \node at (180, 1.2) {$I = I_0 \cos^2\theta$};
\end{tikzpicture}
\end{document}
```



[^1]: **Footnote on the Cartesian sign convention**
	This is mentioned explicitly in the specification.
[^2]:**Footnote on wording of polarisation**
	This wording is mildly confusing. In a polarised EM wave, each field of the wave oscillates in only one plane; the magnetic field oscillates in only one plane and the electric field oscillates in only one other plane (at right angles still)
