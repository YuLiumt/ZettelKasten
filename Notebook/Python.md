## Python

## Install Package

Python package can be installed in a variety of ways.

- Using pip:
	```
	$ pip install <package>
	```
- Using conda:
	```
	$ conda install -c conda-forge <package>
	```

For installing the development version, you can do:

- Installation from clone:
	```
	$ git clone <github>
	$ cd <package>
	$ pip install -e .
	```

## Python Package

- Astronomy
	- [Astropy](https://www.astropy.org) - Astronomy in Python and foster an ecosystem of interoperable astronomy packages.
	- [PyEphem](https://rhodesmill.org/pyephem/index.html) - Compute planet, comet, asteroid, and Earth satellite positions.
	- ShowerModel - Cosmic-ray
	- [JetFit](https://github.com/NYU-CAL/JetFit) - The JetFit package fits GRB afterglow light curves for arbitrary viewing angle using the "boosted fireball" structured jet model.
- MCMC
	- [emcee](https://emcee.readthedocs.io/en/v2.2.1/) - MCMC
	- [PyMC3](https://docs.pymc.io) - MCMC
	- [UltraNest](https://johannesbuchner.github.io/UltraNest/index.html) - Bayesian inference package for parameter estimation and model comparison.
- Telescopes
	- [DarpanX](https://github.com/biswajitmb/DarpanX) - Modeling X-ray Reflectivity of Multilayer Mirrors
	- [Curvit](https://github.com/prajwel/curvit) - Produce light curves from the Ultra-Violet Imaging Telescope (UVIT)
- Gravitational Wave
	- [GWpy](https://gwpy.github.io/docs/latest/index.html) - Providing tools for studying data from ground-based gravitational-wave detectors.
	- [PyCBC](https://pycbc.org) - Detect coalescing compact binaries and measure the astrophysical parameters of detected sources.
	- [Bilby](https://lscsoft.docs.ligo.org/bilby/) - A user-friendly interface to perform parameter estimation.
	- [PyFstat](https://pyfstat.readthedocs.io/en/latest/) - Continuous gravitational-wave data analysis
	- [pygwinc](https://git.ligo.org/gwinc/pygwinc) - Gravitational Wave Interferometer Noise Calculator
- Artificial Intelligence
	- [scikit-learn](https://scikit-learn.org/stable/) - Machine Learning
- General Relativity
	- [[EinsteinPy]]
- Numerical Relativity
	- [[NRPy+]] - Python-based code generation for numerical relativity.
	- [[pyGWAnalysis]] - Gravitational Wave postprocessing tool.
	- [sxs](https://github.com/sxs-collaboration/sxs)- Download and interact with the SXS Catalog
	- [[EccRed]]- Automated framework to produce low eccentricity numerical binary black hole simulations.
	- [[surfinBH]] - surfinBH provides surrogate final Black Hole properties for mergers of binary black holes (BBH).
	- gwsurrogate - 
	- [[binaryBHexp]] - Generates visualizations of precessing binary black hole mergers and the final remnant black holes.
	- [[Riroriro]] - Simulate the gravitational waveforms of binary mergers of black holes and/or neutron stars, and calculate several properties of these mergers and waveforms.
	- [[surrkick]]- Black-hole kicks from numerical-relativity surrogate models.
- Visualization
	- [seaborn](http://seaborn.pydata.org) - Drawing attractive and informative statistical graphics.
	- [[ipygany]] - Jupyter Interactive Widgets library for 3-D mesh analysis
	- [[Mayavi]] - 3D plotting and data visualization with numpy