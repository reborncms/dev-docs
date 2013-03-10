#Error Handler class for RebornCMS

**namespace** - Reborn\Cores

This class handle all exception errors.

##How to use Error Handler class

###register()

Register the error handler.

**Code Sample**

	$exceptions = new Reborn\Cores\ErrorHandler();
	$exceptions->register();
	
	
###exceptionHandler()

Handler for the Exception Error.

* *(Object)* The exception object

**Code Sample**

	// return will be meixed
	$exceptions = new Reborn\Cores\ErrorHandler();
	$exceptions->exceptionHandler();
	
	
###getTraceString()

Get Error Trace as a sting for Exception Handler

* *(array)* Traces Array

**Code Sample**

	// String value will be retuned
	$exceptions = new Reborn\Cores\ErrorHandler();
	$exceptions->getTraceString();
	
	
###errorHandler()

Error hanlder method

* *()* $errno

* *()* $errstr

* *()* errfile

* *()* $errline

**Code Sample**

	$exceptions = new Reborn\Cores\ErrorHandler();
	$exceptions->errorHandler();

	
	
	