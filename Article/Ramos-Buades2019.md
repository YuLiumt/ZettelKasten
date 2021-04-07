## Simple procedures to reduce eccentricity of binary black hole simulations

- **Author**: Ramos-Buades A, [[Sascha Husa]], Pratten G. 
- **Summary**:
	- We present simple procedures to construct quasicircular initial data for numerical evolutions of binary black hole spacetimes.
	- Our method consists of using post-Newtonian (PN) theory in three ways:
		- First to provide an initial guess for the initial momenta at 3.5PN order that implies low residual eccentricity.
		- Second to measure the resulting eccentricity.
		- Third to calculate corrections to the momenta or initial separation that further reduce the eccentricity.
	- We discuss a robust fitting procedure to measure eccentricity from numerical simulations using the orbital frequency Ω, and derive from the quasi-Keplerian parametrization at 1PN order the correction factors for the tangential and radial momentum components required to reduce the measured eccentricity to zero.
	- We observe that the iterative procedure produces low eccentric simulations with eccentricities of the order $O\left(10^{-4}\right)$.
	- We have tested this procedure to measure the eccentricity of genuinely eccentric NR simulations, and we found accurate measurements up to eccentricities $e_{t}=0.1$.
		- For higher eccentricities the measurements are inaccurate.
- **Link**: [[BBH - Orbital Eccentricity]], [[EccRed]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019PhRvD..99b3003R) Ramos-Buades A, Husa S, Pratten G. Simple procedures to reduce eccentricity of binary black hole simulations. PRD, 2019, 99(2): 23003.

___

## Highlight

- Initial data for numerical relativity simulations of black hole binaries are typically constructed in a five-step procedure, which can be roughly summarized as follows:
	- One chooses the separation and the spin components.
	- One chooses the momenta or velocities of the black holes (BHs) such as to result in a low eccentricity. This step is usually guided by post-Newtonian (PN) approximations.
	- The constraint equations of general relativity are solved numerically for the chosen parameters, often using the approximation of conformal flatness.
	- The data are evolved numerically until the eccentricity can be estimated reliably from the corresponding oscillations in the separation, or orbital and gravitational wave frequency, as well as in other quantities.
	- A correction to the initial parameters is applied, and steps 2-5 (or 1-5) are applied until the eccentricity is deemed low enough for applications.
- In GR there is, however, no unique definition of eccentricity, and a specific quantity usually referred to as "eccentricity estimator" needs to be chosen, which reduces to the Newtonian concept of eccentricity in the Newtonian limit.
	- Determining eccentricity from the orbital frequency $\Omega$, one would, for example, typically choose the eccentricity estimator $$e_{\Omega}=\frac{\Omega(t)-\Omega(e=0)}{2 \Omega(e=0)}$$ which measures the time dependent oscillations in the orbital frequency relative to the case with vanishing eccentricity.
		- We compute the orbital frequency $\Omega$ from the position vector $\vec{r}$ in the center of mass frame, with $r=|\vec{r}|$, and its time derivative $\vec{v}$ as $$\Omega=|\vec{\Omega}|=\frac{|\vec{r} \times \vec{v}|}{r^{2}}$$ In the PN simulations $\vec{r}$ and $\vec{v}$ are computed from the motion of the point particles, whereas in the NR simulations they are computed from the coordinate positions of the punctures.
	- We choose an orbital quantity as our eccentricity estimator for simplicity and to save computational resources for numerical relativity simulations. Using wave quantities such as the strain or $\Psi_{4}$ requires longer numerical evolutions to allow the waves to travel to the extraction sphere.
	- Among quantities related to the orbital dynamics, the orbital frequency is convenient due to its weak gauge dependence, e.g., compared to the separation.

## Post-Newtonian Initial Data

-We describe the particles in the center of mass (CM) frame, so that the motion of the two point particles can be described by the motion of one effective particle. We choose our $z$ axis in the direction of the initial orbital angular momentum, and initially locate the particles on the $\mathrm{x}$ axis with $y=z=0$, and then locate $p_{\phi}=L_{z}$ with the standard definition of spherical polar coordinates. We define the tangential momentum as 
$$
p_{t}=\frac{p_{\phi}}{r}
$$ 

Using the standard relation between Cartesian and polar coordinates one can write $\left(p_{x}, p_{y}\right)$ in terms of $\left(p_{\phi}, p_{t}\right)$ as 

$$
\begin{array}{l} p_{x}=\frac{x p_{r}-y p_{t}}{\sqrt{x^{2}+y^{2}}}=p_{r} \cos \phi-p_{t} \sin \phi \\ p_{y}=\frac{x p_{t}+y p_{r}}{\sqrt{x^{2}+y^{2}}}=p_{r} \sin \phi+p_{t} \cos \phi \end{array}
$$

To compute the initial parameters we use the ADMTT Hamiltonian in the CM frame which is currently completely known up to 3.5PN order,

$$
H=H_{N S}+H_{S O}+H_{S S}+H_{S S S}
$$

One can compute the circular conditions for the orbit of the binary in the absence of radiation reaction:

$$
p_{r}=0, \quad\left(\frac{\partial H}{\partial r}\right)_{p_{r}=0}=0
$$

This equation gives a set of conditions to solve in PN order by order for $p_{\phi}(r)$. Once we have computed $p_{\phi}$, or equivalently $p_{t}(r),$ we can then compute

$$
\Omega=\left(\frac{\partial H}{\partial p_{\phi}}\right)_{p_{r}=0}
$$

and obtain an expression for the orbital frequency as a function of $r$.

For completeness, we can also obtain an expression for the ADM mass defined by

$$
M_{A D M}=M+H
$$

where $M$ is the total mass and $H$ is the 3.5PN Hamiltonian in ADMTT gauge.

The procedure to obtain a postcircular expression for the radial momentum can be summarized in the following algorithm:

1. Compute the circular expression for $p_{t}(r)$.
2. Use the expression for $p_{t}(r)$ and $p_{r}=0$ to compute $d H_{\mathrm{circ}} / d r$.
3. Combine $d H_{\mathrm{circ}} / d r$ with the gravitational wave flux for the quasicircular orbits, $d E_{\mathrm{GW}} / d t$, to obtain $d r / d t$.
4. Use Hamilton's equations to compute $d r / d t=\partial H / \partial p_{r}$. Taylor expand at first order in $p_{r}$ around $p_{r}=0$ of the right-hand side and isolate $p_{r}$ as a function of $d r / d t$.
5. From step 4 compute an expression of $p_{r}$ using the value of $d r / d t$ calculated in step 3 .