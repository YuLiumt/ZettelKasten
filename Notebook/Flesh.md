# Flesh

The flesh is the core of [[Cactus]], it provides the APIs for [[Thorns]] to communicate with each other, and performs a number of administrative tasks at build–time and run–time.

- build–time
	- The flesh is responsible for parsing the configuration files at build-time, generating source code to instantiate the different required thorn variables, parameters and functions, as well as checking required thorn dependencies.
- run-time
	- At run-time the flesh parses a user provided parameter file which defines which thorns are required and provides key-value pairs of parameter assignments. The flesh then activates only the required thorns, sets the given parameters, using default values for parameters which are not specified in the parameter file, and creates the schedule of which functions provided by the activated thorns to run at which time.
	- The Cactus flesh provides the main iteration loop for simulations but does not handle memory allocation for variables or parallelization; this is performed by a [[Driver]].
		![[flesh.png]]










