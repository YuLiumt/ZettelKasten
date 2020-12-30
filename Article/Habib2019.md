## Characterization of numerical relativity waveforms of eccentric binary black hole mergers

- **Author**: Habib S, [[Eliu Huerta]].
- **Summary**:
	- Once the data products of NR simulations are post-processed, and NR waveforms are extracted, it is necessary to characterize them, i.e., we need to quantify the eccentricity and other orbital parameters that uniquely identify them.
	- We introduced a method to characterize numerical relativity waveforms that describe nonspinning black holes on moderately eccentric orbits.
	- This method provides a robust characterization of eccentric binary black hole mergers with mass-ratios $q \leq 10$ and eccentricities $e_{0} \leq 0.2$ fifteen cycles before merger.
- **Link**: [[Binary Black Hole]], [[BBH - Orbit Eccentricity]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019PhRvD.100d4016H) Habib S, Huerta E A. Characterization of numerical relativity waveforms of eccentric binary black hole mergers. PRD, 2019, 100(4): 44016.

___

## Highlight

- Methods to characterize NR waveforms
	- If BBHs are on **nearly quasi-circular orbits**, then one could combine information about the orbital separation of the BHs, and waveform phase and amplitude of the Weyl scalar $\psi_{4}$. Healy2017
	- Infer orbital eccentricity based on the trajectories of the BHs in the NR simulation, which is not a sound approach given that these trajectories are **gauge-dependent**.
	- We circumvent the aforementioned limitations by introducing a gauge-invariant method that characterizes a NR waveform by comparing to a large array of ENIGMA waveforms.
		- The inspiral-merger-ringdown ENIGMA model consists of an inspiral evolution that encodes higher-order post-Newtonian (PN) corrections to the motion of compact sources on eccentric orbits, combined with self-force and BH perturbation corrections.
		- ENIGMA was constructed under the assumption that moderately eccentric BBH systems circularize prior to merger.
		- This approach ensures that **the dynamics of quasi-circular and moderately eccentric BBHs are accurately described**.
- The circularization of moderately eccentric BBH mergers.
	- All NR waveforms, with eccentricities $e_{0} \leq 0.2$ fifteen cycles before merger, circularize at least $50 M$ before merger.
		![[Pasted image 20201216130620.png]]
	- Modeling eccentric BBH mergers under the assumption that they circularize prior to merger requires two key components:
		- an effective scheme that describes the early inspiral evolution, and which remains accurate at least $50M$ before merger.
		- a stand-alone quasi-circular merger that can be smoothly attached to the late-inspiral evolution.
- The impact of higher order waveform modes
	- NR waveforms that describe asymmetric mass-ratios, eccentric BBH mergers have a much richer topology that requires the inclusion of $(\ell,|m|)$ modes.

## Algorithm to characterize NR waveforms

We measure the orbital eccentricity of NR waveforms using the $\ell=|m|=2$ mode. The rationale for this choice is that we are characterizing NR waveforms using the **ENIGMA waveform model**, which **only includes the $\ell=$ $|m|=2$ mode**.

We explored a variety of **gauge-invariant** objects to directly compare NR and ENIGMA waveforms, and found that **the dimensionless object** $M \omega$, where $\omega$ is the mean orbital frequency, and $M$ stands for the total mass of the BBH, provides **a robust approach to capture the signatures of eccentricity**.

$$
\begin{aligned}
h^{(\ell=|m|=2)}(t) &=h_{+}-i h_{\times} \\
M \omega =M \dot{\phi}^{(\ell=|m|=2)} &=\frac{1}{2} \frac{\dot{h}_{+} h_{\times}-h_{+} \dot{h}_{\times}}{h_{+}^{2}+h_{\times}^{2}}
\end{aligned}
$$

On the other hand, the quantity $M \omega$ is one of the building blocks of the ENIGMA model.

A schematic of the algorithm used to characterize NR waveforms.
- The ENIGMA parameters of concern are initial orbital eccentricity $e_{0}$ initial GW frequency $f_{0},$ and mean anomaly $l_{0}$.
- Initial conditions of the ENIGMA simulation are varied until the ENIGMA time evolution of $M \omega$ agrees with the NR evolution to a specified degree of accuracy.
	- Both eccentricity and gravitational wave frequency are coupled. In view of this observation, we optimize $\left(e_{0}, f_{0}\right)$ simultaneously. On the other hand, the net effect of varying $l_{0}$ is to introduce what amounts to a minor shift in the position of the peaks of the orbital frequency $M \omega$.
	- Since we know experimentally that values close to $l_{0} \sim \pi$ will produce ENIGMA waveforms that tend to be aligned with their NR counterparts, we start the optimization with this seeded value for $l_{0}$ and then do minor refinement to this value later on.
	- We provide an informed guess of GW frequency using the relation $\omega_{0} /(M \pi),$ where $\omega\left(t_{0}\right)=\omega_{0}$ and $t_{0}$ is the time at which the NR waveform is free from junk radiation. Orbital eccentricity does not require a seed value since the range of possible values is consistent for all catalogued waveforms.
	- In order to avoid the **hill-climbing problem** of finding a solution at a local minimum of the cost function, the initial guesses of $\left(f_{0}, e_{0}\right)$ are randomly sampled within the range confined by the grid search.
	![[Pasted image 20201216111448.png]]
- The NR waveform is first preprocessed by cutting off initial noise (junk radiation). We then apply a SavitskyGolay filter to remove high frequency noise from the $M \omega$ time-series data.
	![[Pasted image 20201216112001.png]]

The results of this optimization procedure for a sample of NR waveforms.
	![[Pasted image 20201216112941.png]]