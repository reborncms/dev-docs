#Validation class for Reborn CMS

Form validation class. Now support 18 type of validation.

* 01) - max [Input value's Maximum is given value]
* 02) - min [Input value's Minimum is given value]
* 03) - maxLength [Input value's string length Maximum is given value]
* 04) - minLength [Input value's string length Minimum is given value]
* 05) - required [Input value is required]
* 06) - alpha [Input value is Alpha(a-zA-Z)]
* 07) - alphaNum [Input value is AlphaNumeric(a-zA-Z0-9)]
* 08) - alphaDash [Input value is AlphaNumeric, Dash and Underscore(a-zA-Z0-9-_)]
* 09) - alphaDashDot [Input value is alphaDash and Dot(a-zA-Z0-9-_.)]
* 10) - numeric [Input value is Numeric(0-9)]
* 11) - integer [Input value is Integer value]
* 12) - email [Input value is Valid Email]
* 13) - url [Input value is Valid URL]
* 14) - ip [Input value is Valid IP address]
* 15) - between [Input value is Between first and last value eg:between:5,7]
* 16) - equal [Input valis is Equal with given value or field name eg:equal:9]
* 17) - color [Input valis is valid 6-digits color hexadecimal code eg:#efefef]
* 18) - patterm [Input valis is valid regex pattern eg:"/\d{4}-\d{2}-\d{2}/"]

## Usage of Validation

**Code Sample**

	// Input field
    //eg: array('name' => 'Reborn', 'age' => '25', 'address' =>'Yangon-Myanmar')
    $inputs = array( // Get the all input from form submit
           'name' => Input::get('name'),
            'age' => Input::get('age'),
            'address' => Input::get('address')
        );
    $rules = array(
            'name' => 'required',
            'age' => 'between:18,30',
            'address' => 'minLength:10|alphaDashDot'
        );

    // Create the validation
    $v = new Validation($inputs, $rules);
    // (or)
    $v = Validation::create($inputs, $rules);

    // Check the validation
    if ($v->valid()) {
         echo 'Input is Valid';
    } else {
        $errs = $v->getErrors();
        foreach ($errs as $e) {
	        echo $e.'<br>';
        }
    }
    // (or)
    if ($v->fail()) {
    	$errs = $v->getErrors();
        foreach ($errs as $e) {
	        echo $e.'<br>';
        }
    } else {
      	echo 'Input is Valid';
    }


###addRule()

We can add new validation rule using addRule() method.

* *(string)* $name Validation name

* *(string)* $msg Error message for this rule

* *(Closure)* $callback Callback function for rule

**Code Sample**

	$input = array('t' => 'test');
	$rule = array('t' => 'test');
	$v = \Validation::create($input, $rule);
	$v->addRule('test', 'Test is fail', function($value){
			return ($value == test);
		});
	dump($v->valid()) // Output is true


###getErrors()

Get the Validation Errors. If doesn't have any validation error, return null

**Code Sample**

	// return errors in array if error occure or return null if not
	$v->getErrors();

