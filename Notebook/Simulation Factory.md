## Simulation Factory

The Simulation Factory provides capabilities for compiling and deploying a Cactus application on machines and ging simulations.

The Simulation Factory is typically placed into a `simfactory` folder inside a Cactus source tree.

## Initial Setup

The Simulation Factory contains a database known as the Machine Database. This collection of information describes all the aspects that are unique about each individual HPC system, so that the Simulation Factory can provide a common interface for all systems that hides these differences.

The Machine Database consists of different sections, one for each machine. The section name is given in square brackets, e.g. `[comet]`. There is a special section `[default]` that provides default values for those properties that are not explicitly set in the machine-specific entries.

The command

```bash
./simfactory/bin/sim setup-silent
```

will generate a machine database entry for your local machine.

You can add, change, or overwrite it under the file `simfactory/etc/defs.local.ini`.

The command

```bash
./simfactory/bin/sim list-machines
```

outputs a list of all preconfigured machines that the Simulation Factory knows about.

## Extended Local Workstation Configuration

Once determining the hostname of your machine through the command:

```bash
hostname
```

Then edit `simfactory/mdb/machines/<hostname>.ini`.

## Building Cactus Configuration

### Information Commands

To list all existing Cactus configurations, use the following command

```bash
./simfactory/bin/sim list-configurations
```

### Building a Configuration

To build a configuration, four pieces of information are required:

- Thorn list
	- This defines which thorns are to be included into the configuration.
	- Override: `--thornlist=<thornlist>`
- Option List
	- This specifies the compiler and build options that need to be used to build Cactus on a particular system.
	- Override: `--optionlist=<optionlist>`
- Submission Script
	- This specifies how to submit a job to the queueing system on a particular system.
	- Override: `--submitscript=<submitscript>`
- Run Script
	- This specifies to how execute an MPI process on a particular system; it is closely connected to the submission script.
	- Override: `--runscript=<runscript>`

To build a configuration with a specific thornlist, issue the following command:

```bash
./simfactory/bin/sim build [<configurationname>] --thornlist=<thornlist>
```

If you choose to omit the configuration name, it will default to `sim`.

The Simulation Factory provides default scripts for all its preconfigured machines. These scripts can be found in `simfactory/mdb`

### Additional Options

- `--reconfig`
	- Reconfigure before building, i.e. re-examine the configuration options and re-run the CST stage. This happens automatically when the option list changes.
- `--clean`
	- Clean the configuration (remove all object files etc.) before building.

## Managing Simulations

The status of all simulations on a particular machine can be seen with the following command

```bash
./simfactory/bin/sim list-simulations
```

If a more detailed look at each simulation is required, the verbose option can be specified

```bash
./simfactory/bin/sim list-simulations --verbose
```

### Submitting a Simulation

Four primary pieces of information are necessary when submitting a simulation to the host queuing system. They are

- Configuration
	- The Cactus configuration to run
	- option: `--configuration`
	- default: `sim`
- Parfile
	- The Cactus parameter file to use
	- option: `--parfile`
- Walltime
	- The total amount of wall time required
	- option: `--walltime`
	- default: MDB Key maxwalltime
- Processors
	- The total number of processors to use
	- option: `--procs`
	- default: 1

Here is an example of submitting a simulation named `static_tov` using the configuration `sim` and the aforementioned options:

```bash
./simfactory/bin/sim submit static_tov --configuration sim --parfile=par/static_tov.par --walltime=4:00:00 --procs=8
```

If `--configuration <configuration>` is omitted, the default `sim` configuration is used.

### Additional Options: Submission

- Processors per node
	- The number of processors per node requested from the queueing system
	- option: `--ppn`
	- default: all processors on a node
- Number of OpenMP Threads
	- The number of OpenMP threads per MPI process. (You specify the total number of processors (cores), and the number of OpenMP threads; the number of MPI processes is then calculated automatically.)
	- option: `--num-threads`
	- default: 1 (as if OpenMP was not used)

### Running a Simulation

The Simulation Factory can execute a simulation directly, bypassing the queuing system. Running a simulation directly uses the same options, but ignores wall time limit etc. You use the run command for this:

```bash
./simfactory/bin/sim run static_tov --configuration sim --parfile=par/static_tov.par --procs=8
```

### Other Simulation Commands

- To stop a simulation:
	```bash
	./simfactory/bin/sim stop <simulationname>
	```
- To purge an existing simulation:
	```bash
	./simfactory/bin/sim purge <simulationname> [--restart-id=<restartid>]
	```
- To show the current output (`stdout` and `stderr`) for a given simulation:
	```bash
	./simfactory/bin/sim show-output <simulationname> [--restart-id=<restartid>]
	``` 
	
## Output

When a simulation is submitted for the first time, all necessary information from the Cactus build configuration is brought into a specific simulation folder. Contained inside this folder, which has the same name as the specified simulation, are the executable, run script, submit script, a SIMFACTORY folder, a log file, and the output directories for each individual restart.

> Simulations are self-contained, and once created do not rely on outside information.

The SIMFACTORY folder contains the executable, the necessary script files for submission and execution, and a `properties.ini` file that is used by the Simulation Factory to store information about the simulation.

Each time a simulation is either run or submitted, a restart directory is created underneath the simulation directory. This restart folder has a name of the format "output-####", starting with "output-0000".