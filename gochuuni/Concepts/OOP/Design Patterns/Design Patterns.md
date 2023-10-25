## Creational - How objects are created
- Singleton - Object that can only be instantiated once. 
	- Use case: Settings
- Prototype - Fancy word for "clone". 
	- Create clone object instead of extending object.
- Builder - Create object with methods instead of constructor. 
	- Examples: 
		- JQuery.
- Factory - Instead of using a new keyword to instantiate an object you use a function or method to do it for you. 
	- Use case: Cross platform app - Conditional checking to determine which button to show.

## Structural - How objects relate to each other
- Facade - A simplified API to hide low level details in your code base. 
	- Use case: Create facade class that contain the low level systems as dependencies which then simplifies their operation. 
	- Examples: 
		- JQuery.
- Proxy - Fancy word for "substitue". Replace target object with a proxy. 
	- Examples: 
		- Vue's reactivity system.

## Behavioral - How object communicate with each other
- Iterator - Traverse through a collection of objects. 
	- for loop.
- Observer - Many objects subscribe to events that are broadcast from another object. 
	- one-to-many relationship. 
	- Loop that unfolds over the dimension of time.
- Mediator - Is like a middle man or broker. 
	- Examples: 
		1. Air traffic controller that sits between the runways & airplains to provide coordination & communication. 
		2. Middleware
- State - Object behaves differently based on a finite amount of states. 
	- Examples: 
		- Finite State Machines