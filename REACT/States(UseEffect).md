## React Component Phases ->

![[Pasted image 20231026165451.png|500]]
1. Initialization = The moment a component is created .
2. Mounting = The moment a component is rendered on the screen for the first time.
3. Updation = Updating a component. A component is rendered between updates.
4. Unmounting = The Moment a component is taken out of the screen. 

Whenever we want to perform a task which is to be done in between the component phases, we use UseEffect Hook .

The `useEffect` Hook allows you to perform side effects in your components.

Some examples of side effects are: fetching data, directly updating the DOM, and timers.

`useEffect` accepts two arguments. The second argument is optional.

`useEffect(<function>, <dependency>)`

We can define async function outside useEffect and then call it OR we can directly write inside the useEffect.
- - -
Lets say we have two components - 
![[Pasted image 20231026171546.png|400]]

### We want something to happen 