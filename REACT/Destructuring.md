- - -
## Objects ->

```javascript
let person = {
	firstName = "Tridib",
	lastName = "Chatterjee"
};

//Access objects the new way
let {firstName , lastName} = person;
//we are basically pulling apart the variables from the object and assigning them to new variables
console.log(firstName);
console.log(lastName);

//We can also Rename the variables with the new value
 let {firstName: fName , lastName: lName} = person;
 console.log(fName);
 console.log(lName);
```

![[Pasted image 20231021115455.png|800]]
For the middleName variable priority will be given to ' ' as this variable is not defined in the person object so it will print the default value.
But for the age it will print 28.

## Arrays ->

```javascript
const arr = [1,2,3];

let [x,y,z] = arr;
console.log(x);
console.log(y);
console.log(z);
```

### Skip an item in array Destructuring ->
```javascript
const arrval = ['One' , 'Two' , 'Three'];
const [x,,z] = arrVal;

console.log(x); //One
console.log(z); //Three
```
- - -
## Spread Operator ->


### Arrays ->
```javascript
const names = ['Sonny', 'Jay', 'Brian', 'Rodgers'];
// destructuring assignment in arrays
// assigning remaining elements to y
const [x, ...y] = names;

console.log(x); // Sonny
console.log(y); // ["Jay", "Brian", "Rodgers"]
//the ...y returns an array instead of returning only the values inside the array like x 
```

### Objects ->
```javascript
const person = {
name: 'Sonny Sangha',
age: 28,
gender: 'Male'
}

// destructuring assignment
// assigning remaining properties to rest
let { name, ...rest } = person;

console.log(name); // Sonny Sangha
console.log(rest); // {age: 28, gender: "Male"}
// the ...rest returns an object(key:value) instead of returning only the value like in the case of name 
```

### Important ---> We should use spread operator only at the last while destructuring.
- - - 
## Swapping two variables using destructuring ->

```javascript
let namel = 'Sonny';
let name2 = 'Jay'; I

// swapping variables
[namel, name2] = [name2, namel];

console.log(namel); // Jay
console.log(name2); // Sonny
```

## Nested Object Destructuring ->

```javascript
let member = {
	id: 01,
	name: {
	firstName: 'Sonny',
	lastName: 'Sangha'
    }
};

// Heres how to destructure it...
let { id, name: { firstName, lastName}} = member;

console.log(firstName); // Sonny
console.log(lastName); // Sangha
```
- - -
## Destructuring Functional Arguments ->

We will see destructuring most in this type mainly in REACT-JS.

### Old-School way-->
```javascript
let displayFullName = (person) => {
'${person.firstName}  ${person.lastName}';
}

let person = {
	firstName : "Tridibn",
	lastName : "Chatterjee";
};

displayFullName(person);
```

### New React-style Way-->
```javascript
let displayFullName = ({firstName, lastName}) => {
`${firstName} ${lastName}`;
}

let person = {
	firstName: 'Tridib',
	lastName: 'Chatterjee'
};

displayFullName (person);
```
