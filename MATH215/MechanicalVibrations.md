## Mechanical Vibrations


The goal is to study **Physical systems** that are modeled with $2^{nd}$ order ODEs, and classify different possible regimes.

Remember when we were solving $2^{nd}$ order ODEs and we simplified it into the form 

$$e^{\alpha t}\cdot C\cos\left(\omega t - \phi \right)?$$

We know that $C$ is the amplitude, $\omega$ is the natural frequency, and $\phi$ is the shift.

If you didn't take physics, $\frac{\omega}{2\pi}$ is the **usual frequency** (Number of cycles per second), and conversely, $\frac{2\pi}{\omega}$ is the **period** (seconds per cycle).

### Examples

We will see that we can describe several physical systems as $2^{nd}$ order ODEs:

- Mass spring systems (either horizontal or vertical)
- RLC circuits
- Pendulums

Let's try a vertical mass spring system. 

**Example 1.** A mass $m$ is attached to a spring with force constant $k$. The spring is hanging from a ceiling, with length $L$ at rest.

The mass is experiencing a force downwards by gravity, $mg$. The spring is pulling it upwards with a force $kz$, where $z$ is the length of the spring. Then we set $x=z-L$.

Now what ODEs satisfies $x(t)$?

From Newton's formula, we know that force = $mz''=-k(z-L)$. Now by replacing $z$ with $x$,

$$mx''+kx=0$$

and we know how to study this using our techniques from 2nd order ODEs.

Since we do not consider damping, this is an example of free undamped motion. We find that $\omega = \frac{k}{m}$ and $x(t) = C\cos(\omega t - \phi)$.

Now let's throw some numbers in. $m=10^{-2}kg$, and $L=2.45\cdot10^{-2}m$. At time $y=0$, we lift the mass up $2\cdot10^{-2}m$. Now we want to find the amplitude and phase shift.

Now we want to find $k$. At equilibrium, we know that the forces even out, so $kL=mg$ (since $L$ is the length at rest, which is equilibrium). Thus $k=\frac{mg}{L}$.