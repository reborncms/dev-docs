#Hashing class for Reborn CMS.

**namespace** - Reborn\Util

This class contain some hashing method. Now only support bCrypt.

##How to use Hashing Class

**Example**

	// First, create the hash object
	$hashing = new Hash(); (or) new Hash(8); // a two digit cost parameter
	$hashedValue = $hashing->hash('something');
	// return value '$2a$10$gVs3TMrKftl1yQ7rwee8oezDoayceL0vWtMMnWurxw8QoUreZ0UM6'

	// Check the hash value is true or false.
	if ($hashing->check('something', $hashedValue)) {
		// This is true.
	} else {
		// This is false.
	}
