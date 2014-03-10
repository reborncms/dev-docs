#Helper functions for Reborn CMS

You can use these helper functions anywhere in Reborn.

##dump($value, $die = false)

Dump the given value. Use for [var_dump()](http://www.php.net/manual/en/function.var-dump.php). If you want to die the script after dump, use as second parameter is true.

* **$value** (mixed) - Value to dump 
* **$die** (boolean) *default=true* - exit after dump.

**Example**

	dump($value, true);

##h($str, $flags = ENT_QUOTES, $encode = 'UTF-8', $doubleEncode = true)

Shortcut function for htmlspecialchars() function.
See detail at php's [htmlspecialchars function.](http://php.net/htmlspecialchars)

* **$str** (string) - String to convert
* **$flags** (int)
* **$encode** (string)
* **$doubleEncode** (boolean)

**Example**

	// Output is &lt;script&gt;alert('hello!');&lt;/script&gt;
	h("<script>alert('hello!');</script>");

##t($key, $replace = null, $default = null)

Helper function for the translate. This function is same with Translate::get()

* **$key** (string) - Key for Translate value
* **$replace** (array|null) - Arguments in translate text
* **$default** (string) - Default value if key not found.

**Example**

	t("blog::blog.save");
	
	//Translate text with Arguments	
	return array(
	    'say_hello' => 'Hello, {:name}'
	);
	
	t("blog::blog.say_hello", array('name' => 'John'));

##flash()

Get the flush session view (with html). This function is same with Flash::flahsBox();

This method is purpose for use at html view file.

**Example**

	flash();

##value($val)

Return the value of given param. If the value is closure, return closure result.

* **$val** (mixed)

**Example**

	value($val);

## slug($str, $separator = '-')

Generate the given string to slug(URL) type string

* **$str** (string) String to convert
* **$separator** (string) *default='-'* Separator for space.

**Example**

	// Output is this-is-my-blog-title
	// Replace the space with default separator (-)
	slug("This is my blog title");

	// Ok. We use separator (_) instead of default (-)
	slug("This is my blog title", "_");
	// Output is this_is_my_blog_title

##sanitize($str, $pattern)

Sanitize the given string by given pattern

* **$str** (string) String to sanitize
* **$pattern** (string) Regular Expression Pattern

**Example**

	// Output is "Who are you"
	sanitize('Who are you?', 'A-Za-z-0-9-\s');

##random_str($length = 10)

Generate the random string.

* **$length** (int) default=10 - Length of random string

**Example**

	// Output is "SLDtRbL2yJ"
	randomStr();

	// Output is "9lW0wJt6638BAEoCdlcJ"
	randomStr(20);
	

##array_pluck($arr, $key)

Remove value from the given array

* **$arr** (array) Array to remove from
* **$key** (string) Key of the value to remove

**Example**

    $student_data = array(
        'name' => 'John Doe',
        'age'  => 18,
        'created_at' => '2014-02-10 12:51:02'
    );
    
    $new_student_data = array_pluck($student_data, 'age');
    
    //Output 
    $new_student_data = array(
        'name' => 'John Doe',
        'created_at' => '2014-02-10 12:51:02'
    );



##array_get($array, $key, $default = null)

Get an item from an array using "dot" notation.

This function is original from Illuminate\Supprot\src\helpers.php file.

* **$array** (array) Array to get value from
* **$key** (string) Key of the value to get
* **$default** (mixed) Default value for the key

**Example**

	$array = array('first' => array(
				'second' => 'This is second level',
				'third' => 'This is another second level')
			);

	// Result is "This is second level"
	array_get($array, 'first.second')

	// Result is "I am Default", because not found first.unknown key in given array
	array_get($array, 'first.unknown', 'I am Default')

##arr_is_multi($array)

Check the given array is multidimensional array or not.

* **$array** (array) Array to check

**Example**

	$array = array('first' => array(
					    'second' => 'This is second level',
					    'third' => 'This is another second level'
					    )
			 );

	// Return is "true"
	arr_is_multi($array);

##arr_to_object($array)

Convert given array to object.

* **$array** (array) Array to convert

**Example**

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
    
	arr_to_object($array);
	

##is_json($string)

Check given string is json or not    

* **$string** (string) String to check

##remove_base_url($url)

Remove base url from given url

* **$url** (string) Url to convert

**Example**
    
    remove_base_url('http://reborncms.com/blog');
    
    //Output : 'blog'


##url($path = '')

Helper function for the Uri::create()

* **$path** (string) uri to create url

**Example**

	// Output is "http://localhost.dev/blog/category/test/"
	url('blog/category/test');

##admin_url($path = '')

Helper function for the Uri::create() with ADMIN Panel Link.

* **$path** (string) uri to create url

**Example**

	// Output is "http://localhost.dev/admin/blog/category/test/"
	admin_url('blog/category/test');
	

##image_url($name, $width = null, $height = null)

Media module image url

* **$name** (string) Filename
* **$width** (int|null) Image Width in px
* **$height** (int|null) Image Height in px

##asset_url($path = '')

Get Asset File Path

##css($file, $media = "all", $module = null)

Helper function for the Asset::css().

**Example**

	// Output is Style tag with css file link (file from active theme)
	css('style.css');

##less($file, $media = "all", $module = null)

**Example**

	less('style.less');


##js($file, $module = null)

Helper function for the Asset::js().

**Example**

	// Output is Script tag with js file link (file from active theme)
	js('script.js');

##img($file, $alt = null, $attr = array(), $module = null)

Helper function for the Asset::img().

**Example**

	// Output is Image tag with image file link (file from active theme)
	img('example.jpg');
	


##assetPath($type)

Helper function for the Asset File Path (css, js, img).

**Example**

	// Output is js folder link (folder from active theme)
	assetPath('js');

##global_asset($type, $filename)

Get Global Assets Files (path_to_project/global/assets)

* **$type** (string) Asset Type (js, css, img)
* **$filename** (string) Asset filename

**Example**
	
	global_asset('js','jquery.min.js');


##arr_for_select()

Converts a multi-dimensional associative array into an array of key => values base on your set field name.

**Example**

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

##e2s($data, $key, $value, $blank = false)

Eloquent Model Object to the Select Array

* **$data** (Object) Eloquent Model Object
* **$key** (string) Array Key
* **$value** (string) Array Value
* **$blank** (boolean) If you want to add --Select-- in return array, set true

**Example**

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

##country($key)

Get the country name by country code

* **$key** County code

**Example**

	// Output is "Myanmar [Burma]"
	country('MM');

	// Output is "United States"
	country('US');

	// Output is "Japan"
	country('JP');

##gravatar($email = '', $size = 50, $name = null, $class= null, $rating = 'g', $default = null, $url_only = false)

Get Gravatar image

* **$email** (string) Email address for gravatar
* **$size** (int) Size for gravatar. Default is 50
* **$name** (string) Name of gravatar, using user's name
* **$class** (string) Class attributes
* **$rating** (string) Rating for gravatar. Default is 'g'
* **$default** (string) Default key for gravatar
* **$url_only** (boolean) Set true if you want gravater url only. Default is false

##checkOnline($url = 'www.google.com', $port = 80)

Check internet connection is avaliable or not

* **$url** (string)
* **$port** (int)

##setting($key)

Helper Function of Setting::get().

* **$key** (string) Setting key

##cycle()

Alternate a set of value. Give values as arguments.

**Example**

	$numbers = array(
	    'one', 'two', 'three', 'four', 'five', 'six'
	);

	foreach ($numbers as $num) {
	    echo $num . ' - This is ' . cycle("odd", "even") . ' number.</br>';
	}

##is_home()

Check for home page

**Example**

	if (is_home) {
		//Thing you want to show only at home page.
	}

##markdown($text)

Transform Markdown to HTML with dflydev\markdown.

* **$text** (string) Text to transform

##markdown_extra($text)

Transform MarkdownExtra to HTML with dflydev\markdown.

* **$text** (string) Text to transform

##num($str)

Change numbers with localization number.

* **$str** (string) Number String to convert

##theme_config($key, $default = null)

Get Theme Config Value

* **$key** (string) Config Key
* **$default** (mixed) Default value if key doesn't found.

##first($var)

Produce at first time only in looping.

**Example**

	foreach ($images as $img) {
	 	<div class="first('active')">
			<img src="$img">
		</div>
	}

##template_parse($template, $data = array())

Parse reborn template string embedded in data. Eg. Reborn template written in blog, page, etc. Should use before template render.

* **$template** (string) Template String
* **$data** (array) Data array

##navigation($nav = 'header', $type = 'reborn')

Navigation render from Navigation Module.

* **$nav** (string) Navigation Area
* **$type** (string) Navigation CSS Style Type. Avaliable Types (default, bootstrap, foundation, purecss)

**Example** 
	
	navigation('header');

##formatSizeUnits($bytes)

Convert filesize Unit from bytes to KB, MB, GB

* **$bytes** File size in bytes

**Example**

	formatSizeUnits('104857600');

	//Output : '100.00 MB'

##formatSizeToBytes($size)

Convert filesize Unit frin KB, MB, GB to bytes

* **$size** File Size in KB, MB, GB and bytes

**Example**

	formatSizeToBytes('100MB');

	//Output : 104857600

##image_data($image)

Covert image into base64 encoding data

* **$image** Image Path

##tree_lists($lists, $parent = 'parent_id')

Format parent child data array into tree style data (eg. Comments)

* **$list** (array) Unformatted data list
* **$parent** (string) Key for parent_id

**Example**

	$comments = Comments::all()->toArray();

	$comments = tree_lists($comments);

##ga($gid, $domain = null)

Google Analytics JS code. See details at [https://developers.google.com/analytics/devguides/collection/analyticsjs/](https://developers.google.com/analytics/devguides/collection/analyticsjs/)

* **$gid** (string) Google analytic ID
* **$domain** (string) Domain name

##jquery($version = '1.10.2')

get jQuery Google CDN Link

* **$version** jQuery version
