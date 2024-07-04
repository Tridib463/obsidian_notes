 - - -
Middlewares are functions that executes between the Request and Response object. The Middleware sits in between the Request and the Response.(Man in the middle)
![[Pasted image 20231029213454.png|800]]
## Now, what kind of things can middleware do?

### 1. Can pre-process the requests and  make changes to the request and the response objects. ->
So when we know that a request is going to go to a multiple handlers, maybe it could be processed by
get post or put requests.
This intermediate stage where we have our middleware can actually go ahead and change aspects of the
request or perform various functions on that request before it goes to its final routing.
### 2. Logging the request ->
So how long does it take the request to come through?
What type of request get post put, etcetera?
What is the status of the request being handled?
### 3.We can also use middleware for authentication. ->
So before we let the request through to our back end handlers, we can see if that request is actually
came from a client that is authorized to make that request, say, if somebody wants to go and change
Facebook's databases to call it handbook instead of Facebook, we have to make sure that that request
is allowed by that user.
### 4.We can also process any errors in the request ->
We can identify them and handle those errors before they go through to the handlers as well.

![[Pasted image 20231101071121.png|500]]
Middlewares act like a waterfall. Will be applied to all route handlers below.
Build-in Middlewares and route handlers have 'next' already added so we do not add there unlike custom middlewares. So we need to add 'next' to it.

![[Pasted image 20231101073617.png|800]]
In this middleware, we are passing two parameters - message to be appended to the file and the file to be created.
req.method - GET , POST , DELETE , etc.
req.headers.orogin - Where our request is coming from. (ex - any server, google.com , etc)
req.url - Which url are they requesting.(requesting our index page)
![[Pasted image 20231101074323.png|900]]
- - -
## What is CORS?  (More about it in detail later)

Cross-Origin Resource Sharing (CORS) is a security feature implemented by web browsers that allows or restricts web applications running at one origin (domain) to make requests for resources from a different origin (domain). An origin is defined by the combination of the protocol (HTTP or HTTPS), domain, and port.
When a web application wants to make a cross-origin HTTP request (e.g., an XMLHttpRequest or a Fetch API request) to a different domain, the browser sends an HTTP request with an "Origin" header indicating the origin of the page making the request. The server at the target domain can then respond with the appropriate CORS headers to indicate whether it allows or restricts requests from that origin. So, while requesting from a different origin we need to tell the browser that we allow requests coming from different origin(URL).

So, the server is telling the client that these are the allowed URLs that are able to access our backend server. Obviously, not all can access the backend server.
That's where APIs come into the picture.

![[Pasted image 20231102093154.png|800]]

To resolve this issue,  we will use a 3rd Party middleware called 'cors'.



![[Pasted image 20231102171343.png|400]]
But this ok when we have a open to the public API, everyone can use it. But not in private API (Our Server)


Thats why we create a whitelist - The list of web applications domains that can access our nodeJS server.
![[Pasted image 20231102171913.png|600]]
We will remove these after development


Now we will create the functions that cors will apply to allow access of these urls to our server.