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
	find . -name "*.c"
	```
- **which**
- **whereis**
- **top** - For Memory usage, the number you are interested in is RES
- **scp**
	```bash
	scp -r -l 8192 yuliu@172.22.127.9:/home4/yuliu/ /Users/liuyu/
	```
- **rsync**
	```bash
	rsync -avu --progress --delete --exclude=\".*\" --exclude=\"__pycache__\" yuliu@172.22.127.9:/home4/yuliu/Desktop/Pylib/CactusTool/CactusTool /Users/liuyu/Desktop/CactusTool/
	```
- **tail** - Sometimes you want to monitor what new information is being written to a file (i.e. log file).
	```bash
	tail -n <num> -f <file>
	```
	- `-f`:  This option shows the last ten lines of a file and will update when new lines are added.
	- `-n`: Prints the last `<num>` lines instead of last 10 lines.
