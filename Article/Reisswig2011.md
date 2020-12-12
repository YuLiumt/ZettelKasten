# Notes on the integration of numerical relativity waveforms

* **Author**: Reisswig C, Pollney D.
* **Summary**:
    
* **Link**: [[Gravitational Wave]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2011CQGra..28s5015R/abstract) Reisswig C, Pollney D. Notes on the integration of numerical relativity waveforms. Classical and Quantum Gravity, 2011, 28(19): 195015.

#in-progress
___

## FFI Integration

$$
F(t)=\int_{0}^{t} d t^{\prime} \int_{0}^{t^{\prime}} d t^{\prime \prime} f\left(t^{\prime \prime}\right)
$$

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
In the frequency-domain, time integration becomes a simple division by the frequency. Thus, the method is particularly susceptible to low-frequency error.

> The observation of any ﬁnite duration signal is equivalent of multiplying an inﬁnite signal with a rectangular window function. According to the convolution theorem, multiplying a signal with another signal in the time domain corresponds to convolving the Fourier transformed signals in the frequency domain. Because the frequency representation of the rectangular window function is the sinc function, which has inﬁnite bandwidth, the same is true of the convolved signal. This phenomenon, sometimes termed spectral leakage.

Accordingly, we propose to evaluate the integral using the following prescription:
$$
\tilde{F}(\omega)=\left\{\begin{array}{ll}
-i \hat{f}(\omega) / \omega_{0}, & \omega \leq \omega_{0} \\
-i \tilde{f}(\omega) / \omega, & \omega>\omega_{0}
\end{array}\right.
$$
The single free parameter is $\omega_{0}$, which is set according to the lowest expected physical frequency for the given wave mode.