## CoordBase Thorn

The CoordBase thorn provides a method of registering coordinate systems and their properties.



CoordBase provides a way for specifying the extent of the simulation domain that is independent of the actual coordinate and symmetry thorns. This is necessary because the size of the physical domain is not necessarily the same as the size of the computational grid, which is usually enlarged by symmetry zones and/or boundary zones.

  
The black hole "source” region has a length scale of :math:\`G M / c^{2}\`, where G is Newton’s constant, M is the total mass of the two black holes, and c is the speed of light. The gravitational waves produced by the source have a length scale up to :math:\`\\sim 100 G M / c^{2}\`. The source region requires grid zones of size :math:\`\\lesssim 0.01 G M / c^{2}\` to accurately capture the details of the black holes’ interaction, while the extent of the grid needs to be several hundred :math:\`G M / c^{2}\` to accurately capture the details of the gravitational wave signal.

  

## Parameter


\* Specifying the extent of the physical domain.

  

\>>> CoordBase::domainsize = "minmax" # lower and upper boundary locations

\>>> CoordBase::xmin = -540.00

\>>> CoordBase::ymin = -540.00

\>>> CoordBase::zmin = -540.00

\>>> CoordBase::xmax = 540.00

\>>> CoordBase::ymax = 540.00

\>>> CoordBase::zmax = 540.00

\>>> CoordBase::dx = 18.0

\>>> CoordBase::dy = 18.0

\>>> CoordBase::dz = 18.0

INFO (Carpet): CoordBase domain specification for map 0:

physical extent: \[-540,-540,-540\] : \[540,540,540\] (\[1080,1080,1080\])

base\_spacing : \[18,18,18\]

  

\* Boundary description.

  

\>>> CoordBase::boundary\_size\_x\_lower = 3

\>>> CoordBase::boundary\_size\_y\_lower = 3

\>>> CoordBase::boundary\_size\_z\_lower = 3

\>>> CoordBase::boundary\_size\_x\_upper = 3

\>>> CoordBase::boundary\_size\_y\_upper = 3

\>>> CoordBase::boundary\_size\_z\_upper = 3

\>>> CoordBase::boundary\_internal\_x\_lower = "no"

\>>> CoordBase::boundary\_internal\_y\_lower = "no"

\>>> CoordBase::boundary\_internal\_z\_lower = "no"

\>>> CoordBase::boundary\_internal\_x\_upper = "no"

\>>> CoordBase::boundary\_internal\_y\_upper = "no"

\>>> CoordBase::boundary\_internal\_z\_upper = "no"

\>>> CoordBase::boundary\_staggered\_x\_lower = "no"

\>>> CoordBase::boundary\_staggered\_y\_lower = "no"

\>>> CoordBase::boundary\_staggered\_z\_lower = "no"

\>>> CoordBase::boundary\_staggered\_x\_upper = "no"

\>>> CoordBase::boundary\_staggered\_y\_upper = "no"

\>>> CoordBase::boundary\_staggered\_z\_upper = "no"

\>>> CoordBase::boundary\_shiftout\_x\_lower = 0

\>>> CoordBase::boundary\_shiftout\_y\_lower = 0

\>>> CoordBase::boundary\_shiftout\_z\_lower = 0

\>>> CoordBase::boundary\_shiftout\_x\_upper = 0

\>>> CoordBase::boundary\_shiftout\_y\_upper = 0

\>>> CoordBase::boundary\_shiftout\_z\_upper = 0

INFO (Carpet): Boundary specification for map 0:

nboundaryzones: \[\[3,3,3\],\[3,3,3\]\]

is\_internal : \[\[0,0,0\],\[0,0,0\]\]

is\_staggered : \[\[0,0,0\],\[0,0,0\]\]

shiftout : \[\[0,0,0\],\[0,0,0\]\]

INFO (Carpet): CoordBase domain specification for map 0:

interior extent: \[-522,-522,-522\] : \[522,522,522\] (\[1044,1044,1044\])

exterior extent: \[-576,-576,-576\] : \[576,576,576\] (\[1152,1152,1152\])
