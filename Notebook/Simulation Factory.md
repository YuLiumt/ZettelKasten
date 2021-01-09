## Simulation Factory

- [Homepage](http://simfactory.org)
-   [Documentation](https://svn.cct.lsu.edu/repos/numrel/simfactory2/www/info/documentation/userguide/index.html#)

The Simulation Factory provides capabilities for compiling and deploying a [[Cactus]] application on machines and ging simulations.

Note that it is included with the [[Einstein Toolkit]], so if you are using the toolkit, you probably already have it in the directory `Cactus/simfactory`.

## Machine Database

The Simulation Factory contains a database known as the Machine Database. This collection of information describes all the aspects that are unique about each individual HPC system. This allows everybody (including new users) to quickly build the application on every supported system.

The command

```bash
./simfactory/bin/sim list-machines
```

outputs a list of all preconfigured machines that the Simulation Factory knows about.

## Initial Setup

The command

```bash
./simfactory/bin/sim setup
```
will prompt for a username, an email address, and an allocation. You can add, change, or overwrite it under the file `simfactory/etc/defs.local.ini`. 

If you are using a preconfigured machine, then you can skip the Configuration process.

> Generally, configuring SimFactory means providing an optionlist, for specifying library locations and build options, a submit script for using the batch queueing system, and a runscript, for specifying how Cactus should be run, e.g. which mpirun command to use. 
> 
> If you are running SimFactory on an unsupported supercomputer,, these steps typically cannot be performed automatically and require user input.

## Configure the Simulation Factory

If you are running SimFactory on an unsupported supercomputer, the `setup` command will create a new machine definition for the local machine in `simfactory/mdb/machines`. 

### Machine Definitions

Once determining the hostname of your machine through the command:
```bash
hostname
```
Then edit `simfactory/mdb/machines/<hostname>.ini` and set various options for this new machine.

```txt
# Source tree management
hostname        =
basedir         =
sourcebasedir   = 

# Configuration
optionlist      = 
submitscript    = 
runscript       =

# sbatch
ppn             = 
max-num-threads = 
num-threads     = 
nodes           = 
queue           = 
maxwalltime     = 

# slurm
submit          = sbatch @SCRIPTFILE@
getstatus       = squeue -j @JOB_ID@
stop            = scancel @JOB_ID@
```

### Option List

This specifies the compiler and build options that need to be used to build Cactus on a particular system.

### Submission Script

Submission Script specifies how to submit a job to the queueing system on a particular system.

```bash
#! /bin/bash
#SBATCH -p @QUEUE@
#SBATCH -N @NODES@ -n @NUM_PROCS@
#SBATCH --cpus-per-task=@NUM_THREADS@
#SBATCH -t @WALLTIME@
#SBATCH @("@CHAINED_JOB_ID@" != "" ? "-d afterany:@CHAINED_JOB_ID@" : "")@
#SBATCH --export=ALL
#SBATCH -J @SHORT_SIMULATION_NAME@
#SBATCH --mail-type=ALL
#SBATCH --mail-user=@EMAIL@
#SBATCH -o @RUNDIR@/@SIMULATION_NAME@.out
#SBATCH -e @RUNDIR@/@SIMULATION_NAME@.err
cd @SOURCEDIR@
@SIMFACTORY@ run @SIMULATION_NAME@ --basedir=@BASEDIR@ --machine=@MACHINE@ --restart-id=@RESTART_ID@ @FROM_RESTART_COMMAND@
```

Submit scripts make use of several variables defined by SimFactory, such as the number of nodes required for a job, and the walltime to allocate. These definitions are refered to in the submit script using the `@DEF@` syntax, where DEF is the name of the definition. SimFactory converts the templated submit script into a real submit script by expanding these quantities.

### Run Script

Run Script specifies to how execute an MPI process on a particular system; it is closely connected to the submission script.

```bash
# Environment
export CACTUS_NUM_PROCS=@NUM_PROCS@
export CACTUS_NUM_THREADS=@NUM_THREADS@
export GMON_OUT_PREFIX=gmon.out
export OMP_NUM_THREADS=@NUM_THREADS@
export CACTUS_STARTTIME=$(date +%s)

# MPI
mpirun -np @NUM_PROCS@ @EXECUTABLE@ -L 3 @PARFILE@
```

Run scripts make use of several variables defined by SimFactory, such as the number of processors to run on, and the name of the parameter file to run. These definitions are refered to in the run script using the `@DEF@` syntax, where DEF is the name of the definition. SimFactory converts the templated run script into a real shell script by expanding these quantities.

## Building Cactus Configuration

To build a configuration, thornlist is required to define which thorns are to be included into the configuration. To do this, issue the following command:

```bash
./simfactory/bin/sim build [<configurationname>] --thornlist=<thornlist>
```

If you choose to omit the configuration name, it will default to `sim`.

To list all existing Cactus configurations, use the following command

```bash
./simfactory/bin/sim list-configurations
```

### Additional Options

- `--reconfig`
	- Reconfigure before building, i.e. re-examine the configuration options and re-run the CST stage. This happens automatically when the option list changes.
- `--clean`
	- Clean the configuration (remove all object files etc.) before building.

The Simulation Factory provides default scripts for all its preconfigured machines. These scripts can be found in `simfactory/mdb`. You can override it with

- `--optionlist`
- `--submitscript`
- `--runscript`

## Managing Simulations

Simulations are self-contained, and once created do not rely on outside information.

### Create a Simulation

A simulation can be created using the `create` command. SimFactory needs to know a name for the simulation as well as what parameter file to use.

```bash
./simfactory/bin/sim create [<simulationname>] [--configuration <configurationname>] --parfile=<parfile>
```

- If you don't specify a simulation name using the shorthand syntax, a simulation name will be derived from from the parameter file name.
- If `--configuration <configuration>` is omitted, the default `sim` configuration is used.

When a simulation is created, it copies the submit script and the run script from the build configuration into the folder `basedir/<simulationname>/SIMFACTORY`. The executable goes in the `exe/` folder, the run and submit scripts into the `run/` folder, the Cactus options list into the `cfg/` folder, and the parfile into the `par/` folder.

### Submitting a Simulation

The `submit` command submitted a new segment for the simulation to the queueing system.

```bash
./simfactory/bin/sim submit <simulationname>
```

Additional Options:

- Walltime
	- Maximum run time for your simulation.
	- option: `--walltime=<HH:MM:SS>`
	- default: MDB Key maxwalltime
- Processors
	- The total number of processors to use.
	- option: `--procs=<int>`
	- default: 1
- Queue
	- Queue to use for job submission
	- option: `--queue=<identifier>`
	- -   default: taken from the MDB
- Number of OpenMP Threads
	- The number of OpenMP threads per MPI process. (You specify the total number of processors (cores), and the number of OpenMP threads; the number of MPI processes is then calculated automatically.)
	- option: `--num-threads=<int>`
	- default: 1 (as if OpenMP was not used)
- Processors per node
	- The number of processors per node requested from the queueing system
	- option: `--ppn=<int>`
- Used processors per node
	- The number of processors per node that should actually be used, allowing under-using nodes even if the queueing system does not allow it. (The remaining processors will idle and will remain unused.)
	- option: `--ppn-used=<int> `

Each time a simulation is submitted, a restart directory is created underneath the simulation directory. This restart folder has a name of the format "output-####", starting with "output-0000". Contained inside the restart folder are several internal files, the output written to stdout and stderr from the simulation, and the simulation output itself.

The SIMFACTORY folder contains the executable, the necessary script files for submission and execution, and a `properties.ini` file that is used by the Simulation Factory to store information about the simulation.

### Running a Simulation

The Simulation Factory can execute a simulation directly, bypassing the queuing system. Running a simulation directly uses the same options, but ignores wall time limit etc. You use the run command for this:

```bash
./simfactory/bin/sim run <simulationname>
```

### Managing submitted simulations

- The status of all simulations on a particular machine can be seen with the following command
	```bash
	./simfactory/bin/sim list-simulations
	```
- To watch a simulation's log output (`stdout` and `stderr`) use the `show-output` command of simfactory.
	```bash
	./simfactory/bin/sim show-output [--follow] <simulationname> [--restart-id=<restartid>]
	``` 
	- Press `CTRL-C` if you wish to stop watching. You can leave out the `--follow` option if you would like to see all output up to this point.
- Simfactory offers a `stop` command to abort a running simulation.
	```bash
	./simfactory/bin/sim stop <simulationname>
	```
- Simulations that are no longer needed are removed using the `purge` command.
	```bash
	./simfactory/bin/sim purge <simulationname> [--restart-id=<restartid>]
	```

### Checkpoints

Currently simfactory stores the checkpoints for each restart in their own directory.

One solution to this would be for SimFactory to store the checkpoints in a directory above the output-NNNN directories and make the current checkpoints directories under output-NNNN symbolic links to the common directory. This way, all restarts would see the same directory for checkpoint files, and Cactus could clean up the old checkpoints.

SimFactory's philosophy is that each restart is independent of the other restarts.

One problem in long-running simulations is that (a) one may accidentally delete too many checkpoints, so that the simulation becomes unusable. Another problem is that, if an error in the simulation is detected and if all old checkpoints have been deleted, it is impossible to "go back in time".

### Running a simple example

You can now run the Einstein Toolkit with a simple test parameter file.

```bash
./simfactory/bin/sim create-run helloworld --parfile arrangements/CactusExamples/HelloWorld/par/HelloWorld.par
```

If you see

```
INFO (HelloWorld): Hello World!
```

anywhere in the above output, then congratulations, you have successfully downloaded, compiled and run the Einstein Toolkit!

## Test suites

Cactus thorns often contain regression tests consisting of test parameter files and the resulting output, and Cactus has a mechanism for verifying that the output of the parameter files with the current version of the code matches the output stored in the thorn.

- To run all tests immediately on two processors (cores):
	```bash
	./simfactory/bin/sim create-run mytests --testsuite --procs 2
	```
- To run the tests using a queuing system:
	```bash
	./simfactory/bin/sim create-submit mytests --testsuite --procs 2
	```
- By default, the entire test suite is run. If you want to run only specific tests, you can additionally use the `--select-tests` option.
	```bash
	./simfactory/bin/sim create-run mytests --testsuite --procs 2 --select-tests <arrangement>/<thorn>
	```

Whether run using create-run or create-submit, a `summary.log` file will be created in `mytests/output-xxxx/TEST/<configurationname>`

## Parameter file scripts

A parameter file script is a file with a `.rpar` extension which, when executed, generates a file in the same place but with a `.par` extension.

You can write a parameter file script in any language. We provide examples written in Python:

```python
#!/usr/bin/env python

import sys
import re
from string import Template

dtfac = 0.5

lines = """
Time::dtfac = $dtfac
"""

data = open(re.sub(r'(.*)\.rpar$', r'\1.par', sys.argv[0]), 'w')
data.write(Template(lines).substitute(locals()))
```

These parameter file scripts look like standard Cactus parameter files but with `$var` variable replacements (in this case for the `dtfac` variable).

Notes:
- If you want to use the Cactus `$parfile` syntax, you need to escape the `$`
	```python
	IO::out_dir = $$parfile
	```
- If you want to use SimFactory `@...@` replacements, you can use these directly in Python

## Developer

- Gabrielle Allen
- [[Erik Schnetter]]
- Michael Thomas

