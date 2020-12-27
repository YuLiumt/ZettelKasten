## Conservation laws

Many physical systems can be described by conservation laws. Such laws are also called "conservative laws". This means that some quantities are not changed by physical processes happening inside the system, which is why these quantities are called "conserved quantities".

In our simulations, one example of such a conserved quantity is the rest-mass. The conservation of rest-mass is particularly important in shocks, because only conserved rest-mass and momentum can guarantee for correct shock speeds. The conservation is ensured by the Euler equations. Numerical simulations, however, always make errors. These errors can accumulate and destroy the conservation.

A conservative scheme can be implemented for any system in balance law form

$$
\partial_{t} \mathbf{u}+\partial_{i} \mathbf{f}^{(i)}(\mathbf{u})=\mathbf{s}(\mathbf{u})
$$
where $\mathbf{f}^{(i)}(\mathbf{u})$ and $\mathbf{s}(\mathbf{u})$ are the flux vectors and the source terms, respectively.