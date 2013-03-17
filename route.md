#Routing for Reborn CMS

Router is control of any request at Reborn CMS. Router check the module, controller, action, params from request url. And then call the right controller, action with params.


##Where I can add route source code?

You can add Route source at your module's root folder, filename with **routes.php**.

Example : Route file path for Pages module. This is route path for Core Module.

	..\reborn\heart\module\Pages\routes.php;

Example : Route file path for Addon Module.

	..\reborn\content\modules\ModuleName\routes.php;



**Defining A Route**
* @param string $name Route name
* @param string $path Route uri path
* @param string $file Action string(Module\Controller::action) [eg: Pages\Pages::index]
* @param string $method HTTP method (optional)

	// url is http://example.com/login
	Route::add('login', 'login', 'User\User::login');
	// or
	// route for http://example.com/login with POST method
	Route::add('login', 'login', 'User\User::login', 'POST');

**Defining A Route for GET method**

	// url is http://example.com/pages/1234
	Route::get('pages_by_id', 'pages/{:id}', 'Pages\Pages::getBy');

**Defining A Route for POST method**

	// url is http://example.com/pages/create
	Route::post('pages_create', 'pages/create', 'Pages\Pages::create');

**Defining A Route for PUT method**

	// url is http://example.com/pages/123 with PUT method
	Route::put('pages_edit', 'pages/{int:id}', 'Pages\Pages::edit');

**Defining A Route for DELETE method**

	// url is http://example.com/pages/123 with DELETE method
	Route::put('pages_delete', 'pages/{int:id}', 'Pages\Pages::delete');

**Supproted parameter type are**

	{int:key} // Key is Integer value
	{alpha:key} // Key is Alpha, '-', '_' and '.'
	{alnum:key} // Key is Alpha, numeric, '-', '_' and '.'


