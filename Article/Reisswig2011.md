# Notes on the integration of numerical relativity waveforms

- **Author**: Reisswig C, Pollney D.
- **Summary**:
	A simple procedure for integrating numerical waveforms in the frequency domain, which is effective at strongly reducing spurious secular non-linear drifts in the resulting strain.
- **Link**: [[Gravitational Wave Extraction]], [[GW - FFI Integration]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2011CQGra..28s5015R/abstract) Reisswig C, Pollney D. Notes on the integration of numerical relativity waveforms. Classical and Quantum Gravity, 2011, 28(19): 195015.
- **Code**: [[pyGWAnalysis]]
___

## Highlight

- An important source of **unphysical non-linear drift** in numerical computations of gravitational wave strain lies in the transformation of the measured data (commonly the Newman-Penrose variable $\psi_{4}$) to the observable strain $h$, which generically involves an integration in time.
	![[Pasted image 20201214134943.png]]
- For high-pass filters, with a careful choice of a frequency fitting interval, $\left[\omega_{0}, \omega_{1}\right]$ we find that the resulting strain, $h(t)$, is free of non-linear drifts and spurious oscillations.
	![[Pasted image 20201214155400.png]]
- The quality of various integration schemes
	![[Pasted image 20201214163746.png]]

## Random-walk effects

Consider an integral of the form

$$
F(t)=\int_{0}^{t} d t^{\prime} f\left(t^{\prime}\right)
$$

If $f(t)$ is known exactly, then we can evaluate the integral numerically according to a standard scheme, and the integral will converge to its continuum representation in the limit of infinite resolution. However, if the function contains small amounts of experimental (or numerical) noise, this has a significant impact on the accuracy of the time integration.

High-frequency components of the waveforms (whether truly random noise, a deterministic effect of discrete operators, or actual physical modes) are aliased onto the low-frequency physical signal. This can have a profound effect on operations such as integration.

We illustrate the effect of aliasing on integration in Fig. 2. We have integrated a signal which is composed purely of truncation error, modeled by a sinusoid,

$$
n(t)=\epsilon \sin (\omega t)
$$
whose frequency $\omega$ varies in time between the values $\omega_{i}=0.25$ and $\omega_{f}=4$.

![[Pasted image 20201214161338.png]]

The upper panel plots the original data, sampled at an interval of $\Delta t=1$. The function $n(t)$ oscillates near the Nyquist frequency, and is clearly under-resolved. Its first and second integrals are analagous to what would be expected from a random-walk.

## FFI Integration

Consider the Fourier transform,  $\mathcal{F}$, applied to an absolutely integrable function $f(t)$,
$$
\tilde{f}(\omega)=\mathcal{F}[f]=\int_{-\infty}^{\infty} e^{-i \omega t} f(t) d t
$$
The Fourier transform of the time integral of $f$ is given by
$$
\left.\mathcal{F}\left[\int_{-\infty}^{t} d t^{\prime} f\left(t^{\prime}\right)\right]\right|_{\omega}=-i \frac{\tilde{f}(\omega)}{\omega}
$$
and we arrive at a simple expression for the time-domain representation of the integral of $f$ in terms of the inverse Fourier transform:
$$
\int_{-\infty}^{t} d t^{\prime} f\left(t^{\prime}\right)=\mathcal{F}^{-1}\left[-i \frac{\tilde{f}(\omega)}{\omega}\right]=-\frac{i}{2 \pi} \int_{-\infty}^{\infty} \frac{1}{\omega} e^{i \omega t} \tilde{f}(\omega) d \omega
$$
In the frequency-domain, time integration becomes a simple division by the frequency. Thus, the method is particularly susceptible to low-frequency error. For instance, under-resolved high-frequency modes can be aliased onto low-frequency modes of the signal. More important is the fact that any numerically generated (or experimentally measured) time series is necessarily finite in length, which results in spectral leakage.

The effect of the spurious low-frequency modes, resulting from either spectral leakage or aliasing effects, can be significantly suppressed through the following prescription:
$$
\tilde{F}(\omega)=\left\{\begin{array}{ll}
-i \hat{f}(\omega) / \omega_{0}, & \omega \leq \omega_{0} \\
-i \tilde{f}(\omega) / \omega, & \omega>\omega_{0}
\end{array}\right.
$$
The single free parameter is $\omega_{0}$, which is set according to the lowest expected physical frequency for the given wave mode.

## Cutoff frequency

In practice, the choice of $\omega_{0}$ requires a certain amount of tuning. A small value will amplify unphysical low-frequency components during the integration process, while a large value may suppress some desired physical frequencies of the waveform.

 Once a particular $\omega_{0}$ has been found for the dominant $(\ell, m)=(2,2)$ mode, the same procedure can be applied to higher harmonic modes without additional fine-tuning by using the relation $\omega_{\ell m}=m \omega_{22} / 2$, which is a result of the phase relation of the spherical harmonics ${ }_{s} Y_{\ell m}$.
 
 > **Example**:
 > 
 > The initial orbital frequency at the start time of the simulation is $\omega \simeq 0.025$, corresponding to a wave frequency of $\omega_{\mathrm{i}}=0.05$ in the $(\ell, m)=(2,2)$ mode. For the integration procedure, we have used $\omega_{0}=0.035$ for the (2,2) and (3,2) modes, and $2 \omega_{0}$ and $3 \omega_{0}$ for (4,4) and (6,6) respectively.
 
 ## Window Function
 
 In certain situations, the result of the FFI can be improved by first applying a window function to the time domain signal before transforming to the Fourier domain. This is particularly the case for signals which do **not start and end with zero amplitude**.
- tanh window
$$
H(\omega)=\frac{1}{2}\left[1+\tanh \left(\frac{4\left(\omega-\omega_{0}\right)}{\sigma}\right)\right]
$$