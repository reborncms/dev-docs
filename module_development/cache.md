#Cache

##set($key, $value, $time = 10080)

set cache data with given key name

* **$key** (*string*) Cache Key Name
* **$value** (*mixed*) Cache Data
* **$time** (*int*) Cache Life time in minutes

**Example**

	$blog = Blog::find($id)->toArray();
	Cache::set('blog_post_'.$id, $blog);
    
##get($key, $default = null)

get cache data with given key name

* **$key** (*string*) Cache Key Name
* **$default** (*mixed*) Default Data for Cache

**Example**

	Cache::get('blog_post_'.$id);
    
##solve($key, Closure $callback, $time = 10080)

Get cache data or set callback data

* **$key** (*string*) Cache Key Name
* **$callback** (*Closure*) Callback method for solve cache value if cache is not exist.
* **$time** (*int*) Cache Life time in minutes

**Example**

	Cache::solve('blog_post_'.$id, function(){
    	return Blog::find($id)->toArray();
    });
    
##has($key)

Check if cache data exist or not

* **$key** (*string*) Cache Key Name

**Example**

	Cache::has('blog_post_'.$id);
    
##delete($key)

Delete Cache Data

* **$key** (*string*) Cache Key Name

**Example**

	Cache::delete('blog_post_'.$id);
    
##deleteFolder($folder)

Delete Cache Folder

* **$folder** (*string*) Cache Folder Name

**Example** 

	Cache::deleteFolder('blog');
    
##setPath($path)

Set Cache Folder Path

* **$path** (*string*) Cache Folder Path

**Example** 

	Cache::setPath('path-to-cache-folder');
    
##getPath()

Get Cache Path

**Example**

	Cache::getPath();
    
##setExtension($ext)

Set Cache Extension

* **$ext** (*string*) Cache Extension

**Example**

	Cache::setExtension('jpg');
    
##getExtension()

Get Cache Extension

**Example**

	Cache::getExtension();
    

