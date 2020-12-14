# Lorene

LORENE is a set of C++ classes. It provides tools to solve partial differential equations by means of multi-domain [[Spectral Methods]].

![[lorenecode.png]]

- [[Lorene - Mg3D]] - stores Multi-domain grid of collocation points and takes into account symmetries
- [[Lorene - Map]] - relates the numerical grid coordinates $\left(\xi, \theta^{\prime}, \varphi^{\prime}\right)$ to the physical ones $(r, \theta, \varphi)$
- Mtbl - stores values of a function on grid points
- Mtbl_cf - stores spectral coefficients of a function
- [[Lorene - Base_val]] - contains information about the spectral bases
- Valeur - gathers a Mtbl, a Mtbl_cf and the Base_val to pass from one to the other

## Lorene's Header

Any source file using Lorene should include the header

```C++
// C headers
#include <cstdlib>
#include <cassert>
#include <cmath>
// Lorene headers
#include "headcpp.h"    // standard input/output C++ headers (iostream, fstream)
#include "metric.h"     // classes Metric, Tensor, etc...
#include "nbr_spx.h"    // defines infinity as an ordinary number: __infinity
#include "graphique.h"  // for graphical outputs
#include "utilitaires.h"// utilities

using namespace Lorene ;

int main() {
  /* Here goes your code */
  return EXIT_SUCCESS ; 
}
```

## LORENE's class

- Stars and black holes
	- Bhole_binaire - Binary black hole initial data
	- [[Lorene - Binaire]] - Binary neutron star initial data
	- Et_rot_mag - Magnetized isolated neutron star initial data
	- Bin_bhns - Black hole - neutron star initial data
	- Bin_bhns_extr - Black hole - Neutron star with an extreme mass ratio
	- Et_rot_diff - Differentially rotating stars initial data
	- etc
- Equations of state
- Tensorial fields
	- [[Lorene - Scalar]]
	- [[Lorene - Vector]]
	- [[Lorene - Metric]]
- Graphical outputs


