#Event Class for RebornCMS

##How to use Event class

###add()

Add(Register) the Event.

* *(String)* Event name (eg: blog_post_create)

* *(Closure)* Callback function name.

**Add the event**

	\Event::add('blog_post_create', function(){
			echo 'This is blog event'
		});

### addBefore()
Add callback function for the given event before running. This is same with controller before method().

* *(String)* Event name (eg: blog_post_create)

* *(Closure)* Callback function name.

**Add Before this event**

	\Event::addBefore('blog_post_create', function(){
			echo '---- This is prepare process for event blog_post_create ----';
		});

### addAfter()
Add callback function for the given event after running. This is same with controller after method().

**Add After this event**

	\Event::addAfter('blog_post_create', function(){
			echo '---- This is shutdown process for event blog_post_create ----';
		});


###call()

Call(Trigger) the event.

* *(String)* Name of event

* *(array)* Data array for callback event *(optional)*

**Calling the event**

	//return void
	\Event::call('blog_post_create', array());


###has()

Check the given event name is have or not

* *(String)* Name of event

**Checking the event**

	//return true if the event you find is exist and return false if not
	\Event::has('blog_post_create');


###remove()

Remove(UnRegister) the given event name.

* *(String)* Name of the event

**Removing the event**

	\Event::remove('blog_post_create');

### removeBefore()
Remove the given event's before callbacks.

* *(String)* Event name (eg: blog_post_create)

**Remove Before this event**

	\Event::removeBefore('blog_post_create');

### removeAfter()
Remove the given event's after callbacks.

**Remove After this event**

	\Event::removeAfter('blog_post_create');
