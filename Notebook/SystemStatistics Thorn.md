## SystemStatistics Thorn

The SystemStatistics thorn produces output files for simulation statistics such as memory and swap usage.

Cactus processes take a certain amount of memory, and if this exceeds the memory available on the system, the Cactus process will either start to swap, significantly reducing performance, or will terminate. It can be useful to determine quantities such as memory usage of a Cactus process, and that is the purpose of this thorn.

## Output

Collects information about the system on which a Cactus process is running can be output and reduced using the standard Cactus methods such as IOBasic and IOScalar.

- IOBasic
	```python
	IOBasic::outInfo_vars = "SystemStatistics::maxrss_mb
							 SystemStatistics::swap_used_mb"
	```
- IOScalar
	```txt
	IOScalar::outScalar_vars = "SystemStatistics::process_memory_mb"
	```

## Memory Allocation Information (mallinfo)

- `arena` The total amount of memory allocated by means.
- `ordblks` The number of ordinary free blocks.
- `hblks` The number of blocks currently allocated
- `hblkhd` The number of bytes in blocks currently allocated
- `uordblks` The total number of bytes used by in-use allocations.
- `fordblks` The total number of bytes in free blocks.
- `keepcost` The total amount of releasable free space at the top of the heap.

## Developer

- Ian Hinder
