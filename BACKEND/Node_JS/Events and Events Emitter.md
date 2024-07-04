- - -
For example in Node we have a class called HTTP to build a web server. So,  we listen on a given port and every time we receive a request on that given port, that HTTP class raises an event(emits an event) and our job is to respond to that event.
![[Pasted image 20231029122228.png|700]]

```javascript
import EventEmitter from "events"; //importing EventEmitter class from events
const emitter = new EventEmitter(); //creating an instance of the class EventEmitter

//Registering a listener
emitter.on("MessageLogged", () => {
console.log("Listener Called");
});

//Raise an event
emitter.emit("MessageLogged") //when we raise the event , the callback function is called
```
- - -
Now, in the real world it is quite rare to work with the 'emitter' directly. Instead we will create a class that has all the properties of the EventEmitter and then we will use that class.
i will do it later.

