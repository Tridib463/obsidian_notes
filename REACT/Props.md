- - -
We pass props from top-down, i.e. from Parent to children. Props are what makes Components reusable. It can't pass form down to top.
However, props are [immutable](https://en.wikipedia.org/wiki/Immutable_object)—a term from computer science meaning “unchangeable”. When a component needs to change its props (for example, in response to a user interaction or new data), it will have to “ask” its parent component to pass it _different props_—a new object! Its old props will then be cast aside, and eventually the JavaScript engine will reclaim the memory taken by them.

**Don’t try to “change props”.** When you need to respond to the user input (like changing the selected color), you will need to apply “set state” to the parent component above and pass down different props to the child. 

![[Pasted image 20231015213243.png|800]]

## Passing a property to a Child ->

![[Pasted image 20231023100825.png|800]]
## Catching the property by a child -->

![[Pasted image 20231023101057.png|700]]

## Default prop ->

![[Pasted image 20231023101223.png|500]]
This applies when we haven't passed any props to the child.
- - - 
Let's say the 'footer' component needs to have access to the list items that is stored in 'Main' Component. But this are sibling components, and we cant pass props of one sibling component to another sibling component.
To overcome this, we pass the props of 'Main' up to the 'App'(main) component and then pass it down to the 'Footer' component.

## New file structure ->
![[Pasted image 20231023110100.png|750]]


- - -
## States ->
**Definition:**

- **State** is a built-in object in React that represents the mutable data within a component. It allows components to keep track of and manage their own data.

**Key Points:**

- **Local to Component:** State is local and specific to the component in which it is defined. It cannot be accessed or modified by other components.
- **Mutable:** State is mutable, meaning it can be updated using the `setState` method provided by React.
## Properties ->
- **Props (short for properties)** are a way to pass data from a parent component to a child component. They are immutable, meaning a child component cannot modify the props it receives.

**Key Points:**

- **Unidirectional Flow:** Props flow in a unidirectional manner, from parent to child.
- **Read-Only:** Components receiving props cannot modify them. They are read-only.
- **Functional Components:** Props are commonly used in functional components but can also be used in class components.

## Difference between States and Props ->
1. State(like local variables) is the internal data managed by a component than can change overtime ..... Props is the input passed to a component(like function arguments).
2. States are mutable with the help of hooks while props are immutable. 

## Hooks ->
**Hooks** are functions that allow functional components to use state and other React features.