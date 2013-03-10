#File class for RebornCMS

##How to use File class in RebornCMS

###is()

Check the file is exists or not.
This method is equal with php's file_exists() function.

**Usage**

	// Return true if file is exists.
	File::is(__DIR__.'tempate/home.php');

###getContent()

This method can be use to get content of the specific file.
If file doesn't exits, throw the **FileException**

* *(String)* The path for you want to get content.

**Getting Content**

	//This method will return a string of content of the file and return false if reading fail.
	File::getContent('D:/test/data/reborn.txt');

###getFromRemote()

This method can be use to get content of the specific file from another host.

* *(String)* The path for you want to get content.

**Getting Content**

	//This method will return a string of content of the file and return false if reading fail.
	\File::getFromRemote('http://www.reborncms.com/files/10/');




###write()

This method will write content to specific file. If the file is not exist, the method will automatically cretate with given content.

* *(String)* The file path

* *(String)* Filename you want to create or

* *(String)* Content

**Writing Content**

	// return void
	$content = "This is the testing content for File class of Reborn CMS.";
	\File::write('D:/data/', 'the_test.txt', $content);


###put()

Put the new contents to a file. If you want to append th data to a file, set true the $append [third parameter]. Default is false for this.
See details at php's file_put_contents()

* *(String)* The file path with file and extension

* *(String)* Data content to put a file

* *(Boolean)* Append the given file or not. Default is false

**Put the Content**

	// This method will put the data to the file without append
	$content = "This is the testing content for File class of Reborn CMS.";
	\File::put('D:/data/the_test.txt', $content);

	// Ok. We will add new content to the file with exists file's data
	$new_content = "Reborn CMS is leighweight"
	\File::put('D:/data/the_test.txt', $new_content, true);

	// Result at file
	// This is the testing content for File class of Reborn CMS. Reborn CMS is leighweight

###delete()

Delete the given file.

**Delete the file**

	File::delete("D:/data/the_test.txt");







