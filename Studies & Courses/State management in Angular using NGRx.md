State management is very crucial since it is core to all the frameworks for JavaScript: VueJs and ReactJs: process of managing the states of user controls.
* It is a combination of Redux and RxJS (library) 
- Enables heavy data communications while sustaining high application performance.

	Sources:
YouTube - [NgRx in Angular - Redux | Rxjs | State Management - YouTube](https://www.youtube.com/watch?v=nuHBHD32iw8)
Blog by another author - [Angular State Management with NgRx | Syncfusion Blogs](https://www.syncfusion.com/blogs/post/angular-state-management-with-ngrx.aspx)

Five key elements in the NgRx state management process
* Store - contains the state of data for the application. It is immutable here in the store
* Selectors - these enable angular components to subscribe to the store and get the latest state updates
- Reducer - responsible for handling the transition from one state to the another 
	- takes the action mentioned; it also contains the state of data and creates a new state object, returning it to the store. Everytime
- Actions - like filling in a form with data and clicking a button; all these need to be passed to a reducer 
	- These manipulate the state of the store via reducers
- Effects - the result of actions. They can be used to listen for particular action types and run when that action is detected


* We start by defining an action as a constant using an enum. Then, we make the **AddArticleAction** class which implents from the NgRx **Action** class, which accepts two parameters: a type and an optional payload.

![[Pasted image 20221005141330.png]]

The the reducer is needed to aid the state transition and updating the store:
1. First create the initial state of the type (in our case Article interface): Which accepts a state and an action as input parameters.

![[Pasted image 20221005142305.png]]

For the final step of the store creation, we need to create another model to keep all app states in a single place.

![[Pasted image 20221005142804.png]]

