#How to write Reborn Theme?

This is the folder structure of the Reborn Theme.

![Theme Structure](templates/img/theme-folder.png)

* **assets** folder is collection of your assets file.
* **views** folder is collection of view files.
* **handler** folder is collection for Theme Parser Hander files.
* **info.php** file is information file for your theme.

###Theme Information File (info.php)

	return array(
			'name' => 'Default',
			'description' => 'Default theme for the Reborn CMS',
			'author' => 'Reborn Development Team',
			'website' => 'http://www.reborncms.com',
			'version' => 1.0,
			'min-require' => 2.0
		);

* **name** Theme name.
* **description** Theme description
* **author** Theme creator name.
* **website** Theme creator's website.
* **version** Theme version.
* **min-require** Minimum require of Reborn CMS.

###Layout Folder

Your theme may be have many layout for desing. You can add your layout files at this folder. **default.html**(required) is default layout for the Reborn CMS.

###Partial Folder

TODO

###Handler Folder

This folder is optional.

