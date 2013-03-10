#Class Alias Library for Reborn CMS

**namespace** - Reborn\Cores

Please write something for this class Ko Nyan Lynn Htut

##How to use Alias Class

###coreClassAlias()

This method is call when application started. But not allow to call after one time.

**Code Sample**

	$alias = new \Reborn\Cores\Alias();
	$alias->coreClassAlias();
	
	
###aliasRegister()

Register the class alias. You can use your class (enternal of Reborn's Cores) to alies use this method.

* *(Array)* Array data for class alias

**Code Sample**

	$alias = new \Reborn\Cores\Alias();
	$alias->aliasRegister();












