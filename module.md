#Module Class for RebornCMS

##How to use Module Class

###initialize()

Initialize method for module class

**Initializing**

	\Module::initialize();
	
	
###getAll()

Get the all modules

**Getting all modules**

	// return array
	\Module::getAll();
	
	
###getData()

Get module data by given module name

* *(String)* Name of modules

**Getting data**

	// this method will return array or null
	\Module::getData('media');
	

###exist()

Check the given module is exists or not

* *(String)* Name of Modules

**Checking Module**

	// return boolean
	\Module::exist('media');
	
	
###load()

Load the given module

* *(String)* Name of modules

**Loading Module**	

	// return void
	\Module::load('media');
	
	
###install()

Install the given module to DB table

* *(String)* slug of module(folder name)

* *(boolean)* set "true" to enable and "false" to disable. Default value is "false".

**Module Installation**

	\Module::install('media', true);
	

###uninstall()

UnInstall the given module to DB table

* *(String)* slug of module(folder name)

**Module Unstallation**

	\Module::uninstall('media');
	
	
###upgrade()

Upgrade the given module. 	
	
* *(String)* Name of the module

**Upgrading Module**

	\Module::upgrade('media');
	

###boot()

Boot the Module

* *(String)* Name of module

**Booting module**

	// return void
	\Module::boot('media');
	
	
###shutdown()

Shutdown the Module

* *(String)* Name of module

**Shuting down**

	\Module::shutdown('media');
	
	
###isCore()

Check the given module is core module or not.

* *(String)* Module Name(slug)

**Checking the module**

	// this method will return true if specific module is core and return false if not.
	\Module::isCore('media');
	
	
###enable()

Set the given module is enable.
 
* *(String)* Module name

**Enabling module**

	\Module::enable('media');
	
	
###disable()

Set the given module is disable.

* *(String)* Module name

**Disabling module**

	\Module::disbale('media');
	
	
###isEnable()

Check given module is enabled or not

* *(String)* Module name

* *(boolean)* If you set true, throw the Exception message

**Using isEnable method**

	\Module::isEnable('media');
	
	
###isDisable()

Check given module is disable or not

* *(String)* Module name

* *(boolean)* If you set true, throw the Exception message

**Using isDisable method**

	\Module::isDisable('media');
	

###checkModule()

Check the given module is truely or not.

> First - check the module is really exits

> Second - check the module's module.php file

> Third - check the module.php format is correct?

* *(String)* Module name

**Checking Module**

	\Module::checkModule('media');