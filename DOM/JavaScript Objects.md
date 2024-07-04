- - - 
## Creating a Constructor :->

- It's just like objects and classes as if we want to create multiple objects having the same key(properties) but different values. Basically a factory of objects.
```javascript
//creating the constructor
function bellboy(name, age, hasworkpermit, languages)
{
	this.name = name;  //this keyword points to the object
	this.age = age;
	this.hasworkpermit = hasworkpermit;
	this.languages = languages;
}

//initialising the object
let bellboy1 = new bellboy("Tridib", 19, true, ["Bengali", "English", "Hindi"]);
```
