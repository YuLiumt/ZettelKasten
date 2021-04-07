## Parameter Estimation Bias From Overlapping Binary Black Hole Events In Second Generation Interferometers

- **Author**: Relton P, Raymond V.
- **Summary**:
	- we investigate the probability of observing two compact binary mergers at close enough times.
		- Although we are unlikely to observe overlapping signals within the lifetime of current detectors, we should expect such events to occur in observations in LIGO-Voyager.
	- We also investigate the effects overlapping signals can have on parameter estimation techniques currently in use within the LVK Collaboration.
		- We treat overlapping signals as a single event and apply parameter estimation agnostically, making only the assumption that the system is a merging BBH.
		- We attempt to constrain the regions in which such overlapping signals show significant bias.
		- We do not expect these events to produce significant bias due to the significant differences in their frequency evolution.
- **Link**: 
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210316225R) Relton P, Raymond V. Parameter Estimation Bias From Overlapping Binary Black Hole Events In Second Generation Interferometers. arXiv:2103.16225

___

## Highlight

- As the rate of observed mergers increases, the probability of more than one, concurrent signal being observable by the network increases. 
	- Most current detection and analysis techniques assume that only one signal is visible at any period of time. Therefore, any overlapping signals would be assumed to be one single signal.
- Probability of Observing Overlapping Events
	- The number of Compact-Binary-Coalescence (CBC) events observed by a detector depends on the volume of space that the detector can observe, the merger rate of such systems and the length of observing period.
	- By taking a power spectral density (PSD) of a detector, it is possible to characterise the noise of that detector and to use this to calculate the Signal-to-Noise-Ratio (SNR) of a particular compact binary coalescence.
	- As CBC mergers are assumed to be random and independent, they can be modelled by a Poisson distribution. The probability of an merging system being observed within a specific time period is then given by: $$P\left(\mathrm{k} \text { events in time } \mathrm{T}_{\mathrm{obs}}\right)=\frac{\left(R T_{o b s}\right)^{k} \exp ^{-R T_{o b s}}}{k !}$$ where $R$ is the rate of mergers, $T_{obs}$ is the period of observation, $k$ is the number of mergers in that period.
- The PSD was created using the python package pygwinc.