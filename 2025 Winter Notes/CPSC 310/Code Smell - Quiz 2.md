**Magic Numbers**
* Avoid unnamed constants

**Long Methods**
* Methods should do just one thing at the right abstraction level
* Hard to test, understand, and extend

**Long Parameter List**
* Too many parameters can cause confusion and errors
* Fix: Create Parameter Object or pass an object instead of multiple params

**Comments**
* Good
	* Comment technology is necessary for specification and documentation (e.g. requires, modifies, effects)
* Bad
	* Comments needed to explain code do not refer to specification or documentation
	* Special exception for comments that describe why

**Switch on type**
* Using switch or if statements to choose behaviour based on an object's type
* Replace it with polymorphism
	* Each subclass implements its own behaviour, removing the need for the switch

**Duplicate Code**
* Identical or similar methods in multiple classes
* Fix: Pull up common code to superclass

**Feature Envy**
* A method heavily uses another class's data
* Law of Demeter: Too many dereferences means the method is probably in the wrong spot

**Divergent Changes & Shotgun Surgery**
* Divergent changes occurs when one class is commonly changed in different ways for different reasons

