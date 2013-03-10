#Profiler Class for RebornCMS

**namespace** - Reborn\Cores

This class will show profiles.

##How to use Profiler Class

###getTime()

Use this method when you want to know the current time in milisecond.

**Code Sample**

	//return value is String like 1000ms
	$profiler = new \Reborn\Cores\Profiler();
	$profiler->getTime();
	
	
###getMemory()

This method can be used to get memory usage.

**Code Sample**

	//return value is String like 1.1MB
	$profiler = new \Reborn\Cores\Profiler();
	$profiler->getMemory();