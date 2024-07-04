Components often need to change what’s on the screen as a result of an interaction. Typing into the form should update the input field, clicking “next” on an image carousel should change which image is displayed, clicking “buy” should put a product in the shopping cart. Components need to “remember” things: the current input value, the current image, the shopping cart. In React, this kind of component-specific memory is called _state_.

As Props are immutable, we use States to change something inside a Component.

![[Pasted image 20231009192116.png|700]]
Here, 
name = current state(getter).
setName = A function to change the name(state), also called setter and we set initial state to "Tridib".
- - -

## Onchange vs OnClick ->

## e ->
- - -
## Adding an Element using useState ->

### 1. Define a State for the newly added Item 
![[Pasted image 20231026082840.png|760]]
### 2. Apply Onchange
![[Pasted image 20231026115120.png|680]]
### 3. Prevent Reloading the page when we submit the form
![[Pasted image 20231026115717.png|700]]
![[Pasted image 20231026120047.png|800]]




![[Pasted image 20231026122100.png|800]]
- When we click the "submit" button or press Enter, the onSubmit Event listener is activated and handleSubmit function gets triggered.

![[Pasted image 20231026122358.png|800]]

- The addItem function given below ->
![[Pasted image 20231026122729.png|850]]

### Adding an element -> 
First create a new array or Object, then use destructuring to add the new element to the new array.
### Deleting an element->
Use filter method to delete and then display the array.
### Displaying an element ->
Use map method to create a new array and display the new array.
### Searching an element ->
Use filter method.