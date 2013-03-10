#HTTP Request Class

##How to use Request Class

###isAjax()

Check the request is Ajax or not

**Checking**

	// This method will return boolean value
	$request = new \Reborn\Cores\Request();
	$ajax = $request->isAjax();
	dump($ajax);


###baseUrl()

Get the Base URL

**Getting base Url**

	// This method will return baseUrl like www.reborncms.com
	$request = new \Reborn\Cores\Request();
	$url = $request->baseUrl();
	dump($url);