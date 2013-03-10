#Version Control Class for Reborn CMS

##How to use Version Class

###compare()

Compare the Given Version and Current Version of Reborn CMS.

* *(String)* Version of the given to compare with current version.

**Code Sample**

	// Return is same with version_compare() function from PHP.
	$versionObj = new \Reborn\Cores\Version();
	$versionObj->compare('1.0');