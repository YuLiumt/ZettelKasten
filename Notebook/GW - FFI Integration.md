## GW - FFI Integration

The output of the numerical simulation is a discretely sampled time series of finite duration, incorporating some component of unresolved frequencies due to numerical error. The latter aspect can lead to an uncontrollable non-linear drift if the integration is performed in the time domain. An alternative is to perform the integration in the frequency domain. In this case, however, the finite duration of the numerical signal becomes an issue, as artificial low-frequency components of the infinite spectrum of a localized-in-time function dominate the integral. An appropriately chosen band-pass filter improves the situation greatly. Unfortunately, this can require some complicated adjustment of parameters, which is difficult to systematize.


>  Note that the final result is not fully gauge-invariant and contains an unknown amount of systematic error. The reasons are two-fold: First, we did not choose a proper Bondi null tetrad on our extraction spheres, and, second, the extraction spheres have finite radius, thus are neglecting non-linear back-scattering effects of the gravitational field in the wave zone. However, since our coordinate frame asymptotically approaches the Minkowski spacetime, both errors can be minimized by performing extrapolation to future null infinity $\mathcal{J}^{+}$, using a set of extraction spheres at finite radii.



For all higher modes $\omega_{\ell m}=m \omega_{22} / 2$, once a particular $\omega_{0}$ has been found for the dominant $(\ell, m)=(2,2)$ mode. [arXiv:1006.1632]

FFI requires the choice of a cut-off frequency $f_{0},$ which ideally must be below the physical frequency components contained in the signal. For instance, for a typical binary neutron star inspiral signal, $f_{0}^{m}<m \Omega_{\text {orbital }} / 2 \pi,$ where $\Omega_{\text {orbital }}$ is the initial orbital frequency, and $m$ is the associated harmonic $m$-mode number.[arXiv:1212.1191]


Note that the smaller integration radii are not very far from the binary system, and so possibly in a region where is not strictly valid. However, the larger integration radii are in regions of the grid that do not have very good resolution and so numerical error (mostly dissipation) tends to reduce the amplitude of the waves with distance from the source.


- [[Reisswig2011#FFI Integration]]