## Carpet Thorn

Carpet is a mesh refinement driver for Cactus.

In Carpet, a local grid has a number of attributes:
- **reflevel** - This is an integer specifying the grid’s "refinement level" in the Berger-Oliger algorithm.
- **map** - This is an integer specifying the "map" (grid patch) at this refinement level.
- **component** - This is an integer specifying one of the local grids in this map/patch.

## Parameter

- File name to output grid coordinates
	```python
	Carpet::grid_coordinates_filename = “carpet-grid.asc”
	```
- Output timing information in tree form to standard output.
	```python
	Carpet::output_initialise_timer_tree = yes
	Carpet::output_timer_tree_every      = 51200 # report every so many iterations
	```
	
## Output

- Speed of a run
	```python
	IOBasic::outInfo_vars = "Carpet::physical_time_per_hour" # cctk_time/hour
	IOASCII::out0D_vars   = "Carpet::timing"
	```

## Developer

- [[Erik Schnetter]]