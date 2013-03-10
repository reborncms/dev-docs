#Config Class for Reborn Theme?

How to get the config data?

	Config::get('app.lang');
	// return 'en'

**app.lang** is config key lang from the app.php config file from the **appdata/config/**

Example config is :

	// file name is example.php
	return array(
			'cache' => true,

			'cache_data' => array(
					'expire' => 60,
					'path' => '../somepath/from/here/'
				),
		);

	Config::get('example.cache'); // return true
	Config::get('example.cache_data.expire') // return 60
	Config::get('example.cache_data.path') // return ../somepath/from/here/

**Config from the module**

	//PagesModule/config/pages.php file
	return array(
		'title' => 'This is my page',
		'creator' => array(
				'name' => 'Nyan Lynn Htut',
				'website' => 'http://example.com'
			),
		);

	\Config::get('pages::pages.creator.name');
	// This will return Nyan Lynn Htut
	// Prefix with "modulename::"


