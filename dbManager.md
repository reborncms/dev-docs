#DB Manager class for Reborn CMS

**namespace** - Reborn\Connector\DB

The DB Manger class is served as an adapter with database and Reborn Developer.

> DB library is use Illuminate Database.

##How to use DB Manager class

###setEloquent()

Set the Eloquent ORM

**Code Sample**

	\DB::setEloquent();
	
	
###getDefaultConnectionName()

Get the Default Connection Name

**Code Sample**	

	//return String
	\DB::getDefaultConnectionName();
	
	
###getConfig()

Get the Database Configuration

* *(String)* Name of the config key from db.php

**Code Sample**

	// return array
	\DB::getConfig();
	
	

	
	
	
	
	
	
	
	
	
	
	
	
	