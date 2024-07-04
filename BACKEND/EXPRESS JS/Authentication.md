- - -
We need two file Routes -
1. A 'Registration' route to register a new user.
2. A 'Authentication' route to Authenticate the user after they have created an account.


- - -
## For JWT ->
- npm install three packages -
1. jsonwebtoken
2. cookie-parser
3. dotenv

- At the 'root' level, make a new file named - '.env'. We will put our Environment Variables here.
- Open the Command line and type ```node``` . So now we are inside the node terminal. 
- Node has a common core module called 'crypto'.
- Now write ```require('crypto').randomBytes(64).toString('hex')``` , this will give us a random crypto Byte String which we can use as our Access Token Secret .

![[Pasted image 20231213095933.png]]

Make sure to add the .env file inside the gitignore file. We will keep this .env file in the dev environment and then when we host somewhere , they should have a way to put the environment variables in the hosting service and then we can pull those out.

![[Pasted image 20231213164913.png|500]]
- The first thing we will pass in the jwt is a payload. We will use Username object (not password).
- Our secret from the .env file.
- Options value of the time limit of the access token.
### Create a similar thing for the Refresh Token 
### Now we will save the Refresh Token in the database which will allow us to create a Logout route. That will invalidate the Refresh Token when the user logs out.
	 ![[Pasted image 20231213222004.png]]
	

- After that send the access token as JSON, which will be stored by the client in their memory.
- Now, send the Refresh Token as httpOnly cookie , making it unaccessable via JavaScript.
- - -

### Now, create a middleware which will verify the access token as an when the client sends request to our server API. (verifyJWT.js)
![[Pasted image 20231214161434.png|700]]

Now we can add it to routes that we want to protect.
Inside the employees.js file , add the verifyJWT middleware Infront of the route that i want to protect.
![[Pasted image 20231214162120.png|700]]
We are protecting the 'get' route with the JWT. Will first verify the JWT by calling the middleware(verifyJWT) , before going to the next function.
IF we want to protect all the routes , then do this ->
- Import the verifyJWT middleware, in the main server.js.
- Use the middleware, just before the route that you want to apply to.
![[Pasted image 20231214210115.png|800]]
- - -
## Now for the Refresh Token ->

- We create a refreshTokenController, which will will be called by the refresh route.
- In the refreshTokenController, 
1. **Cookie Handling:**
    
    - It retrieves cookies from the request using `req.cookies`.
    - Checks if there is a JWT (JSON Web Token) in the cookies. If not, it responds with a status of 401 (Unauthorized).
2. **Finding User with Refresh Token:**
    
    - It searches for a user in the `usersDB` based on the refresh token extracted from the cookies. Remeber we stored Refresh Tokens in the database of the user.
    - If no user is found, it responds with a status of 403 (Forbidden).
3. **JWT Verification:**
    
    - It uses the `jsonwebtoken` library to verify the refresh token against the secret stored in the environment variable `REFRESH_TOKEN_SECRET`.
    - If there is an error during verification or if the decoded username does not match the username in the found user, it responds with a status of 403 (Forbidden).
4. **Generating and Sending a New Access Token:**
    
    - If the refresh token is valid, it generates a new access token using the `jsonwebtoken` library with a 30-second expiration time.
    - It responds with a JSON object containing the new access token.
- - -

## For Logout ->
- On the Client-Side delete the access token.
- Check whether the jwt is present in the cookie object or not (req.cookies)
- If Refresh Token is not found in the Database, delete only the cookie.
- If Refresh token is found in the DB, Erase the Token as well as the cookie.