#Security Class for RebornCMS

**namespace** - Reborn\Util

This class will handle Security of RebornCMS

##How to use Security Class

###CSRField()

CSRF hidden field

**Example**

	// This method will return String value
	Security::CSRField()
	

###CSRFvalid()

Check valid CSRF

**Example**

	if (Security::CSRFvalid()) {
		//valid
	} else {
		//fail
	}