## Nonspinning binary black hole merger scenario revisited

- **Author**: [[James Healy]], [[Carlos Lousto]], Zlochower Y.
- **Summary**:
	- We present the results of 14 simulations of nonspinning black hole binaries with mass ratios $q=m_{1} / m_{2}$ in the range $1 / 100 \leq q \leq 1$. 
		- For each of these simulations we perform three runs at increasing resolution to assess the finite difference errors and to extrapolate the results to infinite resolution.
- **Link**: [[Binary Black Hole]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2017PhRvD..96b4031H) Healy J, Lousto C O, Zlochower Y. Nonspinning binary black hole merger scenario revisited. PRD, 2017, 96(2): 24031.

___

## Highlight

- Our code uses the Einstein Toolkit / Cactus / Carpet infrastructure.
	- To compute the initial low eccentricity orbital parameters we use the post-Newtonian techniques.
	- Note that once we have the horizon spin, we can calculate the horizon mass via the Christodoulou formula $m_{H}=\sqrt{m_{\mathrm{irr}}^{2}+S_{H}^{2} /\left(4 m_{\mathrm{irr}}^{2}\right)},$ where $m_{\mathrm{irr}}=\sqrt{A /(16 \pi)}$, $A$ is the surface area of the horizon, and $S_{H}$ is the spin angular momentum of the BH (in units of $M^{2}$). 
- For the recoil velocity and peak luminosity, the error is calculated from the finite resolution and finite observer location errors.
	- To estimate the finite resolution error we determine compare the results of the highest resolution with those obtained by a Richardson extrapolation of all resolutions.
	- To estimate the finite observer location error, we take the difference between the largest and smallest radii.
		- Calculating the error in this way overestimates the error, since as $r_{o b s} \rightarrow \infty$ the difference between the values at successive observers decreases.
	- Even with this conservative calculation of the observer location error, the finite resolution error is typically the dominant error source, but we include both in the total error estimate by adding both sources in quadrature.