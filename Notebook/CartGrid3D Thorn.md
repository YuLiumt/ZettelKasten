## CartGrid3D Thorn

CartGrid3D allows you to set up coordinates on a 3D Cartesian grid in a flexible manner. CartGrid3D also provides routines for registering symmetries of grid functions and applying symmetry conditions across the coordinate axes.

## Parameter

- Get specification from CoordBase
	```
	CartGrid3D::type = "coordbase"
	```
- Get specification from MultiPatch
	```
	CartGrid3D::type = "multipatch"
	CartGrid3D::set_coordinate_ranges_on = "all maps"
	```
  

## Output

- 3D Cartesian grid coordinates
	```
	CarpetIOHDF5::out2D_vars = "grid::coordinates"
	```