		|| Design Patterns ||

https://www.dofactory.com/net/design-patterns
- Design patterns are solutions or implementations to mediate software design problems encountered often when developing real-world applications

- 23 Gang of Four (GoF) patterns: Creational, Structural and Behavioral


		|| Behavioral patterns ||

- Patterns that Identify common communication channels between objs and realize these patterns
	- Increase flexibility in carrying out this communication

* concerned with the assignment of responsibilities between objects, or, encapsulating behavior 
in an object and delegating requests to it


1. Command Handler Pattern
Encapsulates (stores) a request as an object, thereby letting you parameterize clients with 
different requests, queue or log requests, and support undoable operations.

2. request response pattern

3.IMediator
https://dotnetcoretutorials.com/2019/04/30/the-mediator-pattern-part-3-mediatr-library/
https://www.youtube.com/watch?v=YzOBrVlthMk&t=761s

* way back to 1994 in the famous book “Design Patterns: Elements of Reusable Object-Oriented Software”.
- Mediator Pattern is to “define an object that encapsulates how a set of objects interact”.
	*  promotes loose coupling by keeping objects from referring to each other explicitly, and it 
	allows their interaction to be varied independently. 

	* Client classes can use the mediator to send messages to other clients, and can receive messages 
	from other clients via an event on the mediator class.


Request comes in (Either a command (associated with modifying entities) or query (just reading data))

	MediatR Specific
* either do “send and receive” type messages, or it can do a “broadcast” type message. 
