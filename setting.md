#Setting Class for Reborn CMS.

> Setting from db_setting table.

##How to use Setting Class

###get()

Get the setting item with key name (slug Column in db table).

* *(String)* Key(slug) name for setting item

**Code Sample**

	// Return array if item is found or reurn null if not.
	$item = \Setting::get($key);
	dump($item);

###has()

Check the given key is exists or not.
Return Boolean.

* *(String)* Key(slug) name for setting item

**Code Sample**

	// Return true if key is exists.
	$item = \Setting::has('site_title');


###set()

Set the data to setting table.

* *(String)* key Key name from the setting table

* *(String)* value

**Code Sample**

	\Setting::set($key, $value)


###is()

Check given key's real value is same with given value.

* *(String)* Name of the setting item

* *(array)* Think value for given setting item name

**Code Sample**

	// setting item site_title is "My Site" in the DB
	\Setting::is('site_title', "My Site"); // return true;
	\Setting::is('site_title', "Hello World"); // return false;


###findAllFromDB()

Find all items from DB table.

**Code Sample**

	\Setting::findAllFromDB();








