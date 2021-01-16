## IOUtil Thorn

This thorn is the flesh for IO - it always needs to be activated if you want to do some IO in Cactus. The thorn just provides basic IO parameters.

## Parameter

- The name of the directory to be used for output.
	```c
	IO::out_dir = $parfile
	```
- How often, in terms of iterations, each of the Cactus I/O methods will write output.
	```c
	IO::out_every = 512 # 2^(n-1) the nth finest level
	```
- Every processor writes its own chunk of data into a separate output file.
	```c
	IO::out_mode = "proc"
	```
	For a run on multiple processors, scalar, 1D, and 2D output will always be written from only processor zero (that is, required data from all other processors will be sent to processor zero, which then outputs all the gathered data). For full-dimensional output of grid arrays this may become a quite expensive operation since output by only a single processor will probably result in an I/O bottleneck and delay further computation. For this reason Cactus offers different I/O modes for such output which can be controlled by the `IO::out_mode` parameter.
- Checkpointing and recovery
	```python
	IO::checkpoint_ID           = yes           # Checkpoint initial data 
	IO::checkpoint_every        = -1            # How often to checkpoint (iterations)
	IO::checkpoint_on_terminate = yes           # Checkpoint after last iteration
	IO::checkpoint_dir          = "checkpoints" # Output directory for checkpoint files
	IO::recover                 = "autoprobe"   # Recover from a checkpoint file Automatically?
	IO::recover_dir             = "checkpoints" # Directory to look for recovery files
	```
- Abort on I/O errors 
	```python
	IO::abort_on_io_errors      = yes
	```
	
## Warning

- No driver thorn activated to provide storage for variables
	```python
	ActiveThorns = "Carpet"
	```
	
## Developer

- Gabrielle Allen
- Tom Goodale
- Thomas Radke