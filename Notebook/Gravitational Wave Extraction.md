## Gravitational Wave Extraction

At null infinity, $\psi_{4}$ is linked to the gravitational wave strain via

$$
\psi_{4}=\ddot{h}_{+}-i \ddot{h}_{\times}
$$

Then the strain is determined by:
$$
h=h_{+}-i h_{\times}=\int_{-\infty}^{t} d t^{\prime} \int_{-\infty}^{t^{\prime}} d t^{\prime \prime} \psi_{4}
$$

In practice, the integration is not performed from $t=-\infty$, but starts at a particular point, the beginning of the simulation. 

>  Note that the final result is not fully gauge-invariant and contains an unknown amount of systematic error. The reasons are two-fold: First, we did not choose a proper Bondi null tetrad on our extraction spheres, and, second, the extraction spheres have finite radius, thus are neglecting non-linear back-scattering effects of the gravitational field in the wave zone. However, since our coordinate frame asymptotically approaches the Minkowski spacetime, both errors can be minimized by performing extrapolation to future null infinity $\mathcal{J}^{+}$, using a set of extraction spheres at finite radii.

- FFI Integration
	- [[Reisswig2011#FFI Integration]]
- Extrapolation to null infinity
	- Extracting the signal at different radii and computing a fit to a polynomial in $\frac{1}{R}$.
	- Propagating the signal obtained at finite radius to null infinity with an analytic formula based on the results of perturbation theory of the Schwarzschild (or Kerr) spacetime.
	- Performing a characteristic evolution using as inner boundary conditions the metric and its derivatives on a timelike worldtube (CCE).

For all higher modes $\omega_{\ell m}=m \omega_{22} / 2$, once a particular $\omega_{0}$ has been found for the dominant $(\ell, m)=(2,2)$ mode. [arXiv:1006.1632]

FFI requires the choice of a cut-off frequency $f_{0},$ which ideally must be below the physical frequency components contained in the signal. For instance, for a typical binary neutron star inspiral signal, $f_{0}^{m}<m \Omega_{\text {orbital }} / 2 \pi,$ where $\Omega_{\text {orbital }}$ is the initial orbital frequency, and $m$ is the associated harmonic $m$-mode number.[arXiv:1212.1191]
