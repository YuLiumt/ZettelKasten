## Lorene - Map

A mapping relates, in each domain, the numerical grid coordinates $\left(\xi, \theta^{\prime}, \varphi^{\prime}\right)$ to the physical ones $(r, \theta, \varphi)$. The simplest class is `Map_af` for which the relation between and $\xi$ and $r$ is linear (nucleus + shells) or inverse (CED).

![[Map.png]]

- The boundary of each domain is chosen in order to coincide with a physical discontinuity.

```C++
// radial boundaries of each domain:
double r_limits[] = {0., 1., 2., __infinity} ;
assert(nz==3) ; // since above array describes only 3 domains
// Construction of an affine mapping (Map_af)
Map_af map(mgrid, r_limits) ;
```