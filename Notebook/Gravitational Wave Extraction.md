## Gravitational Wave Extraction

In constructing templates, the natural observable is the one which is also measured by the detectors, namely the gravitational wave strain $h \equiv h_{+}-i h_{\times}$, decomposed into $+$ and $\times$ polarizations in the transverse-traceless gauge. However, this is typically not the quantity which is directly computed in numerical simulations.



At null infinity, $\psi_{4}$ is linked to the gravitational wave strain via

$$
\psi_{4}=\ddot{h}_{+}-i \ddot{h}_{\times}
$$

Then the strain is determined by:
$$
h=h_{+}-i h_{\times}=\int_{-\infty}^{t} d t^{\prime} \int_{-\infty}^{t^{\prime}} d t^{\prime \prime} \psi_{4}
$$

In practice, the integration is not performed from $t=-\infty$, but starts at a particular point, the beginning of the simulation. 

## Numerical integration

Transforming the measured variables to the strain involves some numerical subtleties.

- Time-domain integration
- Frequency-domain integration
	- [[GW - FFI Integration]] - fixed frequency integration
	- High-pass filters and window functions

## Extrapolation to null infinity

A potential source of the problem may come from the fact that $\psi_{4}$ is typically extracted at a finite distance from the gravitating source. The strain $h$, however, is related to $\psi_{4}$ only at an infinite distance from the source hence introducing a systematic "finite-radius" error.

By eliminating these systematic errors, one would

- Extracting the signal at different radii and computing a fit to a polynomial in $\frac{1}{R}$.
- Propagating the signal obtained at finite radius to null infinity with an analytic formula based on the results of perturbation theory of the Schwarzschild (or Kerr) spacetime.
- Performing a characteristic evolution using as inner boundary conditions the metric and its derivatives on a timelike worldtube (CCE).




## Relationship Graph

- To estimate the gravitational waves emitted by the binary we use the [[Newman-Penrose scalar]] $\Psi_{4}$.