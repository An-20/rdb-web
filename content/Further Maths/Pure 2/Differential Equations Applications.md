#### Simple harmonic motion
Some differential equations have solutions with sines and cosines, which describe **oscillating behaviour**. **Simple harmonic motion** is described by a purely sinusoidal solution, and can be applied to many physical situations.

The differential equation for simple harmonic motion is:
$$
\frac{\textrm{d}^2x}{\textrm{d}t^2} = -\omega^2x
$$
Where $x$ represents the displacement from the **equilibrium position** (where the acceleration is zero). Solving this differential equation involves solving the auxillary equation $\lambda^2 = -\omega^2$, giving a general solution of:
$$
x = A\sin\omega t + B\cos\omega t
$$
The **general solution** can also be written as:
$$
x = R\sin(\omega t + \phi)
$$
Where $R$ is the **amplitude**, and $\phi$ is the **phase shift**.

For certain cases, the solution is simplified as either the $A$ or $B$ constants is clearly zero. For example:
- If an object is **initially at rest at maximum displacement from the equilibrium position**, then the general solution is $x = A\cos\omega t$.
- If an object is **initially at the equilibrium position**, then the general solution is $x = A\sin\omega t$.

There are some useful definitions for simple harmonic motion:
- The **equilibrium position** is the position around which the object oscillates.
- The **amplitude** is the maximum distance from the equilibrium position.
- The **period** is the time after which the motion repeats.
- The **angular frequency** is $\omega$ (omega).

The period and angular frequency are related, as the motion repeats when $\omega t = 2\pi$:
$$
T = \frac{2\pi}{\omega}
$$
The object has maximum speed as it goes through the equilibrium position. The object is instantaneously at rest when at maximum displacement from the equilibrium position.

For a object with simple harmonic motion with amplitude $a$, velocity and displacement are related by:
$$
v^2 = \omega^2(a^2-x^2)
$$
Proof of the above result:
- Let $x = a\sin\omega t$ (we can adjust when we start $t$ so this is true).
- Differentiating, we get $v = a\omega \cos\omega t$.
- Rearranging, we get $v^2 = a^2\omega^2\cos^2 \omega t = a^2\omega^2 - a^2\omega^2\sin^2 \omega t$.
- Substituting in $x = a\sin\omega t$, we get $v^2 = \omega^2a^2 - \omega x^2$.
- Giving $v^2 = \omega^2(a^2 - x^2)$ as required.

#### Damping
Objects often move against a **resistive force**, e.g. air resistance or water resistance. One way to account for these forces is to model them as proportional to the speed, acting against the motion:
$$
D = -Kv
$$
Where $K$ is a constant.

By applying $a=\frac{F}{m}=\frac{-Kv}{m}=-\frac{K}{m}\frac{\textrm{d}x}{\textrm{d}t}$:
$$
\begin{split}
&\frac{\textrm{d}^2x}{\textrm{d}t^2} = -\omega^2x -\frac{K}{m}\frac{\textrm{d}x}{\textrm{d}t} \\
\implies &\frac{\textrm{d}^2x}{\textrm{d}t^2} +\frac{K}{m}\frac{\textrm{d}x}{\textrm{d}t} + \omega^2x = 0 \\
\implies &\frac{\textrm{d}^2x}{\textrm{d}t^2} + k\frac{\textrm{d}x}{\textrm{d}t} + \omega^2x = 0 \quad\textrm{where}\,k=\frac{K}{m}
\end{split}
$$
This is called **damped simple harmonic motion**. The solutions to this differential equation depend on the discriminant of the auxiliary equation, from [[Differential Equations]].
$$
\lambda^2 + k\lambda + \omega^2 = 0
$$

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[scale=1]

  \begin{scope}[shift={(0,0)}]
	\draw[->] (-0.5,0) -- (3,0) node[right] {$x$};
	\draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=0:3]
	    plot(\x,{(2*exp(-2*\x)+exp(-\x)) * 4/5});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
	\node[align=left] at (1.3, -1.0) {$k^2 - 4\omega ^2 > 0$};
	\node[align=left] at (1.3, -1.5) {Overdamping};
	\node[align=left] at (1.3, -2.0) {$x = Ae^{\lambda_1 t} + Be^{\lambda_2 t}$};
  \end{scope}

  \begin{scope}[shift={(5,0)}]
	\draw[->] (-0.5,0) -- (3,0) node[right] {$x$};
	\draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=0:3]
	    plot(\x,{(\x + 0.4) * exp(-\x) * 3});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
	\node[align=left] at (1.3, -1.0) {$k^2 - 4\omega ^2 = 0$};
	\node[align=left] at (1.3, -1.5) {Critical damping};
	\node[align=left] at (1.3, -2.0) {$x = (A + Bt)e^{-\frac{k}{2}t}$};
  \end{scope}
  
    \begin{scope}[shift={(10,0)}]
	\draw[->] (-0.5,0) -- (3,0) node[right] {$x$};
	\draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
	\draw[thick,smooth,samples=100,domain=0:3]
	    plot(\x,{exp(-\x) * (cos(\x*150)) * 2});
	\node at (0, 0) [circle,fill,inner sep=1pt]{};
	\node[align=left] at (1.3, -1.0) {$k^2 - 4\omega ^2 < 0$};
	\node[align=left] at (1.3, -1.5) {Underdamping};
	\node[align=left] at (1.3, -2.0) {$x = e^{-\frac{k}{2}t}(A\sin\beta t + B\cos\beta t)$};
  \end{scope}

\end{tikzpicture}
\end{document}
```

The cases are:
- $k^2-4\omega^2>0$ describes **overdamping**, where there are no oscillations. The general solution is $x = Ae^{\lambda_1 t} + Be^{\lambda_2 t}$, where $\lambda_1$ and $\lambda_2$ are roots of the auxiliary equation.
- $k^2-4\omega^2=0$ describes **critical damping**. The general solution is $x = (A + Bt)e^{-\frac{k}{2}t}$, as if the discriminant is zero, the auxiliary equation will have a repeated root at $-\frac{k}{2}$.
- $k^2-4\omega^2=0$ describes **underdamping**, where there is oscillatory behaviour. The general solution is $x = e^{-\frac{k}{2}t}(A\sin\beta t + B\cos\beta t)$, where $\beta$ is the imaginary part of the roots to the auxiliary equation. The roots are given by $\frac{-k\pm\sqrt{k^2-4\omega^2}}{2}$, so the real part is $-\frac{k}{2}$ and the imaginary part is $\frac{\sqrt{k^2-4\omega^2}}{2}$.

#### Linear systems
Systems of **coupled differential equations** can describe model situations such as predator-prey models, where the rate of change of each independent variable is related to the other variable. For linear systems with first-order equations, these can be solved by eliminating variables to form a second-order differential equation in one variable and solving using standard methods.
