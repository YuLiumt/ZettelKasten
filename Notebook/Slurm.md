## Slurm

Users submit jobs, which are scheduled and allocated resources (CPU time, memory, etc.) by the resource manager. Slurm is a resource manager and job scheduler designed to do just that, and much more.

## Gathering information

Slurm offers many commands you can use to interact with the system. For instance, the `sinfo` command gives an overview of the resources offered by the cluster, while the `squeue` command shows to which jobs those resources are currently allocated.

By default, `sinfo` lists the partitions that are available. A partition is a set of compute nodes grouped logically.

```bash
$ sinfo
PARTITION AVAIL TIMELIMIT NODES STATE  NODELIST
```

The `squeue` command shows the list of jobs which are currently running

```bash
$ squeue
JOBID PARTITION NAME USER ST  TIME  NODES NODELIST(REASON)
```

To cancel a job, you would use `scancel <JOBID>`.

## Creating a job

A job consists in two parts: resource requests and job steps. Resource requests consist in a number of CPUs, computing expected duration, amounts of RAM or disk space, etc. Job steps describe tasks that must be done, software which must be run.

The typical way of creating a job is to write a submission script. A submission script is a shell script, e.g. a Bash script, whose comments, if they are prefixed with SBATCH, are understood by Slurm as parameters describing resource requests and other submissions options. You can get the complete list of parameters from the sbatch manpage `man sbatch`.

> The `SBATCH` directives must appear at the top of the submission file, before any other line except for the very first line which should be the shebang (e.g. `#!/bin/bash`).

For instance, the following script, hypothetically named `submit.sh`,

```bash
#!/bin/bash
#SBATCH --ntasks=1
#SBATCH --time=10:00
#SBATCH --mem-per-cpu=100

srun hostname
srun sleep 60
```
would request one CPU for 10 minutes, along with 100 MB of RAM, in the default queue. When started, the job would run a first job step `srun hostname`, which will launch the UNIX command `hostname` on the node on which the requested CPU was allocated. Then, a second job step will start the `sleep` command. 

Once the submission script is written properly, you need to submit it to slurm through the `sbatch` command

```bash
$ sbatch submit.sh
sbatch: Submitted batch job 99999999
```

## Going parallel

[[Parallel Calculations]]

There are several ways a parallel job

- by running a multi-process program (e.g. with MPI)
- by running a multithreaded program (shared memory paradigm, e.g. with OpenMP)

In the Slurm context, a task is to be understood as a process. So a multi-process program is made of several tasks. By contrast, a multithreaded program is composed of only one task, which uses several CPUs.

Tasks are requested/created with the `--ntasks` option, while CPUs, for the multithreaded programs, are requested with the `--cpus-per-task` option. Tasks cannot be split across several compute nodes, so requesting several CPUs with the `--cpus-per-task` option will ensure all CPUs are allocated on the same compute node. 

## Monitoring your jobs

Making sure your jobs use the right amount of RAM and the right number of CPUs.

The easiest way to check the instantaneous memory and CPU usage of a job is to ssh to a compute node your job is running on.


- Task and CPU usage stats
- Memory usage stats
	- The resident set size (RSS) is the amount of space of physical memory (RAM) held by a process. If the full amount of space required by a process exceeds the RSS, the remaining portion is typically stored in swap.
- Disk usage stats

 A summary of used resources

- Task and CPU usage stats
	- `AllocCPUS`: Number of allocated CPUs.
	- `NTasks`: Total number of tasks in a job or step.
	- `MinCPU`: Minimum CPU time of all tasks in job (system + user).
	- `MinCPUTask`: The task ID where the mincpu occurred.
	- `AveCPU`: Average CPU time of all tasks in job (system + user)
	- `Elapsed`: The jobs elapsed time
	- `ExitCode`: The exit code returned by the job script.
- Memory usage stats
	- `MaxRSS`: Maximum resident set size of all tasks in job.
	- `MaxRSSTask`: The task ID where the maxrss occurred.
	- `AveRSS`: Average resident set size of all tasks in job.
	- `MaxPages`: Maximum number of page faults of all tasks in job.
	- `MaxPagesTask`: The task ID where the maxpages occurred.
	- `AvePages`: Average number of page faults of all tasks in job.
- Disk usage stats
	- `MaxDiskRead`: Maximum number of bytes read by all tasks in job
	- `MaxDiskReadTask`: The task ID where the maxdiskread occurred.
	- `AveDiskRead`: Average number of bytes read by all tasks in job.
	- `MaxDiskWrite`: Maximum number of bytes written by all tasks in job.
	- `MaxDiskWriteTask`: The task ID where the maxdiskwrite occurred.
	- `AveDiskWrite`: Average number of bytes written by all tasks in job.


Slurm records statistics for every job, including how much memory and CPU was used.

```bash
seff <jobid>
seff-array <jobid>
```