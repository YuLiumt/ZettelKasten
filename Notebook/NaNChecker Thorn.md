## NaNChecker Thorn

This thorn is a utility thorn, designed to be used for debugging and testing code for uninitialised variables, or for variables which become corrupted during a simulation, for example following a division by zero or illegal memory usage.

## Parameter

- Periodic testing of variables
	```python
	NaNChecker::check_every     = 256 # How often to check (iterations)
	NanChecker::check_after     = 0   # Start checking after so many iterations
	NaNChecker::check_vars      = "ML_BSSN::ML_log_confac"
	```
- What to do if a NaN was found
	```python
	NaNChecker::action_if_found = terminate
	```
- Tracking and Visualizing NaNs Positions
	```python
	NaNChecker::out_NaNmask     = yes
	```
	The NaNChecker thorn can mark the positions of all the NaNs found for a given list of CCTK grid functions in a mask array and save this array to an HDF5 file `NaNmask.h5`.

## Developer

- Thomas Radke