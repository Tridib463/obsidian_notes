- - -
Whenever we add the new workout , it updates the Real time in the UI as well as the Database

### UseParams Hook ->
Used to extract something from the route path 

## Workflow of frontend and backend ->


### Frontend->
1. Create a Signup.js page. Inside this extract the email and password. Import the useSignup hook. Inside the useSignup hook, call the signup function by passing the email and password as arguments .
2. Create a useSignup hook. From the useSignup hook return the signup function so that we can use that later.
3. Inside the signup function, fetch this route  
 ![[Pasted image 20240126112801.png|500]]

### Backend ->
1. Inside the userModel, create a function named signup to store the email and hashed password inside the database and return the user.
![[Pasted image 20240126114730.png|700]]

2. Inside the userController, inside the singupUser function , call the signup function inside the userModel to save the email and password.
3. Create the JWT Token and return the email and token back to the client(frontend).
 ![[Pasted image 20240126115431.png|700]]
 
4. Save the the token received in the client-side in the local Storage 
![[Pasted image 20240126115536.png|700]]


![[Pasted image 20240126151251.png|600]]

- - -
## Setting the Initial Auth Status ->

Lets say the user have logged in our website. The JWT Token gets stored inside the Local Storage. Now , if we refresh the page the UI shows that the user is not logged in i.e.
the Auth Status becomes 'null'. But if we check the local storage , the JWT is still there that means we area practically logged in. 
To Avoid this , the server checks whether the client has the JWT stored in local storage or not at the very First INITIAL RENDER and updates the Auth status accordingly.

## Protecting the API Routes ->

We have to make sure that that only logged in users can access their respective data.
We have to create a middleware inside the workout.js (routes) that fires before every route.
The Middleware checks whether the JWT is sent along with the request or not. If sent , whether it is valid or not.
### The Syntax of the Token being sent
'Bearer sdfsdfsdfsdf.sdfsdfsdfsdf.sdfsdfsdfs'  Bearer then three (3) different parts of the Token .
It is in the String format and characters after Bearer is the Token.

### Function of the Middleware 
![[Pasted image 20240127075332.png|600]]
If the token is successfully verified , from the payload of the token the 'id' property is stored in _'id'_ .
We are attaching the user property to the req object. So, whenever we go to one of the route-handler functions after the middleware, On those req objects we will have this 'User' property.
![[Pasted image 20240127080406.png|700]]

### Making Authorized Requests 
Now with every request to the Server, the Client have to send the JWT token in the authorization header. Only then we can access the data.
WE need to do that in Three(3) different places -->
1. When we are fetching all the workouts.
2. In the Form when we are adding a New Workout.
3. When we are deleting a Workout.
4. We will come to the Update part later.

### Assigning workouts to Users 
When I can log in as a certain User , I only see the workouts that I add. So everyone has their own workouts and they only see their own respective workouts.
We will do it by adding a User_id property to each workout document when we save it in the Database.
