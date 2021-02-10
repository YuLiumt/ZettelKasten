## Exploring the Small Mass Ratio Binary Black Hole Merger via Zeno's Dichotomy Approach

- **Author**: Lousto C O, Healy J.
- **Summary**:
	- We perform a sequence of binary black hole simulations with increasingly small mass ratios, reaching to a 128:1 binary that displays 13 orbits before merger.
		- Roughly a linear computational resources scaling with $1/q$ is observed.
- **Link**: [[Intermediate Massive Black Hole]], [[Numerical Relativity]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020PhRvL.125s1102L) Lousto C O, Healy J. Exploring the Small Mass Ratio Binary Black Hole Merger via Zeno’s Dichotomy Approach. PRL, 2020, 125(19): 191102.

___

## Highlight

- For the $q=1 / 15$, the detail of the convergence of the waveform phase and amplitude with global numerical resolution is shown in Fig. 1 displaying an eighth order convergence rate.
	![[Pasted image 20210204154830.png]]
	- The high convergence of these results allow us to use the medium of the resolutions, n100, as the reference grid to perform a set of smaller $q$ simulations, each time halving the mass ratio and adding a new refinement level around the smaller hole (12, 13, 14, 15 levels for $q =1/15$, $1/32$, $1/64$, $1/128$, respectively).
		![[Pasted image 20210204155609.png]]
	- An important test of accuracy of our simulations is to compare the final properties versus the predictions of the formulas obtained in Ref. [[Healy2017a]].
		![[Pasted image 20210204160022.png]]
	- In light of these good results, we can now use the current data to generate a new fit of the nonspinning binary remnant and merger waveform properties.
		- The fitting formula for $M_{\mathrm{rem}}$ is given by $$\begin{aligned} \frac{M_{\mathrm{rem}}}{m}=&(4 \eta)^{2}\left\{M_{0}+K_{2 d} \delta m^{2}+K_{4 f} \delta m^{4}\right\} \\ &+\left[1+\eta\left(\tilde{E}_{\mathrm{ISCO}}+11\right)\right] \delta m^{6} \end{aligned} \tag{1}$$ where $\delta m=\left(m_{1}-m_{2}\right) / m$ and $m=\left(m_{1}+m_{2}\right)$ and $4 \eta=$ $1-\delta m^{2}$.
		- The final spin has the form $$\begin{aligned} \alpha_{\mathrm{rem}}=& \frac{S_{\mathrm{rem}}}{M_{\mathrm{rem}}^{2}}=(4 \eta)^{2}\left\{L_{0}+L_{2 d} \delta m^{2}+L_{4 f} \delta m^{4}\right\} \\ &+\eta \tilde{J}_{\mathrm{ISCO}} \delta m^{6} \end{aligned} \tag{2}$$ 
		- For the nonspinning recoil $$v_{m}=\eta^{2} \delta m\left(A+B \delta m^{2}+C \delta m^{4}\right) \tag{3}$$
		- We model the peak amplitude (of the strain $h$) $$\left(\frac{r}{m}\right) h_{\text {peak }}=(4 \eta)^{2}\left\{H_{0}+H_{2 d} \delta m^{2}+H_{4 f} \delta m^{4}\right\}+\eta \tilde{H}_{p} \delta m^{6} \tag{4}$$ where $\tilde{H}_{p}\left(\alpha_{\mathrm{rem}}\right)$ is the particle limit, taking the value $H_{p}(0)=1.4552857$ in the nonspinning limit.
		- The formula to model the peak luminosity $$\mathcal{L}_{\text {peak }}=(4 \eta)^{2}\left\{N_{0}+N_{2 d} \delta m^{2}+N_{4 f} \delta m^{4}\right\} \tag{5}$$
		- We model the peak frequency of the (2,2) mode of the gravitational wave strain $$m \omega_{22}^{\text {peak }}=(4 \eta)\left\{W_{0}+W_{2 d} \delta m^{2}+W_{4 f} \delta m^{4}\right\}+\tilde{\Omega}_{p} \delta m^{6} \tag{6}$$ where $\tilde{\Omega}_{p}\left(\alpha_{\text {rem }}\right)$ is the particle limit, taking the value $\tilde{\Omega}_{p}(0)=0.279525$ in the nonspinning limit.
		- Table III summarizes the new values of all those coefficients with their estimated errors.
			![[Pasted image 20210204162226.png]]
			
