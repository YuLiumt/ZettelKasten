## Cactus Configuration Language

Cactus Configuration Language (CCL) files are text files which tells the flesh all it needs to know about the thorns.

> CCL files may contain comments introduced by the hash `#` character, which indicates that the rest of the line is a comment. If the last non-blank character of a line in a CCL file is a backslash `\\`, the following line is treated as a continuation of the current line.

## The interface.ccl File

- implementation name
	```C++
	implements: <name>
	```
	- The implementation name must be unique among all thorns.
- Inheritance relationships between thorns
	- There are two relationship statements that can be used to get variables (actually groups of variables) from other implementations.
		- Gets all Public variables from implementation `<name>`, and all variables that `<name>` has in turn inherited
			```C++
			Inherits: <name>
			```
			- A thorn cannot inherit from itself. Inheritance is transitive (if A inherits from B, and B inherits from C, then A also implicitly inherits from C), but not commutative.
		- Gets all Protected variables from implementation `<name>`, but, unlike inherits, it defines a transitive relation by pushing its own implementation’s Protected variables onto implementation `<name>`.
			```C++
			Friend: <name>
			```
			- A thorn cannot be its own friend. Friendship is associative, commutative and transitive (if A is a friend of B, and B is a friend of C, then A is implicitly a friend of C).
- Cactus variables
	- Cactus variables are placed in variable groups with homogeneous attributes, where the attributes describe properties such as the data type, variable group type, rank, dimensions, and number of time levels.
		```C++
		[<access>:]

		<data_type> <group_name>[[<number>]] [TYPE=<group_type>] [DIM=<dim>] [TIMELEVELS=<timelevels>] [SIZE=<size>] [DISTRIB=<distribution_type>] [GHOSTSIZE=<ghostsize>] [TAGS=<tags>]
		{
			<variable_name>,  <variable_name>,  <variable_name>
		} ["<group_description>"]
		```
		- Currently, `<group_name>` and `<variable_name>` must be distinct.
		- `<access>` There are three different access levels available for variables.
			- Public: Can be 'inherited' by other implementations.
			- Protected: Can be shared with other implementations which declare themselves to be friends of this one.
			- Private: Can only be seen by this thorn.
			- By default, all groups are private.
		-  `<data_type>` Cactus defines its own data types for thorns. 
			-  CCTK_INT
			-  CCTK_REAL
			-  CCTK_COMPLEX
			-  The motivation to provide Cactus data types comes from the fact that there is not a standard size for data types across all platforms. Providing Cactus-specific data types allows the framework to maintain an explicit variable size across all platforms, and provides maximum code portability. In addition it allows users to select the size of these standard types at build time across all thorns.
		- `<number>` If present, indicates that this is a vector group.
		- `<group_type>` Groups can be either scalars, grid functions (GFs), or grid arrays.
			-  SCALAR: This is just a single number.
			-  GF: This is the most common group type. A GF is an array with a specific size, set at run time in the parameter file, which is distributed across processors. All GFs have the same size, and the same number of ghostzones. Groups of GFs can also specify a dimension, and number of timelevels.
			-  ARRAY: This is a more general form of the GF. Each group of arrays can have a distinct size and number of ghostzones, in addition to dimension and number of timelevels. The drawback of using an array over a GF is that a lot of data about the array can only be determined by function calls, rather than the quicker methods available for GFs.
		-  `<dim>` DIM defines the spatial dimension of the ARRAY or GF. 
			-  The default value is `DIM=3`.
		-  `<timelevels>` TIMELEVELS defines the number of timelevels a group has if the group is of type ARRAY or GF. 
			-  The default is one timelevel.
		-  `<size>` A Cactus grid function or array has a size set at runtime by parameters. 
			- This size can either be the global size of the array across all processors (`DISTRIB=DEFAULT`), or, if `DISTRIB=CONSTANT`, the specified size on each processor. If the size is split across processors, the driver thorn is responsible for assigning the size on each processor.
		- `<ghostsize>` Cactus is based upon a distributed computing paradigm. That is, the problem domain is split into blocks, each of which is assigned to a processor. For hyperbolic and parabolic problems the blocks only need to communicate at the edges. 
			- It defaults to zero.
		- `<tags>` TAGS defines an optional string which is used to create a set of key-value pairs associated with the group. The keys are case independent. The string (which must be deliminated by single or double quotes) is interpreted by the function ``Util_TableSetFromString()``.
	- Cactus variables are used instead of local variables for a number of reasons
		- Cactus variables can be made visible to other thorns, allowing thorns to communicate and share data.
		- Cactus variables can be distributed and communicated among processors, allowing parallel computation.
		- A database of Cactus variables, and their attributes, is held by the flesh, and this information is used by thorns, for example, for obtaining a list of variables for checkpointing.
- Function