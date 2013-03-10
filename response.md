#HTTP Response Class

##How to use Respnse Class

###isAjax()

Check the request is Ajax or not

**Checking**

	// This method will return boolean value
	$response = new \Reborn\Cores\Response();
	$ajax = $response->isAjax();
	dump($ajax);