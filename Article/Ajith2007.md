## Data formats for numerical relativity

- **Author**: Ajith P, Boyle M, Brown D A, Fairhurst S, Hannam M, Hinder I, Husa S, Krishnan B, Mercer R A, Ohme F, Ott C D, Read J S, Santamaria L, Whelan J T.
- **Summary**:
	- We present a simple and extendible data format which is applicable to various kinds of gravitational wave sources.
- **Link**: [[Numerical Relativity]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2007arXiv0709.0093A/abstract) Ajith P, Boyle M, Brown D A, Fairhurst S, Hannam M, Hinder I, Husa S, Krishnan B, Mercer R A, Ohme F, Ott C D, Read J S, Santamaria L, Whelan J T. Data formats for numerical relativity. arXiv:0709.0093.

___

## Units

Black hole waveforms are given in units of $M$, where $M=m_{1}+m_{2}$ is the total initial black hole mass (for spinning BHs, this mass includes the spin contribution). Black hole separations are measured in coordinate distance, measured in $M$.

For simulations involving matter fields, the physical scale is fixed. Waveforms from such systems cannot be scaled to different masses. We use the convention of time in units of $M_{\odot}=4.92549095 \times 10^{-6} \mathrm{~s}$, and strain $r h_{\{+, \times\}}$ in units of $M_{\odot}=1.47662504 \times 10^{5} \mathrm{~cm}$. Frequencies in metadata are in units of $1 / M_{\odot}=203.025447 \mathrm{kHz}$.

## Gravitational wave start frequency

it is essential to indicate the start frequency of the waveform. Since different spheroidal harmonic modes differ in frequency, we choose to specify the start frequency of the $l=m=2$ harmonic harmonic. For black hole binaries, where all results scale with the total mass $M$, this is best done in units of $M$, and frequency $f_{0} / M$ is specified.

## Spin-weighted spherical harmonics

The explicit expression for the spin-weighted spherical harmonics in terms of the Wigner d-functions is
 
$$
{}^{-s} Y_{l m}(\iota, \phi) =(-1)^{s} \sqrt{\frac{2 \ell+1}{4 \pi}} d_{m, s}^{\ell}(\iota) e^{i m \phi}
$$
where

$$
d_{m, s}^{\ell}(\iota)=\sum_{k=k_{1}}^{k_{2}} \frac{(-1)^{k}[(\ell+m) !(\ell-m) !(\ell+s) !(\ell-s) !]^{1 / 2}}{(\ell+m-k) !(\ell-s-k) ! k !(k+s-m) !} \times\left(\cos \left(\frac{\iota}{2}\right)\right)^{2 \ell+m-s-2 k}\left(\sin \left(\frac{\iota}{2}\right)\right)^{2 k+s-m}
$$
with $k_{1}=\max (0, m-s)$ and $k_{2}=\min (\ell+m, \ell-s)$. For reference,

$$
\begin{aligned}
{}^{-s} Y_{22} &=\sqrt{\frac{5}{64 \pi}}(1+\cos \iota)^{2} e^{2 i \phi} \\
{}^{-s} Y_{21} &=\sqrt{\frac{5}{16 \pi}} \sin \iota(1+\cos \iota) e^{i \phi} \\
{}^{-s} Y_{20} &=\sqrt{\frac{15}{32 \pi}} \sin ^{2} \iota \\
{}^{-s} Y_{2-1} &=\sqrt{\frac{5}{16 \pi}} \sin \iota(1-\cos \iota) e^{-i \phi} \\
{}^{-s} Y_{2-2} &=\sqrt{\frac{5}{64 \pi}}(1-\cos \iota)^{2} e^{-2 i \phi}
\end{aligned}
$$