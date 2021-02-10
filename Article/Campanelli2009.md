## Comparison of numerical and post-Newtonian waveforms for generic precessing black-hole binaries

- **Author**: Campanelli M, [[Carlos Lousto]], Nakano H, Zlochower Y.
- **Summary**:
	- We analyzed the first long-term generic waveform produced by the merger of unequal mass, unequal spins, precessing black-hole binaries.
		- These waveforms clearly show the effects of eccentricity and precession on the amplitude in the sub-leading ($\ell=2, m=1$) and ($\ell=3, m=3$) modes.
		- In particular, analyzing the ($\ell=2, m=1$) mode provides a way of detecting precessional effects in the observed waveforms.
	- Our results indicate that higher-order PN corrections to the orbital motion may further increase the accuracy of the PN waveforms.
- **Link**: [[BBH - Orbital Precession]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2009PhRvD..79h4010C) Campanelli M, Lousto C O, Nakano H, Zlochower Y. Comparison of numerical and post-Newtonian waveforms for generic precessing black-hole binaries. , 2009, 79(8): 84010.

___

## Highlight

- We evolve these black-hole-binary data-sets using the LazEv
- To generate the initial data parameters, we used random values for the mass ratio and spins of the binary. We then calculated approximate quasi-circular orbital parameters for a binary with these chosen parameters at an initial orbital separation of $50M$ and evolved using purely PN evolutions until the binary separation decreased to $11M$. The goal was to produce very low eccentricity orbital parameters at $r = 11M$.
- trajectory
	![[Pasted image 20210210095354.png]]
- The precession of the orbital plane is itself driven by the precession of the total spin of the binary. Thus we can measure the rate of orbital plane precession by looking at the components of the black-hole spins as a function of time.
	![[Pasted image 20210210095908.png]]
	- Note that the precessional frequency is quite low, with the precession occurring on a timescale of order $1000M$.
	- Despite this long timescale, precession can affect the waveform modes on shorter timescales via mode-mixing effects. That is, precession of the orbital plane will cause our mode decomposition to mix different modes.
- Due to the spurious radiation on the initial slice, the numerical black-hole masses change with time, and eventually equilibrate to a mass ratio of $q = 0.7993$.
	- Thus in order to compare the PN and numerical waveforms, we need to account for this change in mass ratio.