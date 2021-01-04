## Initial Data and Eccentricity Reduction Toolkit for Binary Black Hole Numerical Relativity Waveforms

- **Author**: Habib S, Ramos-Buades A, [[Eliu Huerta]], Husa S, [[Roland Haas]], [[Zachariah Etienne]].
- **Summary**:
	- An open source Python tools for initial data production and eccentricity reduction of spinning black hole binaries.
		- NRPyPN provides the zeroth estimate for low-eccentricity initial data. [[NRPy+]]
		- The process of eccentricity reduction using EccRed.
- **Link**: [[Binary Black Hole]], [[BBH - Orbital Eccentricity]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020arXiv201108878H) Habib S, Ramos-Buades A, Huerta E A, Husa S, Haas R, Etienne Z. Initial Data and Eccentricity Reduction Toolkit for Binary Black Hole Numerical Relativity Waveforms. arXiv:2011.08878.

___

## EccRed

Automated framework to produce low eccentricity numerical binary black hole simulations.

```bash
git clone https://github.com/ncsagravity/eccred
```

The code expects to two sets of files in the output directories:
- A file `TwoPunctures.bbh` as produced by the TwoPunctures thorn that describes the parameters of the initial black holes.
- A set of puncture location files `puncturetracker-pt_loc..asc` as produced by the PunctureTracker thorn.