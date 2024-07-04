 - -
Now, we will fetch API data from React.
To do this we need two things - 
1. Server - We will a use a package named 'json server'.
2. Database - We will manually hardcode our database in JSON.
### How to install JSON-Server?
![[Pasted image 20231105103713.png|500]]
npx - for Temporary Installation
db.json - is the database connected to this server. 

```javascript
 (async () => await fetchItems())();
```
For async code inside the useEffect , we have to explicitly call the function.
- - -
## Catching a error ->
For catching a error, we will use useState,  and will use conditional ternary operator in the 'return' section. 

## Mocking an API call ->
An API data wouldn't load immediately onto the screen, it will take some time. Meanwhile, while we are waiting for the response
the screen should display "Loading".

![[Pasted image 20231108145139.png]]
1st Line - If isLoading is true , then display "Loading Items..."
2nd Line - If fetchError is true(error is there) , then display the Error Message
3rd Line - If isLoading and fetchError both are false, then display the Main component.

This was Reading an API. Now we will do Create , Update and Delete operation in a new folder.

- - -
![[Pasted image 20231108183924.png|700]]
The 'optionsObj' really creates a difference between being a Create , Delete and Update Request. Above is the async function for Create ,  Delete and Update. We will export that function to the Content.js. Options anywhere is always is represented in Object. 

![[Pasted image 20231109204058.png|850]]
Now, write the above code inside the Content.js

### For Updating we will send that particular property to update to the apiRequest method.
![[Pasted image 20231109204328.png]]



