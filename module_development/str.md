#String Helper Class

**namespace** - Reborn\Util

String Helper Class

##camel($str) 

convert string to camel case

* **$str** (string) String to convert

**Example**
    
    Str::camel('Your Function Name'); //Output : yourFunctionName
   
##snake($str, $delimiter = '_')

convert string to snake case

* **$str** (string) String to convert
* **$delimiter** (string) Delimiter for snake case. *default* = '_'

**Exmaple**
    
    Str::snake('String to Snake'); //Output : string_to_snake    

##studly($string)

convert string to studly case

* **$string** (string) String to convert

**Example**
    
    Str::studly('String to studly'); //Output : StringToStudly

##slug($str, $separator = '-')

convert string to slug(url) type string

* **$str** (string) String to convert
* **$separator** (string) Separator for space. *default* = '-'

**Example**

    Str::slug('Introduction to RebornCMS'); //Output : introduction_to_reborncms    

##sanitize($str, $pattern)

Sanitize the given string by given pattern

* **$str** (string) String to sanitize
* **$pattern** (string) Regular Expression Pattern for sanitization

**Example**

    Str::sanitize('Who are you ?', 'A-Za-z\s'); //Output : Who are you
   
##random($length = 10)

Generate random String

* **$length** (int) random string length. *default* = 10

**Example**

    Str::random(5);

##words($string, $limit = 100, $ending = '...')

Truncate string with words limit

* **$string** (string) String to truncate
* **$limt** (int) Number of words to limit *default* = 100
* **$ending** (string) Symbol at the end of the stirng to show text continuation. *default* = '...'

**Example**

    Str::words('Nam liber tempor cum soluta', 4); //Output : Nam liber tempor cum...

##limit($string, $limit = 100, $ending = '...')

Truncate string with character limit

* **$string** (string) String to truncate
* **$limt** (int) Number of character to limit *default* = 100
* **$ending** (string) Symbol at the end of the stirng to show text continuation. *default* = '...'

**Example**
    
    Str::limit('Nam liber tempor cum soluta', 10); //Output : Nam liber ...

##title($value, $remove_separator = true, $separator = '_')

Change slug text back to Title String Type

* **$value** (string) String to convert
* **$remove_separator** (boolean) Remove separator (_ or -) from string. *default* = true
* **$separator** (string) Require if $remove_separator is false. *default* = '_'

**Example**

    Str::title('hello_world'); //Output : Hello World
    Str::title('hello_world', true); //Output : Hello_World
    Str::title('hello_world, true, '-'); //Output : Hello-World
    

##increment($str)

Increment for string. Example : If you give hello_world, it will return hello_world_1. 

* **$str** (string) String to get increment

**Example**

    Str::increment('hello_world'); //Output : hello_world_1

##join($separator)

Join Multiple strings with separator

* **$separator** (string) Separator to join between strings

**Example**

    Str::join('_','Hello', 'World', 'John', 'Doe'); //Output : Hello_World_John_Doe
    

##highlight($text, $term, $class = 'highlight', $flag = 'i')

Add span tag with given class to highlight exact term.

* **$text** (string) Text 
* **$term** (string) Term to make highlight
* **$class** (string) Class for span tag *default* = 'highlight'
* **$flag** (string) Flag for regular expression to match $term

**Example**

    Str::highlight('Place text to highlight here.', 'highlight');
    
    //Output : Place text to <span class='highlight'>highlight</span> here.

##startWith($needle, $haystack, $ignorecase = true)

Check the given string is start with an exact string

* **$needle** (string) Term to check
* **$haystack** (string) String to check
* **$ignorecase** (boolean) Ignore Case Sensitive. *default* = true

**Example**
      
    Str::startWith('hello', 'Hello World', false); //Output : true

##endWith($needle, $haystack, $ignorecase = true)

Check the given string is end with an exact string

* **$needle** (string) Term to check
* **$haystack** (string) String to check
* **$ignorecase** (boolean) Ignore Case Sensitive. *default* = true

**Example**
      
    Str::endWith('world', 'Hello World', false); //Output : true  

##endIs($string, $end)

End the string with an exact string. If the string is not ended with specifiy string, that string is added to the end.

* **$string** (string) Input String
* **$end** (string) End string

**Example**

    Str::endIs('Hello World', ', Everyone!'); //Output : Hello World, Everyone!

##isBlank($str = null)

Check the given string is blank or not.

* **$str** (string) String to check

**Example**

    Str::isBlank(''); //Output : true
    Str::isBlank(null); //Output : true
    Str::isBlank(' '); //Output : true
    Str::isBlank('\n'); //Output : true
    Str::isBlank('1'); //Output : false

##isNotBlank($str)

Check give string is blank or not. Opposite of Str::isBlank()

* **$str** (string) String to check

##lines($str)

Explode string by new line (\n)

* **$str** (string) String to explode

**Example**

    Str::lines('Hello World! \n How are you ?'); //Output : array('Hello World!', 'How are you ?');

##contain($needle, $haystack, $ignorecase = true)

Check given string contain an exact string.

* **$needle** (string) Term to check
* **$haystack** (string) String to check
* **$ignorecase** (boolean) Ignore Case Sensitive. *default* = true

**Example**

    Str::contain('hello', 'hello world');

##containIn($lists, $haystack, $ignorecase = true)

Check one of the string in the list is contain in the given string.

* **$lists** (string) List of String
* **$haystack** (string) String to check
* **$ignorecase** (boolean) Ignore Case Sensitive. *default* = true

**Example**

    Str::containIn(array('array', 'list'), 'list must be array'); //true
    Str::containIn(array('list', 'object'), 'list must be array'); //true
    Str::containIn(array('object', 'string'), 'list must be array'); //false


##containAll($lists, $haystack, $ignorecase = true)

Check all strings from the list is contain in the given string.

* **$lists** (string) List of String
* **$haystack** (string) String to check
* **$ignorecase** (boolean) Ignore Case Sensitive. *default* = true

**Example**

    Str::containAll(array('array', 'list'), 'list must be array'); //true
    Str::containAll(array('list', 'object'), 'list must be array'); //false

##lengthBetween($string, $min, $max)

Check given string length is between min and max

* **$string** (string) String to check
* **$min** (int) Minimum Length
* **$max** (int) Maximum Length

**Example** 
    
    Str::lengthBetween('Hello World', 5, 20); //Output : true


##lowercase()

Convert given string to lowercase

**Example**

    Str::lowercase('Hello World'); //Output : hello world








