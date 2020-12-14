## Lorene - Mg3D

Multi-domain grid of collocation points on which the functions are evaluated to compute the spectral coefficients.

```C++
int nz = 3 ; // Number of domains
int nr = 7 ; // Number of collocation points in r
int nt = 5 ; // Number of collocation points in theta
int np = 8 ; // Number of collocation points in phi
```

Additional symmetries can be taken into account:

```C++
int symmetry_theta = SYM ; // symmetry with respect to the equatorial plane (z=0)
int symmetry_phi = NONSYM ; // invariance under the (x,y)->(-x,-y) transform.
```

The last domain have a $1/r$ sampling.

```C++
bool compact = true ; // external domain is compactified
```

In each domain, the radial variable used is $\xi \in[-1,1],$ or $\in[0,1]$ for the nucleus.

```C++
// Multi-domain grid construction:
Mg3d mgrid(nz, nr, nt, np, symmetry_theta, symmetry_phi, compact) ;
```