#Class Alias Library for Reborn CMS

**namespace** - Reborn\Cores

Register the class alias. You can use your class (external of Reborn's Cores) to alies use this method.

**Code Sample**

	// If you want to use Products\Libs\Shopper to Shopper
	Alias::aliasRegister(array('Shopper' => 'Products\Libs\Shopper'));

	// Ok, Shopper class is aliased now
	// You can call the Products\Libs\Shopper by Shopper
	Shopper::calculate();
