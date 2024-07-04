- - -
## Authentication-->
It is the process of verifying who someone is.
## JWT ->
JSON Web Tokens . A form of user identification that is issued after the initial user authentication takes place.
When a user completes there login process(authenticated) , the REST API will issue the client ->
- An Access Token  = Short Time (5- 15 mins) before it expires 
- A Refresh Token = Long Time (hours or day) before it expires
### There are typically main Hazards associated with it
1. XSS ->    Cross-Site Scripting 
2. CSRF -> Cross Site Request Forgery
## Access Token ->
- Our API will send and receive access token as JSON data. 
- It is advised to store it in the client's Memory(Current app state)so that it is automatically lost when the app is closed.
- DO NOT store it in 'local storage' or 'cookie' . Essentially if you store somewhere with JS , the hacker can also retrieve it with JS.
### Process ->
- Issued to client at the time of Authorization.
- The client can access out API's protected route with the token until it expires.
- Every time an access token is used to make request, our API will verify it with Middleware.
- When the access token does expire, client should send a 'Refresh Token' to API's refresh endpoint to get a new access token.

## Refresh Token ->
- Our API will issue(sent as) Refresh token in an 'httpOnly' Cookie. This type of cookie is not accessible via JS.
- Must have an expiry at some point in time which will then require the user to log in AGAIN.
- Refresh tokens should not have the ability to issue new 'Refresh Token' as it will grant indefinite access.
### Process ->
- Issued at authorization.
- Client uses to request new 'Access Token'.
- Verified with endpoint and Database.
- Must be allowed to expire or LOGOUT (If the user decides to).

![[Pasted image 20231215114853.png|700]]
- - -


## Authorization -->
It is the process of verifying what resources a user has access to.
When we login with the username and the password, we are verifying who we are and that is Authentication.
- After logging in our API server issues the client JWT tokens.
- While its true that the JWT Tokens confirm the authentication process, these tokens allow access to our API endpoints which provide data resources. THIS IS AUTHORIZATION. 
- A JWT Token uses the Authorization Header.

More about this in the 'Authorization' file. 