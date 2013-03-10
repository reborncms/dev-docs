#Validation class for Reborn CMS

##How to use Validation Class

###Validation Rules

* **max** Input value's Maximum is given value
* **min** Input value's Minimum is given value
* **maxLength** Input value's string length Maximum is given value
* **minLength** Input value's string length Minimum is given value
* **required** Input value is required
* **alpha** Input value is Alpha(a-zA-Z)
* **alphaNum** Input value is AlphaNumeric(a-zA-Z0-9)
* **alphaDash** Input value is AlphaNumeric, Dash and Underscore(a-zA-Z0-9-_)
* **alphaDashDot** Input value is alphaDash and Dot(a-zA-Z0-9-_.)
* **numeric** Input value is Numeric(0-9)
* **integer** Input value is Integer value
* **email** Input value is Valid Email
* **url** Input value is Valid URL
* **ip** Input value is Valid IP address
* **between** Input value is Between first and last value eg:between:5,7
* **equal** Input valis is Equal with given value or field name eg:equal:9
* **color** Input valis is valid 6-digits color hexadecimal code eg:#efefef
* **patterm** Input valis is valid regex pattern eg:"/\d{4}-\d{2}-\d{2}/"

###create()

* *(array)* Input fields

* *(array)* Rules for Input field

**Code Sample**

	\Validation::create();
	
	
###addRule()

waiting

* *()* name

* *()* message

* *()* callback

**Code Sample** 
	
	\Validation::addRule();
	
	
###valid()

Check the validation is valid or not.

**Code Sample**

	// This method will return boolean value
	\Validation::valid();
	

###fail()

Opposite of valid method

**Code Sample**

	// This method will return boolean value
	\Validation::fail();
	
	
###getErrors()

Get the Validation Errors. If doesn't have any validation error, return null

**Code Sample**

	// return errors in array if error occure or return null if not
	\Validation::getErrors();
	
	
###compute()

Compute the Input and his rule is valid or not.

* *(String)* Input field name

* *(String)* Validation rule for given input field

**Code Sample**

	\Validation::compute();
	
	











