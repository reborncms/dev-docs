#Controller Class for Reborn CMS

###before()

Before method will be called before request action.


###after()

After method will be called after request action.

###setTheme

Set the current theme and theme path. Call within Controller Only.

* (String) Theme name
* (String) Theme path or theme directory

**Setting a theme**

	\Controller::setTheme('rbDefault', 'www.reborncms.com/themes/reborn/');
	
###setLayout()

Set the current theme's layout name

* (String) Layout name for current theme

**Setting a theme**

	\Controller::setLayout('rbDefault', 'www.reborncms.com/themes/reborn/');
	
