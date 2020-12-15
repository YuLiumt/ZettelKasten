## SystemStatistics Thorn

Cactus processes take a certain amount of memory, and if this exceeds the memory available on the system, the Cactus process will either start to swap, significantly reducing performance, or will terminate. It can be useful to determine quantities such as memory usage of a Cactus process, and that is the purpose of this thorn.

## Output

Collects information about the system on which a Cactus process is running can be output and reduced using the standard Cactus methods such as IOBasic and IOScalar.

- IOBasic
	```
	IOBasic::outInfo_every      = 256  
	IOBasic::outInfo_reductions = "minimum maximum"  
	IOBasic::outInfo_vars       = "SystemStatistics::maxrss_mb"
	```
- IOScalar
	```txt
	IOScalar::outScalar_every      = 256  
	IOScalar::outScalar_reductions = "minimum maximum average"  
	IOScalar::outScalar_vars       = "SystemStatistics::process_memory_mb"
	```


