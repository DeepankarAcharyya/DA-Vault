Source : https://www.youtube.com/watch?v=rpt8PpIPhJQ
Basically proven and reusable approaches to common software design problems.

Creational Patterns - how objects are created
- Singleton
	- one shared instance of a class
		- app config
		- logger
	- globally accessible
	- explicit passing the instance
- Builder
	- Build the object step by step
		- The constructor - is created with the necessary required info
		- Add the other optional data to the object using multiple methods
- Factory
	- there is an abstract factory class
	- subclasses implement them
		- Eg : notification
			- can be email, sms
---
Structural Design Pattern : how objects are organized and combined
- Adapter
	- helps 2 incompatible components work together - when the interfaces doesnt match
	- override the functions
- Facade
	- simple interface to a complex system
		- complicated workflow
			- the user / client have to know the underlying complicated steps and the sequence of the steps
	- Facade provides a single interface for the user to use
		- it hides the complexities within it
		- the user doesnt need to know whats happening under the hood
- Proxy
	- It places a substitute object infront of the original object to control access to it
	- both real object and the proxy exposes the same interface
		- so the client can use the proxy just like the original object
- Decorator
	- add new behavior to an object dynamically without its original class