- - -
## Callback functions :->
- Functions which are passed to another function as parameters.
```javascript
function firstfunction(parameters, callback)
{
	//do stuff
	callback();
}
```

- But callback functions(Callback Hell) has other problems. Lets say we have to initiate number of functions one after another. This would initiate a chain reaction and gets a little harder to follow. Example given below ->
```javascript
firstfunction(para, ()=> {
	secondfunction(para, ()=> {
		thirdfunction(para, ()=> {
		})
	})
})
```
So promises came to avoid the callback Hell.

- - -
## Promises :->

![[Pasted image 20230922072334.png |600]]
![[Pasted image 20230922121848.png|500]]
Important Link for promises - https://www.freecodecamp.org/news/javascript-async-await-tutorial-learn-callbacks-promises-async-await-by-making-icecream/
### Creating a new promise :->
```javascript
let p = new Promise((resolve , reject))
```
The promise object passes a callback function which has two arguments resolve and reject.
```javascript
let p = new Promise((resolve , reject)=> {

    let a = 1+1; //the actual promise

    if(a==2)

    {

        resolve("Success"); //what we want to do when the promise succeeds

    }

    else

    {

        reject("Failed");//what we want to do when the promise fails

    }

})

  

p.then((message) => {    //do this when it succeeds 

    console.log("This is in the even " + message)

}).catch((message) => {   //do this when it fails

    console.log('This is in the catch '+ message)

})
```
- The `.then()` method takes up to two arguments; the first argument is a callback function for the fulfilled case of the promise, and the second argument is a callback function for the rejected case. Each `.then()` returns a newly generated promise object, which can optionally be used for chaining.
- A `.catch()` is really just a `.then()` without a slot for a callback function for the case when the promise is fulfilled.

Promises are really great when we want to do something that's going to take a long time in the background, such as downloading an image from a different server instead of making to wait all other processes.
- - - 

## Replace a Code written with callbacks with Promises :->

### Callback Code ->
```javascript
const userLeft = false
const userWatchingCatMeme = false

function watchTutorialCallback(callback, errorCallback) {
	if (userLeft) {
		errorCallback({
			name: 'User Left',
			message: ':('
		})
} else if (userWatchingCatMeme) {
		errorCallback({
			name: 'User Watching Cat Meme',
			message: 'WebDevSimplified < Cat'
		})
	} else {
		callback('Thumbs up and Subscribe')
	}
}
watch TutorialCallback((message) => {
	console.log('Success: ' + message)
}, (error) => {
console.log(error.name +' '+ error.message)
```
The Code replaced with promises is in VS-Code under the folder ASYNC_JS(index1.js).
A Promise is an object. There are multiple functions within an Object which can be called ex - 
1. resolve() = It resolves the promise.
2. reject() = It rejects the promise.
3. .then() = It takes two parameters, resolve and reject, The .then() method returns a Promise. It takes up to two arguments: callback functions for the success and failure cases of the Promise.

## Return value of .then() :->

Returns a new [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) immediately. This new promise is always pending when returned, regardless of the current promise's status.

One of the `onFulfilled` and `onRejected` handlers will be executed to handle the current promise's fulfillment or rejection. The call always happens asynchronously, even when the current promise is already settled. The behavior of the returned promise (call it `p`) depends on the handler's execution result, following a specific set of rules. If the handler function:

- returns a value: `p` gets fulfilled with the returned value as its value.
- doesn't return anything: `p` gets fulfilled with `undefined` as its value.
- throws an error: `p` gets rejected with the thrown error as its value.
- returns an already fulfilled promise: `p` gets fulfilled with that promise's value as its value.
- returns an already rejected promise: `p` gets rejected with that promise's value as its value.
- returns another pending promise: `p` is pending and becomes fulfilled/rejected with that promise's value as its value immediately after that promise becomes fulfilled/rejected.

![[Pasted image 20230927195959.png|800]]

## Async Await :->

We have written a code of promises with .then under the folder ASYNC_JS(index2.js).. Now we will modify and write the same code with async await. It is a better way of dealing with promises.
We need to have some kind of function(Async) that our awaiting code is inside of.

### Code ->
```javascript
async function doWork()
{

}
```
OR 
```javascript
doWork = async () => {

}
```

Each time when an async function is called, it returns a new [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be resolved with the value returned by the async function, or rejected with an exception uncaught within the async function.

Async functions can contain zero or more [`await`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) expressions. Await expressions make promise-returning functions behave as though they're synchronous by suspending execution until the returned promise is fulfilled or rejected. The resolved value of the promise is treated as the return value of the await expression.

```javascript
const myCool Function = async () => {

//this fetch method returns a promise, we are basically telling wait till the promise is resolved
const response = await fetch("https://jsonplaceholder.typicode.com/users");

//this .json() method also returns a promise, we are basically telling wait till the promise is resolved
const jsonUserData = await response.json ();

//async functions always return a promise
return jsonUserData;
}
```
Code after each await expression can be thought of as existing in a `.then` callback. In this way a promise chain is progressively constructed with each reentrant step through the function. The return value forms the final link in the chain.

Async functions always return a promise. If the return value of an async function is not explicitly a promise, it will be implicitly wrapped in a promise unlike .then() where returning a value will directly give us that.
![[Pasted image 20230927222416.png|700]]
This will give the Output - Promise{Pending}. To access the data, we need to deal with the returned Promise.

