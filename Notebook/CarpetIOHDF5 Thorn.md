## CarpetIOHDF5 Thorn

Thorn CarpetIOHDF5 provides HDF5-based output to the Carpet mesh refinement driver in Cactus. HDF5 is highly recommended over ASCII for performance and storage-size reasons.

## Parameter

- Overrides `IO::out_every`
	```python
	IOHDF5::out_every   = 512 # 2^9 the 10th finest level
	IOHDF5::out2D_every = 512 # 2^9 the 10th finest level
	```
- Variables to output in CarpetIOHDF5 file format. The variables must be given by their fully qualified variable or group name.
	```python
	IOHDF5::out_vars   = "ADMBase::gxx{ cctk_iteration = 0 }"
	IOHDF5::out2D_vars = "ADMBase::gxx" # 2D HDF5 file format
	```
- Do checkpointing with CarpetIOHDF5?
	```python
	CarpetIOHDF5::checkpoint                    = yes
	CarpetIOHDF5::open_one_input_file_at_a_time = no  # Open all input files first, then import data (most efficient). Set to yes to reduce memory requirements.
	```
- Automatic `gzip` dataset compression
	```python
	CarpetIOHDF5::compression_level = 0   # Higher numbers compress better
	```
- Parallel Output
	```python
	IO::out_mode = "proc" # Parallel (chunked) Output of Grid Variables
	```
	The default is to output distributed grid variables in parallel, each processor writing a file `<varname>.file\_<processor ID>.h5`. Unchunked means that an entire Cactus grid array (gathered across all processors) is stored in a single HDF5 dataset whereas chunked means that all the processor-local patches of this array are stored as separate HDF5 datasets (called chunks). When visualising chunked datasets, they probably need to be recombined for a global view on the data. This needs to be done within the visualisation tool.

## Developer

- [[Erik Schnetter]]