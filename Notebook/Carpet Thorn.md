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

A few words about the Carpet grid structure statistics.

```c
INFO (Carpet): Grid structure statistics:
INFO (Carpet): GF: rhs: 25k active, 33k owned (+30%), 74k total (+124%), 6 steps/time
INFO (Carpet): GF: vars: 69, pts: 11M active, 14M owned (+30%), 31M total (+124%), 1.0 comp/proc
INFO (Carpet): GA: vars: 271, pts: 0M active, 0M total (+0%)
```
- The first output line shows the number of grid points used by the active (in the sense of being used) grid functions entering the right hand side of MOL thorn. The example above shows that 25,000 (25k) active grid points are used for the whole grid hierarchy; 33k are owned grid points (active + buffer) by the set of all MPI jobs (or components/regions represented by a particular MPI process), resulting in an overhead of 30% with respect to the number of active grid points; adding the ghost regions to the active and buffer regions results into a total of 74k grid points, an overhead of 124% with respect to the owned region.

## Developer

- [[Erik Schnetter]]