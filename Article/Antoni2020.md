## First survey of spinning eccentric black hole mergers: Numerical relativity simulations, hybrid waveforms, and parameter estimation

- **Author**: Ramos-Buades A, Husa S, Pratten G, Estellés H, Garcı́a-Quirós C, Mateu-Lucena M, Colleoni M, Jaume R.
- **Summary**:
	- A new numerical relativity dataset of spinning but nonprecessing binary black holes on eccentric orbits.
		- We construct eccentric hybrid waveforms that connect the numerical relativity data to a post-Newtonian description for the inspiral.
- **Link**: [[BBH - Orbital Eccentricity]], [[Waveform Templates]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020PhRvD.101h3015R) Ramos-Buades A, Husa S, Pratten G, Estellés H, Garcı́a-Quirós C, Mateu-Lucena M, Colleoni M, Jaume R. First survey of spinning eccentric black hole mergers: Numerical relativity simulations, hybrid waveforms, and parameter estimation. PRD, 2020, 101(8): 83015.

___

## Highlight

- The modeling of the gravitational waveforms from eccentric black hole binaries is complicated by the addition of a new timescale to the binary problem, the periastron precession. This new timescale induces oscillations in the waveforms due to the asymmetric emission of gravitational radiation between the apastron and periastron passages.
- We present a catalog of 60 eccentric NR simulations performed with the nonpublic BAM code and the open-source ET code with the multipatch Llama infrastructure.
	![[Pasted image 20210126103245.png]]
	- We have also added 20 public eccentric SXS simulations.
- To produce initial data for a desired eccentricity we perturb the initial tangential momentum of the black holes by a factor $\lambda_{t}$ from its quasicircular value. 
	- The expression for $\lambda_{t}$ in terms of the eccentricity at 1PN order is $$\lambda_{t}\left(r, e_{0}, \eta, \text { sign }\right)=1+\frac{e_{0}}{2} \times \operatorname{sign} \times\left[1-\frac{1}{r}(\eta+2)\right]$$ where $\eta$ is the symmetric mass ratio, $r$ is the orbital separation and $\operatorname{sign}=\pm 1$ depends on the initial phase of the eccentricity estimator.
	- We compute the correction factor applied to the momentum as the mean between the inverse of the expression with the plus sign plus the expression with the minus sign, $$\begin{aligned} \bar{\lambda}_{t}^{0}\left(r, e_{0}, \eta\right) &=\frac{1}{2}\left[\lambda_{t}\left(r, e_{0}, \eta,+1\right)^{-1}+\lambda_{t}\left(r, e_{0}, \eta,-1\right)\right] \\ &=\frac{8 r^{2}-e_{0}^{2}(\eta-r+2)^{2}}{4 r\left(e_{0}(-\eta+r-2)+2 r\right)} \end{aligned}$$
	- Above equations was derived assuming a nonspinning binary in the low eccentric limit.
	- The higher the initial eccentricity of the simulation, the longer the initial separation has to be to avoid the immediate plunge of the binary due to the strong interactions at the periastron.