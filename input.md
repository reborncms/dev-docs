#Input Class for Reborn CMS

Input class is get the value from the HTTP request.

##How to use Input Class

**Get the Input Mdthod**

	// Return the HTTP request method
	Input::method();

**Check the Input Method is POST or Not, GET or Not**

	// return true if request method is POST
	Input::isPost();

	if (Input::isGet()) {
		echo 'This is GET method'.
	}

**Get the Input value**

Input::get() method will return base on request method(GET or POST).
First param is key name and second is default value. When key is not isset in request, return default value. If you use first param only, return **null**.

	// First param is key name and second param is default value
	Input::get('name', 'Unknown');

	// Return the all keys from the request
	Input::get('*');

	// Example request is : http://example.com/?name=Nyan&job=Developer&work=MyanmarLinks
	$all = Input::get('*');
	var_dump($all);
	// Output is
	/*
	array
		'name' => string 'Nyan' (length=4)
		'job' => string 'Developer' (length=9)
		'work' => string 'MyanmarLinks' (length=12)
	*/

**Get the File from the Request**

	Input::file($key, $default);

**Get the Server and execution environment information ($_SERVER)**

	// will return "localhost" at local server
    echo Input::server('HTTP_HOST');
    // OR
    echo Input::server('http_host');

    // will return All Server info (equal $_SERVER)
    var_dump(Input::server('*'));

**Get the Client IP**

	// Output is 127.0.0.1 in my localhost
	echo Input::ip();

**Get the HTTP schema**

	// Output is http in my localhost
	echo Input::scheme();

**Get the user form $_SERVER['PHP_AUTH_USER']**

	Input::user();

**Get the password form $_SERVER['PHP_AUTH_PW']**

	Input::password();

**Checks whether the request is secure or not**

	// return boolean
	Input::isSecure();
