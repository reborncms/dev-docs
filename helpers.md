#Helper functions for Reborn CMS

## (1) dump($value, $die = false)

Dump the given value. Use for var_dump(). If you want to die the script after dump, use as second parameter is true.

**Code Sample**

	dump($value, true);

## (2) h($str, $flags = ENT_QUOTES, $encode = 'UTF-8', $doubleEncode = true)

Filter function for htmlspecialchars.
See detail at php's htmlspecialchars function.

**Code Sample**

	// Output is &lt;script&gt;alert('hello!');&lt;/script&gt;
	h("<script>alert('hello!');</script>");

## (3) t($key, $default = null, $locale = null, $type = 'file')

Helper function for the translate. This function is same with Translate::get()

**Code Sample**

	t("blog::blog.save");

## (4) flash()

Get the flush session view (with html). This function is same with Flash::flahsBox();

This method is purpose for use at html view file.

**Code Sample**

	flash();

## (5) value($val)

Return the value of given param. If the value is closure, return closure result.

**Code Sample**

	value($val);

## (6) slug($str, $separator = '-')

Generate the given string to slug(URL) type string

**Code Sample**

	// Output is this-is-my-blog-title
	// Replace the space with default separator (-)
	slug("This is my blog title");

	// Ok. We use separator (_) instead of default (-)
	slug("This is my blog title", "_");
	// Output is this_is_my_blog_title

## (7) sanitize($str, $pattern)

Sanitize the given string by given pattern

**Code Sample**

	// Output is "Who are you"
	sanitize('Who are you?', 'A-Za-z-0-9-\s');

## (8) randomStr($length = 10)

Generate the random string.

**Code Sample**

	// Output is "SLDtRbL2yJ"
	randomStr();

	// Output is "9lW0wJt6638BAEoCdlcJ"
	randomStr(20);

## (9) array_get($array, $key, $default = null)

Get an item from an array using "dot" notation.

This function is original from Illuminate\Supprot\src\helpers.php file.

**Code Sample**

	$array = array('first' => array(
							'second' => 'This is second level',
							'third' => 'This is another second level')
					);

	// Result is "This is second level"
	array_get($array, 'first.second')

	// Result is "I am Default", because not found first.unknown key in given array
	array_get($array, 'first.unknown', 'I am Default')

## (10) arrIsMulti($array)

Check the given array is multidimensional array or not.

**Code Sample**

	$array = array('first' => array(
							'second' => 'This is second level',
							'third' => 'This is another second level')
					);

	// Return is "true"
	arrIsMulti($array);

## (11) arrToObject($array)

Convert given array to object.

**Code Sample**

	$array = array('first' => array(
							'second' => 'This is second level',
							'third' => 'This is another second level')
					);

	// Result is
	//	object(stdClass)[60]
  	//		public 'first' =>
    //			object(stdClass)[59]
    //  			public 'second' => 'This is second level'
    //  			public 'third' => 'This is another second level'
	arrToObject($array);

## (12) url($path = '')

Helper function for the Uri::create()

**Code Sample**

	// Output is "http://localhost.dev/blog/category/test/"
	url('blog/category/test');

## (13) adminUrl($path = '')

Helper function for the Uri::create() with ADMIN Panel Link.

**Code Sample**

	// Output is "http://localhost.dev/admin/blog/category/test/"
	adminUrl('blog/category/test');

## (14) css($file, $media = "all", $module = null)

Helper function for the Asset::css().

**Code Sample**

	// Output is Style tag with css file link (file from active theme)
	css('style.css');

## (15) js($file, $module = null)

Helper function for the Asset::js().

**Code Sample**

	// Output is Script tag with js file link (file from active theme)
	js('style.css');

## (16) img($file, $alt = null, $attr = array(), $module = null)

Helper function for the Asset::img().

**Code Sample**

	// Output is Image tag with image file link (file from active theme)
	img('example.jpg');

## (17) assetPath($type)

Helper function for the Asset File Path (css, js, img).

**Code Sample**

	// Output is js folder link (folder from active theme)
	assetPath('js');

## (18) arr_for_select()

Converts a multi-dimensional associative array into an array of key => values base on your set field name.

**Code Sample**

	$array = array('0' => array(
							'id' => 1,
							'title' => 'Title One'
							),
						'1' => array(
							'id' => 2,
							'title' => 'Title Two'
							),
					);

	arr_for_select($array, 'id', 'title');
	// Result is
	// array(
	//		'1' => 'Title One',
	//		'2' => 'Title Two'
	//	)

## (19) e2s($data, $key, $value, $blank = false)

Eloquent Model Object to the Select Array

* @param Object $data Eloquent Model Object
* @param string $key Array Key
* @param string $value Array Value
* @param boolean $blank If you want to add --Select-- in return array, set true
* @return array

**Code Sample**

	$cats = \Blog\Model\Category::all();
	e2s($cats, 'id', 'name', true);
	// Return value is
	// array(
	//		'' => '-- Select --',
	//		'1' => 'Category One',
	//		'2' => 'Category Two'
	//	)

	// If you doesn't want -- Select --. Use this
	e2s($cats, 'id', 'name');
	// Return value is
	// array(
	//		'1' => 'Category One',
	//		'2' => 'Category Two'
	//	)

## (20) country($key)

Get the country name by country code

**Code Sample**

	// Output is "Myanmar [Burma]"
	dump(country('MM'));

	// Output is "United States"
	dump(country('US'));

	// Output is "Japan"
	dump(country('JP'));
