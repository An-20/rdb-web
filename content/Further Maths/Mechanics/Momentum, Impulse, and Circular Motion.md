#### Linear momentum and impulse
**(Linear) momentum** is the product of mass ($\text{kg}$) and velocity ($\text{ms}^{-1}$), and has units $\text{kg\,m\,s}^{-1}$.
$$
\text{momentum} = \text{mass} \times \text{velocity} = mv
$$

**Impulse** is the product of force ($\text{N}$) and time ($\text{s}$), and has units $\text{N\,s}$.
$$
\text{impulse} = I = Ft
$$

The **impulse-momentum principle** states the impulse imparted by a force is equal to the change in momentum:
$$
\text{impulse} = I = mv - mu
$$

Force and velocity are both vector quantities, so momentum and impulse are also vector quantities. The direction should be show correctly using the appropriate sign.

If there are no external impulses, then the **law of conservation of momentum** applies:
$$
m_{1}u_{1} + m_{2}u_{2} = m_{1}v_{1} + m_{2}v_{2}
$$
#### Restitution
Collisions range from perfectly elastic to perfectly inelastic. In a **perfectly elastic** collision. no kinetic energy is lost from the system. In a **perfectly inelastic** collision, the two objects coalesce.

###### Collisions between spheres
For two smooth spheres, Newton's Experimental Law states that:
$$
\frac{\text{speed of separation}}{\text{speed of approach}} = \frac{v_{1}-v_{2}}{u_1-u_{2}} = -e
$$
Where $e$ is the **coefficient of restitution**. For a perfectly elastic collision, $e=1$, while for a perfectly inelastic[^1] collision, $e=0$. For this course, $0 \le e \le 1$.

When modelling collisions between spheres, the assumptions generally are:
- The spheres are smooth
- The impulse during the collision acts along the line of sphere centres
- None of the spheres are spinning

###### Collisions between a sphere and a fixed plane
When a sphere collides with a fixed plane, momentum is not conserved because the wall does not usually move. Newton's Experimental Law still holds, so by considering $u_{2} = v_{2} = 0$:
$$
v = -eu
$$


**Footnotes**
[^1]: **Footnote on perfectly inelastic collisions**
	For this course, 'inelastic' is taken to mean 'perfectly inelastic', that is $e=0$ (this is mentioned in the specification).
