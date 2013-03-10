#Routing for Reborn CMS

##How to add route for your Module?

Reborn's route is require 3 parameter.

* First param is route name.
* Second param is route pattern.
* Third param is route map.

##Where I can add route source code?

You can add Route source at your module's root folder, filename with **routes.php**.

Example : Route file path for Pages module. This is route path for Core Module.

	..\reborn\heart\module\Pages\routes.php;

Example : Route file path for Addon Module.

	..\reborn\content\modules\ModuleName\routes.php;

**Defining A Route**

	// url is http://example.com/artice/create
	Route::add('article.create', 'artice/create', array(
			'module' => 'articel',
			'controller' => 'article',
			'action' => 'create',
		));

**Defining A Route with Closure**

	// url is http://example.com/pages/1234
	Route::add('pagesbyID', 'pages/type/{:id}', function($id){
		echo 'Page bi ID '.$id;
	});

**Defining A Route parameter by type**

	// url is http://example.com/pages/2013/01
	Route::add('article.archive', 'article/{int:year}/{int:month}', array(
			'module' => 'articel',
			'controller' => 'article',
			'action' => 'archive',
		));

**Supproted parameter type are**

	{int:key} // Key is Integer value
	{alpha:key} // Key is Alpha, '-', '_' and '.'
	{alnum:key} // Key is Alpha, numeric, '-', '_' and '.'


