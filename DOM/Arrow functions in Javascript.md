- - -
## Two parameters :->

### Normal function ->
```javascript
function sum(a , b)
{
	return a+b;
}
```
### Same function but with arrow function ->
```javascript
let sum2 = (a , b) =>{
	return a+b;
}
```
We can also remove the return because the code inside the bracket is of only one line.
```javascript
let sum2 = (a, b) => a+b 
```
- - - 
## One Parameter :->

### Normal Function ->
```javascript
function isPositive(number)
{
	return number >=0;
}
```

### Same function but with arrow function ->
```javascript
let isPositive2 = (number) =>{
	return number >=0;
}
```
When there is a single parameter, we can remove the parenthesis around the parameter and that would still work.
```javascript
let isPositive2 = number => number>=0
```
- - - 

## No Parameter :->

### Normal Function ->
```javascript
function random_number()
{
	Math.random;
}
```

### Same function with arrow function ->
```javascript
let random2 = () => Math.random
```
- - - 
## Callback Function:->

### Normal Function ->
```javascript
document.addEventListener("click", function() {
		console.log("Click");
})
```

### Same function with arrow function ->

Arrow functions really become helpful when we are passing anonymous function 
```javascript
document.addEventListener("Click", () =>{
	console.log("Click");
})
```