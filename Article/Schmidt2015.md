## Towards models of gravitational waveforms from generic binaries II: Modelling precession effects with a single effective precession parameter

- **Author**: Schmidt P, Ohme F, Hannam M.
- **Summary**:
	- We introduce a single effective precession spin parameter, $\chi_{p}$, which is defined from the spin components that lie in the orbital plane at some (arbitrary) instant during the inspiral.
	- If we can accurately measure the parallel spin components and $\chi_{p}$, then we will be able to accurately measure the spin magnitude of the larger black hole.
	- The present study has been limited to inspiral waveforms only, and we have also neglected the effect of higher PN order spin terms, which may weaken the $\chi_{p}$ degeneracy that we have identified.
- **Link**: [[Gravitational Wave]], [[Binary Black Hole]], [[BBH - Orbital Precession]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2015PhRvD..91b4043S) Schmidt P, Ohme F, Hannam M. Towards models of gravitational waveforms from generic binaries: II. Modelling precession effects with a single effective precession parameter. PRD, 2015, 91(2): 24043.

___

## Highlight

- In the most general cases, the individual spin angular momenta have arbitrary orientations, and any misalignment between the orbital angular momentum and the spins causes the orbital plane as well as the spin vectors to precess.
	- The waveform from the inspiral of a precessing binary can be approximated by an underlying non-precessing-binary waveform that has been "twisted up" by the precessional motion of the orbital plane.
	- The non-precessing waveform is characterised by the individual masses and the components of the black hole spins parallel to the orbital angular momentum, which remain roughly constant throughout the inspiral.
- An open problem in modelling generic binaries is the need for NR simulations across a seven-dimensional parameter space (mass ratio, plus the vector components of each black hole's spin).
	- NR simulations are computationally expensive, and even a coarse sampling of four points in each direction of the parameter space would require $4^{7} \sim O\left(10^{5}\right)$ simulations.
		- The total mass of the binary sets the overall scale in General Relativity and therefore need not be explicitly included in a waveform model.
	- One way to make this problem tractable is to identify the physical parameters (or combinations of them) that most strongly affect the GW signal.
		- This approach has already been used in some models of spinning, non-precessing binaries. This can be parameterized by a weighted sum of the two spins.
		- Our goal in this work is to identify a complementary spin parameter for precession and reduce the remaining four dimensions.
	- This approach will not only provide us with a smaller subspace over which to perform NR simulations, but will also indicate those physical parameters that can most accurately be measured in future GW observations.
- The direction of the total angular momentum $\vec{J}=\vec{L}+\vec{S}_{1}+\vec{S}_{2}$ is approximately fixed.
	![[Pasted image 20210110192751.png|400]]
	- If $\hat{N}$ is the line-of-sight direction of a distant inertial observer (detector), then we can define $\theta=\angle(\hat{J}, \hat{N})$ as the inclination of the binary.
		- The strength of the modulations depends strongly on the relative orientation of the binary to the observer, i.e., $\theta$. Even strongly-precessing systems can show only mild modulations if the the observer is aligned with $\hat{J}_{0}$, i.e., $\theta=0$.
			![[Pasted image 20210110202400.png]]
	- In the following, we adopt a Cartesian coordinate system attached to the binary such that at the initial time $\hat{J}_{0} \equiv \hat{z}$, which we refer to as the $J_{0}$-aligned source frame. Therein, we define the instantaneous direction of the orbital angular momentum, $\hat{L}(t)$, by the two polar angles $(\imath(t), \alpha(t))$. The azimuth angle is directly related to the precession frequency $\omega_{p}(t)=\frac{d \alpha(t)}{d t}$.
- Precession occurs due to spin-orbit and spin-spin couplings.
	- In PN theory, the evolution of $L$ and $S_{i}$ can be described through 2.5PN order.
		- The leading-order effect occurs at 1.5-PN order (spin-orbit coupling).
		- The dominant spin-spin coupling term appears at 2PN order.
- For a precessing binary with mass ratio $q=3$, $\vec{\chi}_{1}=(0.4,-0.2,0.3)$ and $\vec{\chi}_{2}=(0.75,0.4,−0.1)$.
	- The parallel spin components each oscillate around a mean value, which is close to the initial values of $S_{1 \|}=0.01875$ and $S_{2 \|}=-0.05625$.
		![[Pasted image 20210110204018.png]]
	- Note that the individual total spin magnitudes $S_{1}$ are conserved, and the observed oscillations in the parallel spin magnitudes are compensated by changes in the in-plane spin magnitudes at each moment in time.
		![[Pasted image 20210110204234.png]]
	- To describe the precession, we require additional information from the spin components that lie in the orbital plane orthogonal to $\hat{L}$. It is therefore convenient to decompose the spin vectors with respect to $\hat{L}$ into their parallel and orthogonal vector components such that each spin vector $\vec{S}_{i}=\vec{S}_{i \|}+\vec{S}_{i \perp}$.
	- It is possible to faithfully approximate the precession in a generic binary system by combining these four in-plane spin components $\vec{S}_{1 \perp}$ and $\vec{S}_{2 \perp}$ into only one additional spin parameter, a complementary effective precession spin, $\chi_{p}$.
- The results show very strong evidence in favour of the reduced parameterisation to capture the dominant precession effects.
		![[Pasted image 20210110213015.png]]
	- Our approach is to compare a large number of generic inspiral waveforms at three mass ratios, $q=1,3,10$, to a family of corresponding reduced-parameter waveforms where the initial in-plane spin components are replaced by $\chi_{p}$ applied to the larger black hole.
		$$
	\begin{array}{l}
	\left(\chi_{1 x}, \chi_{1 y}, \chi_{1 z}\right) \mapsto\left(0,0, \chi_{1 z}\right) \\
	\left(\chi_{2 x}, \chi_{2 y}, \chi_{2 z}\right) \mapsto\left(\chi_{p}, 0, \chi_{2 z}\right)
	\end{array}
	$$
	- For mass ratios $q=1,3$ we find that less than $2 \%$ of all matches are below $0.965$, respectively.
	

## Effective precession spin

Consider the leading-order PN precession equation:

$$
\begin{aligned}
\dot{\vec{L}} &=\frac{L}{r^{3}}\left[\left(2+\frac{3 q}{2}\right) \vec{S}_{1}+\left(2+\frac{3}{2 q}\right) \vec{S}_{2}\right] \times \hat{L} \\
& \equiv \frac{L}{r^{3}}\left[A_{1} \vec{S}_{1 \perp}+A_{2} \vec{S}_{2 \perp}\right] \times \hat{L}
\end{aligned} \tag{1}
$$
where $A_{1}=2+3 q / 2$ and $A_{2}=2+3 /(2 q)$, and $r$ denotes the separation. We see immediately that the in-plane spins $\vec{S}_{i \perp}$ drive the evolution of $L$. At leading order these suggest that the in-plane spins $\vec{S}_{i \perp}$ rotate within the orbital plane, but with different rotational velocities, i.e., they have different precession rates around $\hat{L}$.

At some times during the inspiral, the two in-plane spin vectors will be parallel, and will add together in Eq. (1). At other times, the in-plane spin vectors will point in opposite directions, and their contributions will be minimised. Over many precession cycles, the overall contribution to Eq. (1) can be approximated by the average magnitude of these two contributions:

$$
\begin{aligned}
S_{p} &:=\frac{1}{2}\left(A_{1} S_{1 \perp}+A_{2} S_{2 \perp}+\left|A_{1} S_{1 \perp}-A_{2} S_{2 \perp}\right|\right) \\
& \equiv \max \left(A_{1} S_{1 \perp}, A_{2} S_{2 \perp}\right)
\end{aligned} \tag{2}
$$
We see that $S_{p}$ is directly related to the in-plane spin angular momentum of one of the black holes. In most configurations this is the in-plane spin of the larger black hole. This indicates that the influence of the spin-spin terms (by placing all of the spin on one black hole) is ignored.

We now use $S_{p}$ to approximate all four in-plane spin parameters. Motivated by the fact that the in-plane spin of the smaller black hole becomes more and more negligible with increasing mass ratio, we assign the precession spin completely to the larger black hole, and define the dimensionless precession spin parameter as

$$
\chi_{p}:=\frac{S_{p}}{A_{2} m_{2}^{2}} \tag{3}
$$
For a small subset of configurations $\chi_{p}$ does not respect the Kerr limit of $\chi_{i} \leq 1$.

Having chosen $\chi_{p}$ to be the approximate mean of the leading-order term in the PN precession equation, we expect to see a similar evolution of the orbital plane in a system where $\chi_{p}$ is used instead of $S_{1 \perp}$ and $S_{2 \perp}$.