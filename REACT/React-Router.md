	- - -
Sometimes the components(webpages) are not requested from the server, instead they are routed directly by the React App. So, they are quite fast.
### Installing react router ->
```javascript
npm i react-router-dom -S
```
-S = production dependency  can 

### Import this in the index.js file ->
```javascript
import {BrowserRouter as Router , Route} from 'react-router-dom';
```

![[Pasted image 20231218090217.png|500]]
This means , the 'App' component will respond to this '/' path.
- - -
## Link component ->

The 'Link' Component comes with the React-Router Library. 
It works just like href in HTML , it takes the user to that page/path.

## Link and Route ->

![[Pasted image 20231121121226.png|600]]

1. When we will click the 'Home' button , we will get directed to "/" route.
2. When we will click the 'Post' button , we will get directed to "/post" route.
3. When we will click the 'About' button , we will get directed to "/Link" route.


![[Pasted image 20231121121915.png|700]]
-  When the directed route is "/", then we will display 1.
-  When the directed route is "/post", then we will display 2.
- When the directed route is "/about", then we will display 3.
- - -

## Nested Routing ->
![[Pasted image 20240319085552.png]]
The Search bar and the Links will remain the same.
Only the UI below the links will change.

### The Parent 
![[Pasted image 20240319125838.png|700]]
The Outlet component will display the Children of the Parent (Product)

### The Nesting
![[Pasted image 20240319130420.png|700]]

- - - 

## Advanced Nesting ->

If we decide to have a banner across the entire Application like the Footer and the Header.