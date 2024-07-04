- - -
![[Pasted image 20231104080807.png|700]]
APIs is essentially a set of rules and protocols that define how softwares can communicate with each other.
They act as a bridge/interface between softwares.

![[Pasted image 20231104081820.png|500]]
These are basically  APIs having different Architectural styles. They each define different set of rules for their API.

- - -
## Private API
![[Pasted image 20231104082558.png|700]]
Now the reason why it's private is because you don't document it for other people to use.
Your server is exclusively serving your own front end and not somebody else.

## Public API
![[Pasted image 20231104091028.png|800]]
But, normally what we are interested in doing IS getting your server to talk to somebody else's server. This is again done through requests and responses but this time it is done through PUBLIC APIs and it's public because this particular server has allowed this kind of behaviors. 
They have probably documented on how to use their API.
They've exposed certain parts of their server to anybody who wants to request it.

- - -
## Structuring API Requests -> 

### API Endpoints
![[Pasted image 20231104102430.png|400]]

![[Pasted image 20231104103531.png|500]]
ENDPOINTS are basically a different route on the API provider server.
eg. - /activity     /filter      /random    /api

### Query Parameters
![[Pasted image 20231104103805.png|500]]

Its basically a way to put Key-Value pair into the url, when we want to put some additional information OR some parameters to a request.

We can also put multiple queries into a url by adding a ?(question) mark 
![[Pasted image 20231104104033.png|700]]

### Path Parameters
Query parameters are more for filtering and searching that is not unique.
While Path Parameters are more for identifying a resource by some specific or unique parameter like KEY or ID.

### Important -> making an API using third party app(Postman) and making a MVC

## MVC(Model View Controller) ->

![[Pasted image 20231207121922.png|780]]
Controller -> will contain all the js files for the route handling logic.
Model -> will contain the database logic 
View -> Dynamic html pages and presentation(Which will be rarely used while creating an API)

config file -> contains the   cors-option and other files.

- - -
1. Create server.js 
2. Create a routes folder. Inside it make a 'api' folder. Inside the 'api' folder, contains files for different routes handling. We will call the functions which we have defined inside the controller folder here.
 ![[Pasted image 20231210185022.png|300]]
 
3. Create a controller folder. Inside it will contain all the js files defining the function.
![[Pasted image 20231210185059.png|300]]

- - -
### STEP-1 ->
- Inside the employeesController file define all the functions.
### STEP-2 ->
- Inside the employees.js import the functions from the 'employeesController' file and define the routes and call the functions inside the functions.
- Export it.
### STEP-3 ->
![[Pasted image 20231210185606.png|600]]
- Import the employees file into the main server.js file.

![[Pasted image 20231210185732.png|500]]
- Use the employees.js file . The word '/employees' will be added to all the routes

So, server.js calls the employees.js file , which in turn calls the employeesController.js file. 
