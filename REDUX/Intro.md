- - -
Redux is a JS library that centralizes application state. Instead of scattering application states in various parts of the UI (Component), We store all the states in a central repository called 'Store', that is a single JS-Object. 
![[Pasted image 20240114002542.png|700]]

We can store Objects, Arrays , numbers , Booleans etc inside the Store. But WE CAN'T DIRECTLY MUTATE THE STATES INSIDE THE STORE.
- - -
![[Pasted image 20240114080037.png|700]]
-  When the user performs an action, we create an action object and dispatch it.
- The Store object has a "Dispatch" method that takes an action, it will then forward this action to the Reducer.
- The Reducer computes the new state and returns it.
- Then the Store will set the state internally, and notify the UI Components.


## Actions ->
- The only way our application can interact with the store.
- Plain JS Objects.
- Have a 'type' property that indicates the type of action being performed.
- The 'type' property is typically defined as string constants.


## Store ->

It Holds the state of our application.

## Reducer ->
- Functions that accepts state and action as arguments , and returns the next state of the application.
- (Previous State, action) => new State



