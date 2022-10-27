Testing with jasmine 

jasmine - is a Behavior Driven Development testing (BDT) framework for JavaScript.
	- focused on the behavior of users rather than the technical functions of the software.
	- to show your business point of view and the requirements of the product

ng test
- builds the application in watch mode, and launches the Karma test runner (a tool which spawns 
a web server that executes source code against test code for each of the browsers connected)

* A Chrome browser opens (--watch=true) and displays the test output in the "Jasmine HTML Reporter"

	|| Basics of testing components ||

Since a component is a congregation of both the html template and code behind (ts files, and other
services) To adequately test a component, you should test that they work together as intended.

Such tests require creating the component's host element in the browser DOM, as Angular does, and
 investigating the component class's interaction with the DOM as described by its template.

Test Fixture
The ComponentFixture is a test harness for interacting with the created component and its corresponding 
element.

Spies
Jasmine has test double functions called spies. A spy can stub any function and tracks calls to 
it and all arguments