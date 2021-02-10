## Numerical Relativity

For all but the simplest systems, analytic solutions for the evolution of such systems do not exist. Hence the task of solving Einstein's equations must be performed numerically on a computer.

## Initial Value Problem

- [[NR - Initial Data]]
- [[NR - Evolution]]
- [[NR - Boundary conditions]]

## Equations

- Einstein Equations
	$$
  R_{\mu \nu}-\frac{1}{2} g_{\mu \nu} R=8 \pi G T_{\mu \nu}
  $$
- Conservation of energy momentum
	$$
  \nabla_{\mu} T^{\mu \nu}=0
  $$
- Conservation of baryon density
	$$
  \nabla_{\mu}\left(\rho u^{\mu}\right)=0
  $$
- Equation of state
	$$
  p=p(\rho, \epsilon)
  $$


## 3+1 Decomposition

## History

The first fully general relativistic (GR) simulations of merging NS-NS binaries were reported in 1999. However, systems containing BHs proved much more difficult to evolve numerically until 2005.

- A major step forward occurred 2005, when three independent groups developed two different techniques, the generalised harmonic [[NR - Gauge conditions]] formalism and the socalled [[Moving Puncture]] method, to evolve vacuum spacetimes containing [[Black Hole]] without encountering numerical instabilities that mark the end of a numerical simulation.

## Source

- [[Binary Neutron Star]]
- [[Binary Black Hole]]
	- Because LIGO is only sensitive to the last few orbits of stellar-mass BHB mergers, and because of the large computational resources needed to produce these simulations, BHB simulations start at relatively small initial separations in astrophysical terms.
	- On the other hand, by the time a BHB enters the LIGO sensitivity band we expect that the eccentricity will be very small because any eccentricity of astrophysical origin would have been most likely radiated away well before the late-inspiral.
- [[Core-Collapse Supernovae]]

## Relationship Graph

- Gravitational wave observations have been a key motivation driving numerical relativity.
- One of the most significant goals of numerical relativity is to compute accurate gravitational waveforms. [[Waveform Templates]]
- Only rather exotic phenomena involve sufficiently strong spacetime curvature to require numerical relativity. [[Dimensionless Compaction]]

## Catalog

- [[SXS Catalog]]
- [[GT Catalog]]
- [[RIT Catalog]]
- [[CoRe]]
- Illinois Data Bank (IDB)
- Federated Research Data Repository (FRDR)

## Tools

- [[Einstein Toolkit]]
- [[Spectral Einstein Code]]