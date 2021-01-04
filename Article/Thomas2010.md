## Simulation Factory: Taming Application Configuration and Workflow on High-End Resources

- **Author**: Thomas M W, [[Erik Schnetter]]
- **Summary**:
	- We introduce the Simulation Factory, a high-level interface to managing source code, accessing remote systems, and performing simulations.
- **Link**: [[Einstein Toolkit]], [[Simulation Factory]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2010arXiv1008.4571T) Thomas M W, Schnetter E. Simulation Factory: Taming Application Configuration and Workflow on High-End Resources. arXiv:1008.4571.

___

## Highlight

- To effectively begin using high performance computing (HPC), one has to overcome a set of unique technical challenges.
	- Using HPC systems to perform simulations is similarly a complex task. These systems are run in batch mode, where one has to prepare a shell script that runs the actual code, and then submit this script to a batch system. After some time (hours or days), the script is executed, and its output and error messages are returned to the user. It goes without saying that debugging such scripts is very time consuming due to the long turn-around time and any user error can delay a simulation project by several days.
	- To add insult to injury, the maximum possible run times in such queuing systems are usually measured in hours, and not more than two days at best. To deal with this, a simulation has to checkpoint itself before its queue time runs out and then restart when it receives another time slot in the batch system.
	- If one uses a large number of nodes, there is an increased chance of system failures that will also require checkpointing and restarting.
	- Dealing with queuing systems can be very stressful for human beings because even small errors can invalidate or destroy weeks of simulation results.
- The machine database describes properties of each machine so that SimFactory can provide a resource-agnostic user interface.
	- The Machine Database is comprised of a set of entries with predefined keys, separated into sections with unique names for each machine.
	- The databases are located in the SimFactory source tree inside the `etc` folder.

## Cactus Software Framework

Cactus is an open-source, modular, and portable programming environment for collaborative high performance computing (HPC).

The Cactus code base is structured as a central part, called the flesh that provides core routines, and components, called thorns. The flesh is independent of all thorns and provides the main program, which parses the parameters and activates the appropriate thorns, passing control to thorns as required. By itself, the flesh does not do any science; to do any computational task the user must compile in thorns and activate them at runtime.

A thorn is the basic working component within Cactus. All user-supplied code goes into thorns, which are, by and large, independent of each other. Thorns communicate with each other via calls to the flesh API or, more rarely, custom APIs of other thorns. The connection from a thorn to the flesh or to other thorns is specified in configuration files that are parsed at compile time and used to generate glue code that encapsulates the external appearance of a thorn. At runtime, the executable reads a parameter file that details which thorns are to be active and specifies values for the control parameters for these thorns.

## Simulation Factory

SimFactory addresses three main goals: 

- source code management
	- it is important to keep track of the different versions and modifications of the application source tree. It is usually not possible to use version control systems at this stage.
- configuring and building simulations
	- Before running simulation one has to configure and build an executable from the source tree.
		- These steps typically cannot be performed automatically and require user input; often, a complex set of inter-dependent configuration variables has to be set. In fact, this step is often so complex that only experts are able to configure and build an application on a particular system even if the applications themselves are portable.
		- System-level tools such as rpm or apt are not provided on HPC systems, and cannot be installed by end-users.
		- Most HPC systems allow user-level configuration tools such as Environment Modules. These packages allow users to choose between several installed software versions, and will ensure that all enabled software packages are compatible with each other.
		- What this all amounts to is that one has to carefully study a system’s documentation and perform careful experiments to find good, working configuration options.
	- SimFactory stores the complete configuration information for every machine in its machine database. This allows everybody (including new users) to quickly build the application on every supported system.
		- This approach is in contrast to a design where the simulation factory would pick up bits and pieces of configuration information automatically from the host system and would then combine the configuration information by itself; this approach lacks the "seal of approval" that exists in the current approach.
		- Given the complexity of identifying a correct set of configuration information for a particular system, where even small details can uncover compiler errors or lead to inconsistencies between different libraries, such a seal of approval is crucially important.
		- The disadvantage is that this approach does not scale well - it requires one maintainer per application per supported system.
	- The Cactus framework supports building multiple executables from the same source trees.
		- Each of these executables is called a configuration, since they differ in the configuration settings that were used to create them.
		- These configuration settings include a thorn list (list of components that should be included into the configuration), and a set of high-level build options such as debug, optimise, or profile. These configurations have different names, allowing the user to specify which configuration to use when performing a simulation.
- managing and executing simulations
	- Once a configuration has been created, SimFactory provides functionality for performing simulations, either by submitting and managing jobs via a job queueing system, or by directly running the executable.
		![[Pasted image 20210102143052.png]]
		- The first step is to create a simulation, which captures an executable, a parameter file, as well as any other parameters that determine the physical result of the simulation. This does not actually start the simulation.
		- To make progress with the simulation, one either submits or runs a restart. This requires choosing incidental parameters, such as the number of processes, wall time limit, allocation/queue names, etc.
		- After the restart finishes, it is cleaned up, which may consist of minor actions such as correcting file permissions, or deleting unnecessary or broken files, or may e.g. automatically archive simulation results.
		- A simulation may consist of arbitrarily many restarts. Presumably, each restart continues where the previous restart left off.
	- In detail, the simulation factory performs the following actions:
		- create and populate a directory structure for the simulation;
		- copy all executables, parameter files, and input files to save them from accidental modification;
		- manage checkpoint files, and/or ensure the correct checkpoint files are used when restarting;
		- use and/or create unique identifiers for simulations and restarts, so that output files can be tagged pointing back to the exact simulation;
		- automatically archive simulations and restarts, since files on HPC systems are often automatically deleted after some time;
		- clean up in various minor but convenient ways, e.g. correct file permissions or delete unnecessary output files.

One unique challenge SimFactory addresses is how to manage multiple stages of a single simulation, whether the stage represents a fresh start or a recovery from a previously interrupted simulation. To address this, SimFactory contains an abstraction called restart. A restart encapsulates several key operations:

- create
	- Before a simulation can be submitted or executed, it must be created. This process initializes any required configuration parameters, directories, and any other infrastructure necessary to facilitate submission or execution.
- submit
	- The submit operation submits the simulation to the queueing system of the host system. A shell script file is the command that is sent for submission. This script contains the necessary options to initialize the queueing system correctly, such as choosing the correct wall time, and then commands calling the SimFactory run operation. This submit operation does not contain any execution logic.
- run
	- The run operation is where all execution logic lives. The run command is capable of launching simulations that have either been submitted in a queuing system, or are executed directly, without the use of a queueing system. The ability to execute a simulation directly is necessary for running small simulations on a local workstation or notebook.
