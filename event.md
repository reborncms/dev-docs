#Event Class for RebornCMS

##How to use Event class

###on()

Add(Register) the Event (callback function). This event will be invoked whenever event is call(fire). You should use event name with prefix (may be module name) to prevent event conflict.

* *(String)* Event name (eg: blog_post_create)

* *(Closure)* Callback function name.

**Add the event**

	Event::on('blog_post_create', function(){
			echo 'This is blog event'
		});

###call()

Call(Trigger) the event when event is already register(Event::on).

* *(String)* Name of event

* *(array)* Parameter array for callback event *(optional)*

**Calling the event**

	//return void
	Event::call('blog_post_create');

	// How to Call with parameter
	Event::on('blog_post_logger', function($id, $title, $author) {
			Log::info('#id-'.$id.' Blog "'.$title.'" is create by '.$author.'!');
		});
	$post = array('id' => 123, 'title' => 'My Blog Post', 'author' => 'Lynn');
	Event::call('blog_post_create', $post);
	// Log message : '#id-123 Blog "My Blog Post" is create by Lynn!'


###has()

Check the given event name is have or not.
Result will return by boolean.

* *(String)* Name of event

**Checking the event**

	//return true if the event you find is exist and return false if not
	Event::has('blog_post_create');


###off()

Remove(UnRegister) the given event name.

* *(String)* Name of the event

**Removing the event**

	Event::off('blog_post_create');

### clear()
Clear the all events from application.

**Clear the all event**

	Event::clear();
