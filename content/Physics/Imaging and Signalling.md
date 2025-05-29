## Imaging
#### Converging lenses
Light can be modelled using **rays** or **wavefronts**. which are perpendicular to the direction of wave motion. Wavefronts have curvature, unless they come from a very distant source, in which case they are **plane wavefronts**.

Curvature is given by:
$$
\text{curvature} = \frac{1}{\text{radius}}
$$
As the radius approaches infinity, the curvature approaches zero.

Converging lenses focus light onto a point behind them, called the **principal focus**. The principal focus lies a distance $f$, the **focal length**, away from the lens. A converging lens has a **power** (measured in Dioptres, $\text{D}$) of $\frac{1}{f}$, which means the lens adds a curvature of $\frac{1}{f}$ to wavefronts passing through it.

The Lensmaker's Equation shows how a converging lens works:
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
Digital cameras contain a microchip called a **CCD (charge-coupled device)**. The CCD has a screen with millions of **pixels**, which store charge when light falls on them, storing an amount of charge proportional to the intensity of incident light. The charges are converted to an **array of numbers** which represents an image.

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
- **Varying brightness**: adding a fixed number to the value of each pixel
- **Increasing contrast**: multiplying the value of each pixel by a fixed number so the range of pixel values is greater
- **Removing noise**: replacing the value of each pixel with the mean / median of the 8 pixels immediately around it
- **Edge detection**: subtracting the average value of the 8 pixels around a pixel from the pixel value

## Digital and analogue signals
**Analogue** signals continuously vary between values, whereas **digital** signals can only take discrete values. Analogue signals are converted to digital signals by **sampling**. The signal is sampled at regular intervals, with a measurement of the amplitude taken and rounded to the nearest **quantisation level**. This produces a **quantisation error** equal to the difference between the actual value and the quantisation level.

**Advantages of digital signals**:
- More resistant to noise
- Easier to send / store / receive with digital systems
- Faster transmission
- Can be compressed easily

**Disadvantages of digital signals**:
- Quantisation error causes loss of detail

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
**Electromagnetic waves** are transverse waves, consisting of oscillating **magnetic** and **electric fields** at **right angles** to each other. Transverse waves can be **polarised**, which means they oscillate in only one plane[^2].


[^1]: **Footnote on the Cartesian sign convention**
	This is mentioned explicitly in the specification.
[^2]:**Footnote on wording of polarisation**
	This wording is mildly confusing. In a polarised EM wave, each field of the wave oscillates in only one plane; the magnetic field oscillates in only one plane and the electric field oscillates in only one other plane (at right angles still)