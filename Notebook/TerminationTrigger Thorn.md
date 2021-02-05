## TerminationTrigger Thorn

This thorn watches the elapsed walltime. If only n minutes are left before the some limit set by the user, it triggers termination of the simulation.

## Parameter

- Walltime in HOURS allocated for this job
	```c
	TerminationTrigger::max_walltime = 1
	```
- When to trigger termination in MINUTES. The rest of the time is for a checkpoint written.
	```c
	TerminationTrigger::on_remaining_walltime = 30
	```
- Output remaining wall time every n minutes
	```c
	TerminationTrigger::output_remtime_every_minutes = 0 # No output
	```
- Create a file called `terminate.txt`. If you add a `1` to this file, Cactus will terminate immediately.
	```c
	TerminationTrigger::termination_from_file   = yes
	TerminationTrigger::termination_file        = "terminate.txt"
	TerminationTrigger::create_termination_file = yes
	```
	Example
	```bash
	echo "1" >> terminate.txt
	```

## Developer

- Christian D. Ott