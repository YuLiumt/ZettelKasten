## Constraining neutron star radii in black hole-neutron star mergers from their electromagnetic counterparts

- **Author**: Fragione G, Loeb A.
- **Summary**:
	- Information on the EM counterpart in BH-NS mergers can be used to place constraints on the NS radius.
- **Link**: [[GW190426_152155]], [[NS - Radius]], [[Black Hole-Neutron Star Binaries]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210107313F) Fragione G, Loeb A. Constraining neutron star radii in black hole-neutron star mergers from their electromagnetic counterparts. arXiv:2101.07313.

___

## Highlight

- What makes BH-NS mergers interesting is the possibility that they can produce an electromagnetic (EM) counterpart after merger.
	- The merger will be followed by an EM counterpart only if the NS is disrupted by the tidal field of the BH, leading to mass ejection and the formation of an accretion torus around it. Otherwise, the NS plunges into the BH and the merger resembles a BH-BH merger.
	- We compute the remnant baryon mass ($M_{\text {rem}}$) using numerical relativity calculations,
		$$\hat{M}_{\mathrm{rem}}=\left[\max \left(\alpha \frac{1-2 C_{\mathrm{NS}}}{\eta^{1 / 3}}-\beta \hat{R}_{\mathrm{ISCO}} \frac{C_{\mathrm{NS}}}{\eta}+\gamma, 0\right)\right]^{\delta} \tag{1}$$ where $C_{\mathrm{NS}}=G M_{\mathrm{NS}} /\left(R_{\mathrm{NS}} c^{2}\right)$ is the NS compaction, which depends on the equation of state, $\eta=\frac{Q}{(1+Q)^{2}}$ with $Q=M_{\mathrm{BH}} / M_{\mathrm{NS}}$, is the symmetric mass ratio, $\hat{R}_{\mathrm{ISCO}}=\frac{R_{\mathrm{ISCO}}}{M_{\mathrm{BH}}}$ is the innermost stable circular orbit (ISCO) radius.	
		- Eq. (1) assumes that the BH spin is aligned to the orbital angular momentum. In the case it is inclined by an angle $I$, the same fitting formulae can be used by replacing the ISCO radius by the radius of the innermost stable spherical orbit (ISSO).
	- The maximum value of the mass ratio $M_{\mathrm{BH}} / M_{\mathrm{NS}}$ for which a BH-NS system will disrupt as a function of the NS radius ($R_{NS}$) and BH spin ($\chi_{\mathrm{BH}}$), assuming $M_{\mathrm{NS}}=1.3 \mathrm{M}_{\odot}$, for different inclinations $I$ between the BH spin and the orbital angular momentum.
		![[Pasted image 20210120193855.png]]
- To constrain the NS radius, information on the BH spin is needed.
	- GW measurements are especially sensitive to the effective spin. In the more typical case the NS is not a millisecond pulsar, and considering that $M_{\mathrm{BH}}>M_{\mathrm{NS}}$, yields $\chi_{\mathrm{BH}, \|} \approx \chi_{\mathrm{eff}} \frac{M_{\mathrm{BH}}+M_{\mathrm{NS}}}{M_{\mathrm{BH}}}$.
	- This information, along with the presence or not of an EM counterpart, can be used to constrain the NS radius.
	- Derive a lower (upper) limit based on the presence (absence) of an EM counterpart.
		![[Pasted image 20210120195027.png]]
		- In case the NS plunges onto the BH and no EM counterpart is observed following the merger, the allowed portion of the parameter space is below the curve (white line). This translates into an upper limit on the NS radius.
		- On the other hand, if the EM counterpart is observed following the BH-NS merger, the allowed portion of the parameter space is above the curve, translating into a lower limit on the NS radius.
	- Our method applied to GW190426_152155
		![[Pasted image 20210120201127.png]]
		- For GW190426_152155, no EM counterpart has been observed.
		- Measurement errors on the effective spin are too large to place an upper limit on the NS radius for this candidate event.
		- If an EM counterpart had been observed, we would have been able to place a lower limit on the NS radius, $R_{\mathrm{NS}} \gtrsim 12.5 \mathrm{~km}$.