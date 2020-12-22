## Effective-one-body

In the EOB formalism, higher-order PN correction is included by re-summation techniques and calibrated by comparing the model waveforms with those derived by numerical-relativity simulations of [[Binary Black Hole]].

These analytic techniques are useful for quickly computing waveform templates to matched filtering searches in GW detector data analysis.

The role of Numerical Relativity (NR) in this regime is mainly to test and help improve the properties of these analytic techniques. However, one has to keep in mind that such comparison and improvement would need the use of NR data extrapolated at infinite resolutions or at a resolution where discretization errors are negligible.

## Model

The template strongly depends on the specific theoretical model of GW source.

- SEOBNR 
	- Buonanno et al. (2007) for the first time combined the Effective-one-body (EOB) method with numerical-relativity (NR) to obtain the EOBNR model.
	- SEOBNR is valid only for quasi-circular orbit and black hole spin perpendicular to the orbital plane which means the precession is not presented.
- SEOBNRE
	- Cao & Han (2017) construct the first eccentric binary waveform model based on effective-one-body-numerical-relativity framework. They call their model SEOBNRE (Spinning Effective-One-Body-Numerical-Relativity model for Eccentric binary).
- TF2+_KyotoTidal
	- Kawaguchi2018 have developed a model for frequency-domain gravitational waveforms of inspiraling BNSs.
	- They focus only on gravitational waves for $f \leq 1000 \mathrm{Hz}$. The reason for this is that the gravitational-wave spectra for $f>1000 \mathrm{Hz}$ would be affected by the post-merger waveforms.
	- They calibrate their waveform model employing hybrid waveforms constructed from their latest numerical-relativity waveforms and the TEOB waveforms. 
	- The hybrid waveforms are composed of the high-frequency part ($> 400 \mathrm{Hz}$) and the low-frequency part ($< 400 \mathrm{Hz}$). For the high-frequency parts, they employ numerical-relativity waveforms. The simulations are performed by using a numerical-relativity code, SACRA. For the low-frequency part, we employ the TEOB waveforms, which are currently among the most successful approximants in which the tidal effects as well as higher PN effects are taken into account.