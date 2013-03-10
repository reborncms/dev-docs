#Router Class for Reborn CMS

##How to use Router Class

###activeModule()

Get the active module.

**Code Sample**
	
	// the method will return the name of actie module
	$moduleName = \Router::activeModule();
	dump($moduleName);
	
	
###activeController()

Get the active controller.

**Code Sample**

	// this method will return the name of active controller
	$controllerName = \Router::activeController();
	dump($controllerName);
	
	
###activeMethod()

Get the active Method.

**Code Sample**

	// this method will return the name of active method
	$methodName = \Router::activeMethod();
	dump($methodName);
	

###params()

Get the active method's params.

**Code Sample**	

	// this method will return all parameters of active method in array
	$parameters = \Router::params();
	dump($parameters);
	

###param()

Get the active method's param by name.

**Code Sample**	

	// this method will return parameter of active method in array
	$parameter = \Router::param($key);
	dump($parameter);

	
###dispitch()

Dispatch the route for Reborn CMS

**Code Sample**

	\Router::dispitch();
	
	
	
	


	