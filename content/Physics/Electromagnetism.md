A **magnetic field** is a region of space where a magnetic force acts. **Magnetic flux lines** run from an N-pole to an S-pole and form a continuous loop (in solenoids). The **magnetic flux density**, $B$, is related to how densely packed magnetic flux lines, and is a measure of the strength of the magnetic field. It is a vector quantity. When magnets interact, they tend to move such that flux lines shorten and straighten.

**Magnetic flux**, $\Phi$, can be thought of loosely as the 'total amount of magnetic field through a surface'. Magnetic flux is related to flux density by:
$$
\Phi = BA
$$
Where:
- $\Phi$ is flux in weber ($\textrm{Wb}$). One weber is the amount of flux needed to change per second to induce an e.m.f of 1 volt.
- $B$ is magnetic flux density in weber per square metre ($\textrm{Wb\,m}^{-2}$)
- $A$ is the area perpendicular to lines of flux, in square meters ($\textrm{m}^2$).

#### Induction
**Induction** is where a changing magnetic flux in a circuit causes a electromotive force to be induced in the circuit. In real circuits, coils with many turns are used, which is why flux linkage is used. **Flux linkage**, $N\Phi$ (measured in weber turns), is equal to the flux multiplied by the number of turns in the coil.

The induced e.m.f in a coil is given by:
$$
\varepsilon = -\frac{\Delta(N\Phi)}{\Delta t} = -\frac{\textrm{d}(N\Phi)}{\textrm{d} t}
$$
This is known as **Faraday's Law of electromagnetic induction**. The **negative sign** is a result of **Lenz's Law**, which states that the induced e.m.f. in a circuit as a result of a changing magnetic field creates a current with a direction that creates a magnetic field that opposes the original change in the magnetic field.

#### Electromagnetic circuits
In a **magnetic circuit**, the flux lines form a closed loop. Similar to conductance in electrical circuits, magnetic circuits have **permeance**; higher permeance means more flux. Thus, magnetic circuits are often made from ferromagnetic materials with a **high magnetic permeability**, for example iron. The magnetic equivalent of p.d. is **current-turns** $NI$ (equal to the current in a coil multiplied by the number of turns), while the magnetic equivalent of electric current is flux $\Phi$. As in a electrical circuit, higher current-turns will cause a higher flux.

For a electric circuit, the conductance is $G = \frac{\sigma A}{l}$, where $\sigma$ is the conductivity. Similarly, for magnetic circuit, the **permeance is maximised** by **maximizing surface area** and **minimising the length of flux lines**. An electric circuit has a large current when there is a high conductance, so a magnetic circuit has a large flux when there is a high permeance. Iron has a magnetic permeability 200,000 times that of air, so flux lines don't 'leak out' of iron cores. If there is a gap in the magnetic circuit, the permeance will be greatly reduced because of air's low permeability.

###### Transformers
**Transformers** are electromagnetic machines that change the potential difference of electrical power. In a transformer, an alternating p.d. in the primary coil creates a changing flux in the core. This changing flux links with the secondary coil to induce a alternating p.d. in the secondary.

In the primary coil, the changing flux in the core creates a magnetic field that induces a current with a magnetic field that opposes the original alternating p.d., by Lenz's Law. This is called **self-inductance**.

###### Deriving the transformer equation
By Faraday's Law, the e.m.f. from self-inductance is given by $-\frac{\textrm{d}(N_1\Phi)}{\textrm{d} t}$, where $N_1$ is the number of turns on the primary coil. The total p.d. across the primary coil is equal to the sum of supply p.d. $V_1$ and the induced e.m.f.. By using Ohm's law on the primary coil, we get:
$$
V_p -\frac{\textrm{d}(N_1\Phi)}{\textrm{d} t} = IR
$$
For an ideal transformer, $R$ is negligibly small (as the coil is just a wire, which has a very low resistance). Thus, $IR \approx 0$, giving:
$$
V_p = \frac{\textrm{d}(N_1\Phi)}{\textrm{d} t} = N_1\frac{\textrm{d}\Phi}{\textrm{d} t} \implies \frac{\textrm{d}\Phi}{\textrm{d} t} = \frac{V_1}{N_1}
$$
This equation means that, loosely, all the p.d. from the supply across the primary coil is converted into magnetic flux. In the magnetic circuit, ignoring the negligibly small leakage of flux into the air, the flux in both the primary and secondary coils is equal (because of the high permeance of the circuit). Thus, if the flux is equal at all times, the change in flux in the primary and secondary coils is also equal:
$$
\begin{split}
&V_2 = -\frac{\textrm{d}(N_2\Phi)}{\textrm{d} t} = -N_2 \frac{\textrm{d}\Phi}{\textrm{d} t} \\
\implies &V_2 = -N_2 \frac{V_1}{N_1} \\
\implies &\frac{V_2}{V_1} = \frac{N_2}{N_1}
\end{split}
$$
Thus giving the familiar transformer equations below, where the negative sign indicates that the alternating p.d. in the secondary coil is $180\degree$ **out of phase** from the primary.
$$
\frac{V_1}{V_2} = -\frac{N_1}{N_2} \quad\quad \frac{V_1}{N_1} = -\frac{V_2}{N_2}
$$
The ratio $\frac{N_1}{N_2}$ is called the **turns ratio**. If $N_1 \gt N_2$ then the transformer is a **step-down transformer**, with $V_2 < V_1$. If $N_1 \lt N_2$, then the transformer is a **step-up** transformer, with $V_2 \gt V_1$. 

An **ideal transformer** is perfectly efficient, thus the total power input and output are equal:
$$
V_1I_1 = V_2I_2 \quad\quad \frac{I_2}{I_1} = \frac{N_1}{N_2}
$$

###### Eddy currents
The changing flux within the core of a transformer induces currents in the transformer core itself, called **eddy currents**. By Lenz's law, these currents create magnetic flux that opposes the flux created by the primary coil. This wastes energy and reduces the transformer's efficiency, with the wasted energy dissipated as heat. Eddy currents can be reduced by making the core from a stack of **laminations**, separated by electrically insulating layers.

#### Generators
A **generator** uses motion to create a changing magnetic field, to induce an e.m.f For a coil moving at constant speeds perpendicular to a uniform magnetic field, the induced e.m.f. is given by:
$$
\varepsilon = BLv
$$
For a coil with angle $\theta$ between its normal and the direction of magnetic flux lines, the flux through it is given by $BA\cos\theta$. **Generators** constantly rotate the coil to cause a change in flux. Let $\theta = \omega t$, where $\omega$ is the angular velocity of the coil. The flux is thus $BA\cos(\omega t)$, while the flux linkage is $BAN\cos(\omega t)$.

By differentiating the flux linkage, we get that e.m.f. is given by:
$$
-BAN\omega\sin(\omega t)
$$
Another way to use Faraday's Law for moving coils is that the **induced e.m.f. is equal to the rate at which flux lines are cut**. Generators are designed to have as large a changing flux as possible. This can be achieved by creating a stronger magnetic field, by increasing the permeance of the magnetic circuit.

#### Electromagnetic forces
When a current-carrying wire is placed in a magnetic field, the wire creates a magnetic field which adds vectorially to the existing field. This causes an asymmetric field, where the **flux lines try to contract and straighten**, producing a force (catapult effect). For a straight current-carrying wire perpendicular to a uniform magnetic field, the force is given by:
$$
F = BIL
$$
Where:
- $B$ is magnetic flux density in tesla ($\textrm{T}$). One tesla is the flux density needed to create one newton of force with one metre of wire carrying one ampere. One tesla is also equal to one weber per square metre ($\textrm{Wb\,m}^{-2}$).
- $I$ is current in amperes ($\textrm{A}$).
- $L$ is length of wire perpendicular to the magnetic field, in metres ($\textrm{m}$).

###### Motors
A **motor** uses an electric current to produce a magnetic field that interacts with a permanent magnetic field to cause a force and motion. A motor contains a coil that produces an upwards force on one side, and a downwards force on the other side, causing a net torque and thus rotation.

Motors and generators are the same thing. If you use a generator to deliver current to a load, there will be resistance from the generator acting as a motor. When a motor spins, it generates a **back-e.m.f** that opposes motion by Lenz's Law, limiting the speed of the motor.
