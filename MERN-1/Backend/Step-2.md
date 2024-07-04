- - -
## Middlewares->

Middlewares are one or more functions that are placed in the path of the request that are received by our Backend API Server . 
![[Pasted image 20231217084831.png|500]]

![[Pasted image 20231217084926.png|500]]

![[Pasted image 20231217084941.png|500]]

- - -
## Built-in Middleware ->

```javascript
//serving the static files(built-in middleware)
1. app.use('/', express.static(path.join(__dirname,'public')));

//middleware to receive and parse JSON Data
2. app.use(express.json());

//middleware to parse cookies
3. app.use(cookiParser());
```

## Custom Middleware ->

- Create two Middlewares -> 
1. Logger Middleware to log every time a user logs in .
![[Pasted image 20231219223119.png|600]]

2.  Error Handler Middleware to handle errors.
![[Pasted image 20231219223212.png|600]]

## CORS Error ->
As our server is a Private API, no external source should be able to access it directly, unless we give permission. 
1. Call the cors middleware .
2. We will create a Public API first and then we will secure it using CORS. 
3. Then create a folder named '**config**', inside it there should be two files -> 
   - allowedOrigins.js -> Would contain the allowed domains that can directly access our Private API.
   - corsOptions -> Our built in Middleware in the server.js that prevents the CORS Error.


 

We will only allow the Origins that we want to Access our API. We can do that using CORS Options .