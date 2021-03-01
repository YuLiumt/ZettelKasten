## Linux

Linux is an operating system (OS). 
Without the operating system, the software wouldn't function.

The Linux operating system comprises several different pieces:
- **Bootloader** - The software that manages the boot process of your computer.
- **Kernel** - The kernel is the core of the system and manages the CPU, memory, and peripheral devices.
- **Init system** - This is a sub-system that bootstraps the user space and is charged with controlling daemons.
- **Daemons** - These are background services (printing, sound, scheduling, etc.) that either start up during boot or after you log into the desktop.
- **Graphical server** - This is the sub-system that displays the graphics on your monitor.
- **Desktop environment** - This is the piece that the users actually interact with.
- **Applications** - Linux offers high-quality software.

## Shell

So, basically, a shell is a program that receives commands from the user and gives it to the OS to process, and it shows the output.

The most well-known being BASH.

## Commands

- **find** - Locate files within a given directory
	```bash
	$ find . -name "*.c"
	```
- **grep** - Search for a string of characters in a specified file
	```bash
	$ grep <pattern> <file>
	```
	- Using Grep to Filter the Output of a Command
		```bash
		$ history | grep <pattern>
		```
- **which**
- **whereis**
- **top** - Display Linux processes
	```bash
	$ top [-U $USER]
	```
	- `-U`: Display specific User process details.
	- load average: These numbers tell you how busy your system's CPU
	- TASK and CPU States
		- **us**: time running user processes
		- **sy**: time running kernel processes
		- **id**: time spent in the kernel idle handler
		- **wa**: time waiting for I/O completion
	- MEMORY Usage
		- Changing the numeric units with the `E` interactive command.
	- the process list
		- **PID**: Process ID.
		- **USER**: The owner of the process.
		- **S**: Status of the process.
		- **%CPU**: The share of CPU time used by the process since the last update.
			- If a process is multi-threaded and top is not operating in Threads mode, amounts greater than $100\%$ may be reported. You toggle Threads mode with the `H` interactive command.
		- **%MEM**: The share of physical memory used.
- **scp** - Transfer files and directories across the systems securely over the network.
	```bash
	$ scp -r [-l <num>] <user@host>:<folder> <folder>
	```
	- `-r`: Copy files and directories recursively
	- `-l`: Limit the bandwidth while copying, specified in `<num> Kbit/s` .
- **rsync** - Transfer just the differences between two sets of files across the  network
       connection
	```bash
	$ rsync -av [--progress] [--delete] [--exclude=<pattern>] <user@host>:<folder> <folder>
	```
	- `-v`: verbose
	- `-a`: archive mode, archive mode allows copying files recursively and it also preserves symbolic links, file permissions, user & group ownerships and timestamp
	- `--exclude`: Specify those files or directories which you want to exclude
	- `--delete`: Delete files that are not there in source directory.
	- `--progress`: Show progress during transfer
- **tail** - Sometimes you want to monitor what new information is being written to a file (i.e. log file).
	```bash
	$ tail [-n <num>] [-f] <file>
	```
	- `-f`:  This option shows the last ten lines of a file and will update when new lines are added.
	- `-n`: Prints the last `<num>` lines instead of last 10 lines.
- **du** - Summarize disk usage of the set of `<FILEs>`, recursively for directories.
	```bash
	$ du -h [-s] [-d <n>] <FILEs>
	```
	- `-h`: Print sizes in human readable format
	- `-s`: Display only a total
	- `-d`: print the total for a directory only if it is `<n>` or fewer levels below the command line argument.
- **free** - Check information about the RAM usage by your system
	```bash
	$ free -h
	```
	- `-h`: Show human-readable output
- **lfs** -  To display disk usage and limits for a user.
	```bash
	$ lfs quota -uh $USER ~
	```
- **unzip** - Unzip a ZIP File
	```bash
	$ unzip <FILEs>
	```

## Memory Management

Memory management is a form of resource management applied to computer memory. The essential requirement of memory management is to provide ways to dynamically allocate portions of memory to programs at their request, and free it for reuse when no longer needed.

### Swapping

Swapping is a mechanism in which a process can be swapped temporarily out of main memory (or move) to secondary storage (disk) and make that memory available to other processes. At some later time, the system swaps back the process from the secondary storage to main memory.