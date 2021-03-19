## The binary black hole explorer: on-the-fly visualizations of precessing binary black holes

- **Author**: Varma V, Stein L C, Gerosa D.
- **Summary**:
	- We present a tool for visualizing mergers of precessing binary black holes. Rather than rely on expensive numerical simulations, we base our animations on surrogate models of numerical simulations.
	- This tool can be used by researchers and students alike, to gain valuable insights into the highly complex dynamics of precessing binary black holes.
- **Link**: [[binaryBHexp]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019CQGra..36i5007V) Varma V, Stein L C, Gerosa D. The binary black hole explorer: on-the-fly visualizations of precessing binary black holes. Classical and Quantum Gravity, 2019, 36(9): 95007.

___

## Highlight

- If the BH spins are misaligned with respect to the orbital angular momentum, relativistic spin-spin and spin-orbit couplings cause the system to precess.  
	- The spins and the orbital angular momentum oscillate about the direction of the total angular momentum.
	- This precession is imprinted on the observed gravitational waves as characteristic modulations of amplitude and frequency.
		- This complexity can be in part removed by moving into a non-inertial reference frame which tracks the direction of the orbital angular momentum $L$.
		- In this coprecessing frame, the waveform looks nearly as simple as that of a nonprecessing source.
	- Visualizations of precessing binary BHs can give valuable insights into their complex dynamics.
- An isolated astrophysical BH is characterized entirely by its mass $m$ and spin angular momentum $S=\chi m^{2}$. $\chi$ is the dimensionless spin, with magnitude $\chi \leq 1$ and $a=\chi m$ is the Kerr parameter.
- A quasicircular precessing binary BH system is characterized by seven intrinsic parameters: mass ratio $q=m_{1} / m_{2}$, and two spin vectors $\chi_{1}, \chi_{2}$.
- The total mass of the system $M=m_{1}+m_{2}$ can be scaled out. Therefore, throughout this paper, all length and time quantities are in units of $M$. After the merger takes place, the remnant BH is characterized by its mass $m_{f}$ spin $\chi_{f}$ and recoil velocity $v_{f}$.
- We assume the masses of the BHs are constant during the evolution. While the masses in an NR simulation can change due to in-falling energy through GWs, this is a very small effect higher than leading orbital energy loss that is safely ignored in current waveform models.
- In-falling angular momentum in the form of GWs can alter the spin magnitudes, but this is also a very small effect that is ignored by current waveform models.
- The BH trajectories extracted from numerical simulations are inherently gauge dependent.
- Given the trajectories in the coprecessing frame, the trajectories in the inertial frame are obtained by a quaternion transformation with the time-dependent rotation (unit) quaternions $\hat{Q}(t)$. $$\boldsymbol{x}_{i}=\hat{Q}(t) \boldsymbol{x}_{i}^{\prime} \hat{Q}^{-1}(t)$$
- Apart from precession, the BH spins have other important effects on the evolution of binaries. One such effect is the so called orbital hang-up effect which delays or prompts the merger of the BHs based on the sign of the BH spin component along the orbital angular momentum.