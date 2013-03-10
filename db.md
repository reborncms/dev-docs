#DB class for Reborn CMS. 

***DB library is use Illuminate Database.***

##How to use DB class

###initialize()

Initialize the DB class

* *(String)* connection name

**Initializing Database**

	\DB::initialize('myConnection');


	
###setEloquent()

Set the Eloquent ORM

**Using setEloquent method**

	\DB::setEloquent();
	


###getDefaultConnectionName()

Get the Default Connection Name

**Getting the default Connection Name**

	\DB::getDefaultConnectionName();
	


###getConfig()

Get the Database Configuration

* *(String)* Name of the config key from db.php

**Getting Configuration**
	
	// return array
	\DB::getConfig('rbDbConfig');