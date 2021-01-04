## SXS Gravitational Waveform Database

Simulating eXtreme Spacetimes (SXS) Collaboration catalog of numerical simulations for merging black holes. All that data is hosted on [[Zenodo]]. Each simulation gets its own DOI and its own web page.

- [Homepage](https://data.black-holes.org/waveforms/index.html)


## Catalog papers

- [[Boyle2019]]

## Simulating eXtreme Spacetimes python package

Currently, the high-level objects encapsulate

- Catalog - a listing of all data produced by the SXS collaboration
- Metadata - data describing the simulation parameters
- Horizons - time-series data describing the apparent horizons
- Waveforms - time-series data describing the extrapolated gravitational-wave modes

An extensive demonstration of this package's capabilities is available [here](https://mybinder.org/v2/gh/moble/sxs_notebooks/master).

The following is just a very brief overview of the `sxs` package's main components.

- The first thing to know about SXS data is just what's available, which we gather together in "the catalog", which contains information about all datasets.

```python
import sxs

catalog = sxs.load("catalog")
catalog.table
```

- Once you have some idea of which simulations you're interested in. For example, you want to look at `SXS:BBH:0314`. This isn't actually specific enough to get any data. There are different versions of this simulation on Zenodo. Each of these are named "Lev" followed by some number. The number is complicated, but generally speaking: the higher this number is, the better.

	> Unless you are checking convergence or comparing results with someone who used a lower Lev, you probably just want the highest Lev. `Lev` would return only the highest result.

```python
import matplotlib.pyplot as plt
import sxs

waveform = sxs.load("SXS:BBH:0123/Lev/rhOverM", extrapolation_order=2)
plt.plot(waveform.t, waveform.data.real);
```

## Tools

-   [GWFrames](https://github.com/moble/GWFrames) - old and ugly
-   [scri](https://github.com/moble/scri) - powerful but complicated
-   [sxs](https://github.com/sxs-collaboration/sxs) - new and beautiful