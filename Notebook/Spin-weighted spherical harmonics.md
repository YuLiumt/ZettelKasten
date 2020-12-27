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