## Trig functions
The **unit circle** is a circle with radius 1 centred at the origin (possibly *NIS* but a useful model regardless).
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[scale=0.8]
	\draw[step=2cm,very thin] (-2.5,-2.5)grid(2.5,2.5);
	\draw(-2.75,0) -- (2.75,0);
	\draw(0,-2.75) -- (0,2.75);
	\node[fill=white] at (-0.4,-0.4){0};
	\foreach \x in {-1,1} \node[] at (-0.4,2*\x){\x};
	\foreach \x in {-1,1} \node[] at (2*\x,-0.4){\x};
	\draw (0, 0) circle (2);

	\coordinate[label=above left:$A$](A) at (2*0.70710678118, 2*0.70710678118);
	\coordinate[label=below right:$B$](B) at (2*0.70710678118, 0);
	\coordinate[label=below:$O$](O) at (0, 0);
	\node at (0.35, 0.15) {$\theta$};
	\draw (A) -- (B) -- (O) -- cycle;
	\draw (2*0.70710678118-.2,0) rectangle (2*0.70710678112,.2);
\end{tikzpicture}
\end{document}
```
For an angle $\theta$ drawn **anticlockwise** from the $x$ axis:
- $\cos \theta = \frac{OB}{OA}$ and $OA = 1$, so $x = OB = \cos \theta$.
- $\sin\theta = \frac{AB}{OA}$ and $OA = 1$, so $y = AB = \sin \theta$.

There are other trig functions:
$$
\begin{align}
\tan\theta = \frac{\sin\theta}{\cos\theta}\quad\quad 
&\cot\theta = \frac{1}{\tan\theta} = \frac{\cos\theta}{\sin\theta} \\
\\
\sec\theta = \frac{1}{\cos\theta}\quad\quad
&\operatorname{cosec}\theta = \frac{1}{\sin\theta}
\end{align}
$$

### Graphs
###### Graph of $\cos\theta$
```tikz
\usepackage{tikz}

\begin{document}
\begin{tikzpicture}[scale=1]
  % axes
  \draw[->] (-7,0) -- (7,0) node[right] {$x$};
  \draw[->] (0,-1.5) -- (0,1.5) node[above] {$y$};
  
  % x-axis labels
  \foreach \x/\lbl in {-6.28/-2\pi, -3.14/-\pi, 0/0, 3.14/\pi, 6.28/2\pi}
    \draw (\x,0) -- (\x,-0.1) node[below] {$\lbl$};

  % y-axis labels
  \foreach \y in {-1,1}
    \draw (0,\y) -- (-0.1,\y) node[left] {$\y$};

  % sine curve
  \draw[thick,smooth,samples=100,domain=-6.28:6.28]
    plot(\x,{cos(\x r)});
\end{tikzpicture}
\end{document}
```
The $\cos\theta$ graph is even (symmetric about $x=0$) and continues indefinitely with a period of $2\pi$.
###### Graph of $\sin\theta$
```tikz
\usepackage{tikz}

\begin{document}
\begin{tikzpicture}[scale=1]
  % axes
  \draw[->] (-7,0) -- (7,0) node[right] {$x$};
  \draw[->] (0,-1.5) -- (0,1.5) node[above] {$y$};
  
  % x-axis labels
  \foreach \x/\lbl in {-6.28/-2\pi, -3.14/-\pi, 0/0, 3.14/\pi, 6.28/2\pi}
    \draw (\x,0) -- (\x,-0.1) node[below] {$\lbl$};

  % y-axis labels
  \foreach \y in {-1,1}
    \draw (0,\y) -- (-0.1,\y) node[left] {$\y$};

  % sine curve
  \draw[thick,smooth,samples=100,domain=-6.28:6.28]
    plot(\x,{sin(\x r)});
\end{tikzpicture}
\end{document}
```
The $\sin\theta$ graph is odd (rotational symmetry order 2 about the origin) and also continues indefinitely with a period of $2\pi$.
###### Graph of $\tan\theta$
```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
  \draw[->] (-7,0) -- (7,0) node[right] {$x$};
  \draw[->] (0,-3) -- (0,3) node[above] {$y$};

  \foreach \x/\lbl in {-6.28/-2\pi, -3.14/-\pi, 0/0, 3.14/\pi, 6.28/2\pi}
    \draw (\x,0) -- (\x,-0.1) node[below] {$\lbl$};
  \foreach \y in {-2,-1,1,2}
    \draw (0,\y) -- (-0.1,\y) node[left] {$\y$};

  \clip (-7,-3) rectangle (7,3);
  \foreach \k/\txt in {-1.5/-\frac{3\pi}{2}, -0.5/-\frac{\pi}{2}, 0.5/\frac{\pi}{2}, 1.5/\frac{3\pi}{2}} {
    \draw[dashed] (\k*pi, -3) -- (\k*pi, 3);
    \node[anchor=north, inner sep=1pt, right, yshift=-0.1cm] at (\k*pi, 2.8) {$x = \txt$};
  }

  \foreach \a in {-2,-1,0,1,2} {
    \draw[thick,smooth,samples=40,domain=(\a*pi-1.3):(\a*pi+1.3)]
      plot(\x,{tan(\x r)});
  }
\end{tikzpicture}
\end{document}
```
$\tan\theta  = \frac{\sin\theta}{\cos\theta}$, so the graph passes through the origin. Both $\sin\theta$ and $\cos\theta$ are positive in the first quadrant, so $\tan\theta$ is positive for $0 \lt x \lt \frac{\pi}{2}$. As $\cos\theta$ gets closer to 0 as $x$ approaches $\frac{\pi}{2}$, $\tan\theta$ gets larger and larger, with an asymptote at $\theta = \frac{\pi}{2}$. The graph continues indefinitely with a period of $\pi$.

## Trig identities
The two most basic **trigonometric identities** are:
$$
\begin{split}
\sin^2\theta + \cos^2\theta = 1\\\\
\tan\theta = \frac{\sin\theta}{\cos\theta}
\end{split}
$$
Dividing the first identity through by $\sin^2\theta$ or $\cos^2\theta$ gives:
$$
\begin{split}
\cot^2\theta + 1 &= \operatorname{cosec}^2\theta \\\\
\tan^2\theta + 1 &= \sec^2\theta \\\\
\end{split}
$$

#### Sine rule
The sine rule
$$
\frac{a}{\sin A} = \frac{b}{\sin B} = \frac{c}{\sin C}
$$
When using the sine rule to find angles, sometimes there may be two possible answers, $A$ and $180\degree - A$.
#### Cosine rule
$$
a^2 = b^2 + c^2 - 2bc\cos A
$$
#### Area of a triangle
The area of a triangle with sides $a$ and $b$ and an angle between them $C$ is given by:
$$
\frac{1}{2}ab\sin C
$$


## Radians
Angles can be measured in degrees or **radians**, with $2\pi\,(\approx6.28)$ radians in a circle ($360 \degree$). Thus, to convert between them:
- To convert from radians to degrees, multiply by $\frac{180\degree}{\pi}$
- To convert from degrees to radians, multiply by $\frac{pi}{180\degree}$.
#### Radians and geometry
The **length of an arc** of a circle with radius $r$ over angle $\theta$ subtended at the centre, in radians, is given by:
$$
l = r\theta
$$
The **area of a sector** of circle with radius $r$ over angle $\theta$ subtended at the centre, in radians, is given by:
$$
A = \frac{1}{2}r^2\theta
$$
#### Small angle approximations
The **small angle approximations** can be used for small angles measured in radians:
$$
\begin{split}
\sin\theta &\approx \theta \\
\cos\theta &\approx 1 - \frac{\theta^2}{2} \\
\tan\theta &\approx\theta 
\end{split}
$$

## Compound angle formulae
#### Geometric derivation
The main derivation for **compound angle formulae** is for $\cos(\alpha + \beta)$, with the other formulae following from this one. *IS*: geometric proof of the compound-angle formulae.

Consider $\triangle ABC$ as below, with $AH$ as an altitude to side $BC$.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\begin{document}
\pagestyle{empty}
\begin{tikzpicture}
	\coordinate[label=above left:$A$](A) at (2, 3);
	\coordinate[label=below right:$B$](B) at (4, 0);
	\coordinate[label=below left:$C$](C) at (-2, 0);
	\coordinate[label=below:$H$](H) at (2, 0);
	\node[xshift=-0.3cm, yshift=-0.5cm] at (2, 3) {$\alpha$};
	\node[xshift=0.15cm, yshift=-0.5cm] at (2, 3) {$\beta$};
	\draw (A) -- (B) -- (C) -- cycle;
	\draw (A) -- (H);
	\draw (1.8,0) rectangle (2,.2);
\end{tikzpicture}
\end{document}
```

The area of $\triangle ACH$ can be calculated:
$$
\begin{split}
\triangle ACH &= \frac{1}{2}(AC)(AH)\sin\alpha
\\ &= \frac{1}{2}(AC)(AB\cos\beta)\sin\alpha
\\ &= \frac{1}2{}(AC)(AB)\sin\alpha\cos\beta
\end{split}
$$
The area of $\triangle ABH$  can also be calculated:
$$
\begin{split}
\triangle ABH &= \frac{1}{2}(AB)(AH)\sin\beta
\\ &= \frac{1}{2}(AB)(AC\cos\alpha)\sin\beta
\\ &= \frac{1}2{}(AB)(AC)\cos\alpha\sin\beta
\end{split}
$$
By considering the area of $\triangle ABC$ as a whole:
$$
\begin{split}
\triangle ABC &= \triangle ACH + \triangle ABH \\
\frac{1}{2}(AB)(AC)\sin(\alpha + \beta) &= \frac{1}2{}(AC)(AB)\sin\alpha\cos\beta + \frac{1}2{}(AB)(AC)\sin\beta\cos\alpha \\
\sin(\alpha + \beta) &= \sin\alpha\cos\beta + \sin\beta\cos\alpha
\end{split}
$$
Giving the final result.

This result can be manipulated to derive the 3 other compound-angle identities for $\sin$ and $\cos$, which we leave a proof for below. These identities can be further manipulated to derive 2 additional compound-angle identities for $\tan$. The below 6 identities are *given*:
$$
\begin{split}
\sin(\alpha \pm \beta) &= \sin\alpha\cos\beta \pm \sin\beta\cos\alpha \\\\
\cos(\alpha \pm \beta) &= \cos\alpha\cos\beta \mp \sin\alpha\sin\beta \\\\
\tan(\alpha \pm \beta) &= \frac{\tan\alpha\pm\tan\beta}{1 \mp \tan\alpha\tan\beta}
\end{split}
$$

#### Phase shift form
An expression of the form $a\sin\theta + b\cos\theta$ can also be written in the forms:
$$
R\sin(\theta \pm \alpha) \quad \text{or} \quad R\cos(\theta \pm \alpha)
$$
for suitably chosen $R$ and $\alpha$. $R$ represents the **amplitude** of the resulting expression, while $\theta$ is a phase shift.

To rewrite an expression into these forms:
- Start with the target form and apply the compound-angle identity
- Compare coefficients on the $\sin\theta$ and $\cos\theta$ terms
- The amplitude is always given by $R = \sqrt{a^2 + b^2}$
- By dividing $\sin\alpha$ by $\cos\alpha$, $\tan\alpha$ and thus $\alpha$ can be found, taking care with signs
- Write the final expression with substituted values for $R$ and $\alpha$.


## Proofs
#### The cosine rule
Consider $\triangle ABC$ such that $AC = b$, $CB = a$, and $\angle ACB = C$. By SAS congruency, all triangles with these properties must be congruent, so $BC$ can only have one length.
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}
\begin{document}
\pagestyle{empty}
\begin{tikzpicture}
	\coordinate[label=above left:$A$](A) at (2, 3);
	\coordinate[label=below right:$B$](B) at (4, 0);
	\coordinate[label=below left:$C$](C) at (-2, 0);
	\coordinate[label=below:$H$](H) at (2, 0);
	\draw (A) -- (B) -- (C) -- cycle;
	\draw (A) -- (H);
	\draw (1.8,0) rectangle (2,.2);
\end{tikzpicture}
\end{document}
```
$AH$ is an altitude drawn to $CB$. The length of $CH$ can be calculated using basic trigonometry in right angle triangle $\triangle AHC$. $\cos C = \frac{CH}{b}$, so $CH = b\cos C$. 

With $CH$ known, $AH$ can be calculated using Pythagoras. $AH^2 = b^2 - (b\cos C)^2$
$HB = CB- CH = a - b\cos C$ 
With $HB$ and $AH$ known, $AB$ can be calculated using Pythagoras. 
$$
\begin{aligned}
AB^2 &= AH^2 + HB^2
\\ &= b^2 - (b\cos C)^2 + a^2 + (b\cos C)^2 - 2ab\cos C
\\ &= b^2 + a^2 - 2ab\cos C
\\ c^2&= a^2 + b^2 - 2ab\cos C
\end{aligned}
$$
Or alternatively:
$$
a^2 = b^2 + c^2 - 2bc\cos(A)
$$

#### The sine rule
```tikz
\usepackage{tikz}
\usetikzlibrary{decorations, decorations.text,backgrounds}
\usetikzlibrary{positioning}

\newcommand{\labelledpoint}[2]{\node[circle, fill=black,inner sep=2pt,label=45:\color{black}$#2$]at (#1){};}

\begin{document}
\pagestyle{empty}
\begin{tikzpicture}[background rectangle/.style={fill=white, rounded corners=.55cm}, show background rectangle]
	\draw (0, 0) circle (3);
	\coordinate[label=above right:$A$](A) at (30:3);
	\coordinate[label=above left:$B$](B) at (150:3);
	\coordinate[label=below right:$C$](C) at (290:3);
	\coordinate[label=left:$D$](D) at (240:1.2);
	\coordinate[label=below left:$E$](E) at (210:3);
	\draw (-2.39807621135,1.3) rectangle (-2.59807621135,1.5);
	\draw (A) -- (B) -- (E) -- cycle;
	\draw (B) -- (C);
	\draw (C) -- (A);
\end{tikzpicture}
\end{document}
```
Here, we know $\angle A$ and $\angle B$ and the side $C$ between them. We draw in the circumcircle of the triangle, making $AE$ a diameter of the circumcircle, which has radius $R$.

Because $\angle AEB$ and $\angle ACB$ subtend the same arc, they are equal.
$$
\begin{aligned}
\sin C &= \sin \angle AEB = \frac{AB}{BE} = \frac{c}{2R}
\\ 2R &= \frac{c}{\sin C}
\end{aligned}
$$
As there is nothing special about side $AB$, we can use the symmetry to write:
$$
\frac{a}{\sin A} = \frac{b}{\sin B} = \frac{c}{\sin C} = 2R
$$

#### Sine and cosine compound angle formulae
Starting with $\sin(\alpha + \beta) = \sin\alpha \cos\beta - \sin\beta\cos\alpha$$, we can apply some manipulations to find the three other variations.

To find $\sin(\alpha - \beta)$:
$$
\begin{aligned}
\sin(\alpha -\beta)) &= \sin(\alpha + (-\beta))
\\ &= \sin(\alpha)\cos(-\beta) + \sin(-\beta)\cos(\alpha)
\\ &= \sin(\alpha)\cos(\beta) - \sin(\beta)\cos(\alpha)
\end{aligned}
$$
Where on the third line we apply $\cos(-\theta) = \cos(\theta)$ and $\sin(-\theta) = -\sin(\theta)$.

To find $\cos(\alpha + \beta)$:
$$
\begin{aligned}
\cos(\alpha + \beta) &= \sin\left(\left(\frac{\pi}{2}-\alpha\right)-\beta\right)
\\ &= \sin\left(\frac{\pi}{2}-\alpha\right)\cos(\beta) 
- \sin(\beta)\cos\left(\frac{\pi}{2}-\alpha\right)
\\ &= \cos(\alpha)\cos(\beta) - \sin(\beta)\sin(\alpha)
\end{aligned}
$$
Where on the third line we apply $\sin(\theta) = \cos\left(\frac{\pi}{2}-\theta\right)$ and $\cos(\theta) = \sin\left(\frac{\pi}{2}-\theta\right)$

To find $\cos(\alpha - \beta)$:
$$
\begin{aligned}
\cos(\alpha - \beta) &= \sin\left(\frac{\pi}{2}-(\alpha-\beta)\right)
\\ &= \sin\left(\left(\frac{\pi}{2}-\alpha\right) +\beta\right)
\\ &= \sin\left(\frac{\pi}{2}-\alpha\right) \cos(\beta) 
+ \sin(\beta)\cos\left(\frac{\pi}{2}-\alpha\right)
\\ &= \cos(\alpha)\cos(\beta) + \sin(\beta)\sin(\alpha)
\end{aligned}
$$
Giving us all four addition formulae for $\sin$ and $\cos$:
$$
\begin{aligned}
\sin(\alpha + \beta) &= \sin(\alpha)\cos(\beta) + \sin(\beta)\cos(\alpha)
\\ \sin(\alpha - \beta) &= \sin(\alpha)\cos(\beta) - \sin(\beta)\cos(\alpha)
\\ \cos(\alpha + \beta) &= \cos(\alpha)\cos(\beta) - \sin(\beta)\sin(\alpha)
\\ \cos(\alpha -\beta) &= \cos(\alpha)\cos(\beta) + \sin(\beta)\sin(\alpha)
\end{aligned}
$$

#### Tangent compound angle formulae
From the $\sin$ and $\cos$ compound angle formulae, we can derive the compound angle formulae for $\tan$:
$$
\begin{aligned}
\tan(\alpha + \beta) &= \frac{\sin(\alpha + \beta)}{\cos(\alpha + \beta)}
\\
\\ &= \frac{\sin(\alpha)\cos(\beta) + \sin(\beta)\cos(\alpha)}
{\cos(\alpha)\cos(\beta) - \sin(\beta)\sin(\alpha)}
\\
\\ &= \frac{\tan(\alpha) + \tan(\beta)}
{1 - \tan(\alpha)\tan(\beta)} 
\end{aligned}
$$
Where on the third line we divide the numerator and denominator by $\cos(\alpha)\cos(\beta)$.

Similarly:
$$
\begin{aligned}
\tan(\alpha - \beta) &= \frac{\sin(\alpha - \beta)}{\cos(\alpha - \beta)}
\\
\\ &= \frac{\sin(\alpha)\cos(\beta) - \sin(\beta)\cos(\alpha)}
{\cos(\alpha)\cos(\beta) + \sin(\beta)\sin(\alpha)}
\\
\\ &= \frac{\tan(\alpha) - \tan(\beta)}
{1 + \tan(\alpha)\tan(\beta)} 
\end{aligned}
$$

