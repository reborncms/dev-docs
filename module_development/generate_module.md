#Generating a Module

You can easily create a module from terminal with RebornCMS command line tool, **php magic**.

Run the following command in your project directory.

	php magic module:generate
    
Follow the instrction and fill out the module information.

**Example**

	Jia-Li:reborn Jia_Li$ php magic module:generate
    Please enter the name of the module : Testing
    Please enter the description of the module : This is testing module
    Please enter the author of the module : Li Jia Li
    Please enter the author email of the module : limonster.li@gmail.com
    Please enter the author URL of the module : http://dragonvirus.com
    Testing Module is backend support? [Y|n]y
    Testing Module is frontend support? [Y|n]y
    Testing Module is allow to set default module? [Y|n]y
    Please enter the URI Prefix of the module : testing
    Testing Module is allow to change the Default URI Prefix? [y|N]y
    Module create......
    Testing Module created
    
Now, you can find your newly created module in **content/main/modules**

Module Folder structure is as follow :

----
* assets
	* css
	* img
	* js
* config
	* dev
		* config.php
	* production
		* config.php
	* config.php
* lang
	* en
* src
	* Testing 
		* Controller
			* Admin
				* TestingController.php
			* TestingController.php
		* Extensions
			* Form
				* TestingForm.php
			* Table
				* TestingTable.php
		* Model
			* Testing.php
* views
	* admin
		* form.html
		* index.html
		* view.html
	* index.html
    * view.html
* Bootstrap.php
* TestingInfo.php
* TestingInstaller.php
* routes.php
---
###assets
Assets folder is where you would put your css, js & image files.

###config
Config folder will include your module configuration. You can also add config files for specific environment.

###lang
Lang folder will include language files for the module.

###src
This folder is the heart of the module. All main files such as Controller, Model and Library and extensions file must include in this folder. You can create any subfolder under **src/Testing** in which Testing is the name of your module.

**Controller** folder is where your controller files will exist. You should put your backend controller under Admin folder.

In **Extension** folder you might see Form and Table Class with your module name. This the Form Builder and Table Generator Classess. Please read more about these at specific section.

**Model** Folder is where your model files must exist.

###views
This is where your view files must exist. In here, it is optional to put backend view files in admin folder. It's just for better management.

###Bootstrap.php
Bootstrap file is the starting point of the module. Bootstrap file includes the following methods.

* **boot()** - The method which will run when the module is booted.
* **adminMenu(\Reborn\Util\Menu $menu, $modUri)** - Registeration of Admin Sidebar menu.
* **moduleToolbar()** - Registration of Admin Module Toolbar.
* **settings()** - Registration of Module Setting Attributes (Readmore at Settings Session)
* **register()** - This method will call when the module is started. You should write things you want to call at module start in here .. such as Event Registration, Alias Registration.

###TestingInfo.php
This is the module info file. This will include the information you fill out before when you generate the module.

Info class include following properties
* **$name** - Name of the module
* **$version** - Module version
* **$displayName** - Module Display Name
* **$description** - Module Description
* **$author** - Author of the module
* **$authorUrl** - Author's Url/Website
* **$authorEmail** - Author's Email
* **$frontendSupport** - Module support frontend or not
* **$backendSupport** - Module support backend or not
* **$useAsDefaultModule** - Allow module to set as default module
* **$uriPrefix** - Uri Prefix for the module
* **$allowToChangeUriPrefix** - Allow user to change uri prefix later.
* **$roles** - List of actions for users permission roles.
* **$allowCustomfield** - Allow to add more custom fields via Fields module.
* **$sharedData** - Shared data table for multiple sites/domains.

###TestingInstaller.php
This is the module Installer file where you must include database schema for module installation, upgrading and uninstallation.
Installer class include the following methods :

* **install($prefix = null)** - Database Schema for Module Installation
* **uninstall($prefix = null)** - Database Schema for Module Uninstallation.
* **upgrade($dbVersion, $prefix = null)** - Database Schema for Module Upgrade.

*Note : Please see Laravel Illuminate Documentation for how to use Database Schema Builder.*

###routes.php
You must write your routings in here. Read more at Routing Section.


