- - - 
![[Pasted image 20240610091739.png|800]]

![[Pasted image 20240611113814.png|700]]


## Mistake -1 (Using Client too high)
![[Pasted image 20240610092622.png|700]]
The 'use client' is like a boundary.
Here, we are using "use client" in Component 1 , means Component 3 will also become a Client Component.

So, try to use "use client" at the leafs, Like for Buttons , input Fields.. small little pieces NOT THE WHOLE PAGE. JUST THE COMPONENT.

IF we import some component inside a "Client Component" that also becomes Client Component.
But, if a Client Component is placed inside a Server Component , then it remains a Client Component.
- - -

## Mistake -2 

IF we import some component inside a "Client Component" that also becomes Client Component.
But if we wrap a Server Component with a State management library Like Context API, Then the Server Components remains like Server Components.

### How to wrap Server Component inside a Server Component?
->



- - -
## How does a Client Component Render?
- A common misconception is that Client Component renders only on the Client-Side(Browser). Not True. It renders for the First time in the Server and then the Server Hydrates the Component by attaching various Interactivity and Event Listeners and then it renders on the Client.

- - -

## Using Browser APIs (e.g. localstorage)

### Method-1 -->
Use useEffect hook. As it runs only on the Client Side.
![[Pasted image 20240610204807.png]]

### Method-2 -->
Import that component dynamically so that it runs only on the Client Side.
![[Pasted image 20240610204944.png]]

- - -

## Incorrectly Dealing with 3rd party components

- Create a Separate Client component and wrap that 3rd party component with that Client component.
![[Pasted image 20240610205454.png|700]]

- Then import this Component.
![[Pasted image 20240610205652.png|600]]

- - -
## CRUD Operation
![[Pasted image 20240610210121.png|600]]

- We can fetch data directly using server components or Creating Route Handlers. basically the same as getting called on the server.
- Suppose we don't want to pass Props . Then we can call fetch function again and again as the data gets cached on the Server side.

### Getting a Waterfall effect when fetching Data -->

SEQUENTIAL FETCHING
![[Pasted image 20240611083351.png|700]]
The above picture is the Sequential Data Fetching. We use this when one component depend on another Component.
First the await getProduct() loads , then only getRatings() loads.
![[Pasted image 20240611083533.png|500]]


PARALLEL FETCHING
![[Pasted image 20240611083636.png|700]]
The getProduct() and the getRatings() will run Independently of each other.


### For POST, PUT, DELETE use Server Actions ->
	Create a separate file for server actions called 'actions'.

If we want to use "Server Actions" in Server Components, then use form action={addProduct()}
If we want to use "Server Actions" in Client Components, then use onClick => {addProduct()}

 Always Validate Input and Protect Server Actions. 

### IMPORTANT->
When Creating "Server Actions", write 'use server' on top of that.
But When we want a Component to run only on the Server-Side , use 'server-only'

- - -
## Params and SearchParams

params --> This is the id.
SearchParams --> This is the part after the question mark.   products/1?color="blue"

### How to use ?
- Push the Searchparams inside the URL using the Router push method.
- Then do the filtering using map.