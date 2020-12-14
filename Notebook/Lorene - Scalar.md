## Lorene - Scalar

The class Scalar gathers a Valeur and a mapping, it represents a scalar field defined on the spectral grid. 

```C++
// Various coordinates associated with the mapping
const Coord& r = map.r ;        // r field
const Coord& x = map.x ;        // x field
const Coord& y = map.y ;        // y field
// Setup of a regular scalar field
Scalar phi(map) ;
phi = x*exp(-r*r-y*y) ;
```

Accessors and modifier of values in a given domain

```C++
// 0 at spatial infinity (instead of NaN !)
phi.set_outer_boundary(nz-1, 0) ; 
```

Spectral base manipulation

```C++
// Standar polynomial bases will be used to perform the spectral expansions
phi.std_spectral_base() ;  
```

In the compactified external domain (CED), the variable $u=1 / r$ is used (up to a factor $\alpha$). When computing the radial derivative (i.e. using the method `phi.dsdr()` of a field $f$, one gets

$$
\frac{\partial f}{\partial u}=-r^{2} \frac{\partial f}{\partial r}
$$

Use of an integer flag `dzpuis` for a scalar field $f$, which means that in the CED, one does not have $f$, but $r^{\mathrm{dzpuis}} f$ stored.

```C++
// Computation of the radial derivative
Scalar dphidr = phi.dsdr() ;
dphidr.dec_dzpuis(2) ;
```
