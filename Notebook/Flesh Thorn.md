## Flesh Thorn



## Parameter

- Description of this simulation
	```c
	Cactus::cctk_run_title = "Description of this simulation"
	```
- Give detailed information for each warning statement
	```c
	Cactus::cctk_full_warnings = no
	```
	| Level | Description |
	| ----- | ------------ |
	| 0       | abort the Cactus run |
	| 1        | the results of this run will be wrong |
	| 2       | the user should know about this, but the problem is not terribly surprising |
	| 3       | this is for small problems that can probably be ignored, but that careful people may want to know about |
	| 4       | these messages are probably useful only for debugging purposes |
- Print the scheduling tree to standard output
	```c
	Cactus::cctk_show_schedule = yes
	```
- Provide runtime of each thorn
	```c
	Cactus::cctk_timer_output = "full"
	```
- Condition on which to terminate evolution loop
	```c
	Cactus::terminate = "time"
	Cactus::cctk_final_time = 100
	```
