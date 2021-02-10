## Error-analysis and comparison to analytical models of numerical waveforms produced by the NRAR Collaboration

- **Author**: NRAR Collaboration
- **Summary**:
	- 
- **Link**: [[Numerical Relativity]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2013CQGra..31b5012H) NRAR Collaboration. Error-analysis and comparison to analytical models of numerical waveforms produced by the NRAR Collaboration. Classical and Quantum Gravity, 2013, 31(2): 25012.

___

## Highlight

- The Numerical-Relativity–Analytical-Relativity (NRAR) collaboration is a joint effort between members of the numerical relativity, analytical relativity and gravitational-wave data analysis communities.

## Error analysis

We identify and provide estimates for three distinct sources of error in the numerical relativity waveforms:

- Finite numerical resolution: Finite resolution error results from the conversion of the continuum Einstein equations into a discrete form suitable for numerical solution.
	- For finite-difference codes, the error is estimated using Richardson extrapolation assuming polynomial convergence of the solution at order r. A quantity $q$ which converges at order $r$ with the grid spacing $\delta$ satisfies $$q(\delta)=q_{0}+C \delta^{r}+O\left(\delta^{r+1}\right)$$ where $q_{0}$ (the continuum solution) and $C$ are unknown and independent of $\delta$.
	- Taking two numerical solutions with different grid spacings $\delta$, the resulting simultaneous equations are solved for $q_{0}$ and $C$, and the error in $q(\delta_{2})$ due to truncation of the finite difference approximation is $$\sigma_{\mathrm{T}}(q) \equiv q\left(\delta_{2}\right)-q_{0}=\frac{q\left(\delta_{2}\right)-q\left(\delta_{1}\right)}{1-\left(\delta_{1} / \delta_{2}\right)^{r}}+O\left(\delta^{r+1}\right)$$
- Finite radius error: Finite radius error results from the computation of gravitational radiation at a finite distance from the source instead of computing it at future null infinity.
	- Using a lower extrapolation order leads to a larger error, but using too high an extrapolation order leads to unwanted overfitting of a model with a large number of degrees of freedom in comparison to the number of data points.
	- The error due to finite-radius effects is estimated by comparing the extrapolant at different orders. The error in the order $p$ extrapolant, $\mathcal{R}_{p}(q)$, is estimated as $$\sigma_{\mathrm{R}}(q) \equiv \min \left(\left|\mathcal{R}_{p}(q)-\mathcal{R}_{p+1}(q)\right|+\left|\mathcal{R}_{p+1}(q)-\mathcal{R}_{p+2}(q)\right|,\left|\mathcal{R}_{p}(q)-\mathcal{R}_{0}(q)\right|\right)$$ where $q \in\{A, \phi\}$. There are two contributions to this error estimate. If extrapolation works well, i.e. different extrapolation orders do not change the results significantly, then we trust the extrapolation, and take the variation with extrapolation order as indicative of the error.
- Strain error:  results from the computation of $h$ from $\Psi_{4}$.
	- We use the difference as an indication of the effects of the FFI error, and quote phase and relative amplitude errors measured in $\Psi_{4}$ here as if they were errors on the resulting $h$, $$\begin{array}{l} \sigma_{\mathrm{S}}(\phi) \equiv \arg \left(\Psi_{4}\right)-\arg (\ddot{h}) \\ \frac{\sigma_{\mathrm{S}}(A)}{A} \equiv \frac{\left|\Psi_{4}\right|-|\ddot{h}|}{|\ddot{h}|} \end{array}$$ 

The three sources of error—truncation, finite radius and fixed-frequency integration—each contribute to the total error in the waveform. Each one is computed individually without and with alignment. We add them in quadrature to obtain our final error estimates on the amplitude and phase of the strain waveform $h$,

$$
\sigma(q)=\sqrt{\sigma_{\mathrm{T}}(q)^{2}+\sigma_{\mathrm{R}}(q)^{2}+\sigma_{\mathrm{S}}(q)^{2}}
$$
where $q \in\{A, \phi\}$.