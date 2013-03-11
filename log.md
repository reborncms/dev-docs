#Log class for RebornCMS

##Using Log class

###getLogger()

Get the Logger Object
 
**Getting Log Object**
	
	// this method will return log object
	\Log::getLogger();
	
	
###debug()

Debug Log method adpater

* *(mixed)* Message you want to logging

**Using debug method**

	\Log::debug("This is the debug test.");
	
	
###info()

Info Log method adpater

* *(mixed)* Message you want to logging

**Using info method**

	\Log::info('This is the info test');


###notice()

Notice Log method adpater

* *(mixed)* Message you want to logging

**Using notice method**

	\Log::notice('This is notice test.');
	
	
###warning()

Warning Log method adpater

* *(mixed)* Message you want to logging

**Using warning method**

	\Log::warning('Warning : this is warning test.');
	
	
###critical()

Message you want to logging

* *(mixed)* Message you want to logging

**Using critical method**

	\Log::critical('This is critical test.');
	
	
###alert()

Message you want to logging

* *(mixed)* Message you want to logging

**Using alert method**

	\Log::alert('This is alert test.');
	
	

###emergency()

Message you want to logging

* *(mixed)* Message you want to logging

**Using emergency method**

	\Log::alert('This is emergency test.');
