- - -
## **Basic Syntax :->**

```javascript
document.querySelector('.classname').addEventListener("event" , function)
```
- event should be passed as a String.
- when we only pass the callback function name , we don't have the to include the brackets.
```javascript
document.querySelector('className').addEventListener("event" , handleclick);
function handleclick()
{
alert("I got clicked");
}
```
- When we pass the function as a whole then we have to include brackets
```javascript
document.querySelector('className').addEventListener("event" , ()=> 
alert("I got clicked"));								 
```

---
## Adding event Listeners to multiple elements :->

- When we have an array we can traverse using forEach method.
- But when we don't have an array - 
```javascript
int len = document.querySelectorAll('.button').length();
for(let i=0;i<len;i++)
{
	document.querySelectorAll('.button')[i].addEventListener("click" , ()=>
	{
		alert("I got Clicked");
	})
}
```

---
## using 'this' keyword :->

```javascript
int len = document.querySelectorAll('.button').length();
for(let i=0;i<len;i++)
{
	document.querySelectorAll('.button')[i].addEventListener("click" , ()=>
	{
		alert("I got Clicked");
		console.log(this);
	})
}
```
- The 'this' keyword gives us the identity of each of the button or objects.