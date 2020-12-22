## Parallel Calculations

Threaded calculations must run on the same node, so you cannot specify more threads than there are cores on the node you use.

Normally, every processor/core reserved via Slurm is assigned to a separate MPI process. However, in the event that an application combines MPI (usually between nodes), and OpenMP (within nodes), different instructions need to be followed.

So if your multi-threaded calculation requests too much memory, you can reduce the memory usage by distributing the job over a smaller number of threads per process, and use more MPI processes.

- Set the number of MPI tasks you require by specifying the number of nodes (#SBATCH --nodes) and the number of MPI processes you desire per node (#SBATCH --ntasks-per-node) then specify the number of OpenMP threads per MPI process (#SBATCH --cpus-per-task).
- Set OMP_NUM_THREADS to the number of OpenMP threads to be created for each MPI process.

> Example:
> 
> This job will have 8 MPI processes (4 per node), each with 10 OpenMP threads for a total of 80 cores.
> ```bash
> #SBATCH --nodes=2                      # node count
> #SBATCH --ntasks-per-node=4    # total number of tasks per node
> #SBATCH --cpus-per-task=10       # cpu-cores per task (>1 if multi-threaded tasks)
> ```


- Example for an OpenMP job
	```bash
	# we ask for 1 task with 20 cores
	#SBATCH --nodes=1
	#SBATCH --ntasks-per-node=1
	#SBATCH --cpus-per-task=20
	```
- Example for a MPI job
	```
	#SBATCH --ntasks=80
	```
	
## MPI

Message Passing Interface

Designed for distributed memory	

## OpenMP

Open Multi-Processing
Completely independent from MPI
Limited by available memory

Designed for shared memory

OpenMP directives tell the compiler to add machine code for parallel execution of the following block
```C++
#pragma omp parallel
```

A process can create one or more threads

```C++
#include <omp.h> 
#include <stdio.h> 

int main(int argc, char *argv[]){ 

	printf("OpenMP running with %d threads\n", omp_get_max_threads()); 

#pragma omp parallel 
	{ 
		//Code here will be executed by all threads 
		printf("Hello World from thread %d\n", omp_get_thread_num()); 
	} 
		
	return 0; 
}
```

`OMP_NUM_THREADS` defines run time number of threads.

```bash
export OMP_NUM_THREADS=4
```

## Hybrid OpenMP & MPI

- MPI between nodes
- OpenMP within shared-memory nodes


- Saves memory by not duplicating data
- Minimize interconnect communication by only having 1 MPI process per node

```bash
#SBATCH --nodes=2
#SBATCH --ntasks-per-node=1
#SBATCH --cpus-per-task=24
#SBATCH --time=12:00:00

export OMP_NUM_THREADS=$SLURM_CPUS_PER_TASK
```