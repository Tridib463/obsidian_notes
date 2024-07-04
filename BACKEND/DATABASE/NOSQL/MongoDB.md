- - -
- It is a noSQL database. While it is possible to host our Database locally on our machine during development, We won't do that in 'Production'.
- So, we can host our Database in the cloud using MongoDB Atlas.
- It is a Database as a Service where managing our MongoDB Database becomes much easier.
- - -
## Steps to set up your MongoDB Atlas ->
- After creating the account, click on the 'Leaf' button and click on 'New Project'.
- Our Cluster would look like this.
![[Pasted image 20231216090750.png]]

- Click on My Collections. And then click on 'Add My Own Data'.
 ![[Pasted image 20231216091306.png|500]]
 
 - We have now created our own Collections under the Database.
 ![[Pasted image 20231216091437.png|700]]

- Now, click on 'Database Access' under Security Tab. Then click on 'Add New User'. We want to create a user who can access our Database.
![[Pasted image 20231216094712.png|700]]

- Go to Database Deployments. Click on Connect.
![[Pasted image 20231220090008.png|700]]

- Click on 'Allow access from Anywhere', only in the development phase. cause we don't know where we will be hosting our database.
- Click on 'Connect through Application'. This gives us a Connection String.
![[Pasted image 20231220090741.png|600]]

- Paste the Connection String inside the .env file.


- - -
## Connecting our DB ->

- Add the Database URI, inside the .env file.  **a URI describing a database connection, also called a connection string**.
- Now install mongoose. It is a library which makes working with MongoDB much easier.
- Import the mongoose library in the server.js file.

Now, we have to create a connection config file. Create a file named 'dbConn.js' inside the config folder.
- Import that file into the server.js file. Connect to the database. We will listen to the port only when our Server is connected to our Database.
![[Pasted image 20231216101914.png|800]]
- - -
### Create a folder named 'model', which will store our Data Models.

## Mongoose Schemas and Data Models ->
It will allow us perform CRUD Operations on our MongoDB DataBase.
- Everything in Mongoose starts with a Schema. Each schema maps to a MongoDB collection and defines the shape of the documents within that collection.
- Mongoose is a popular ODM(Library) for MongoDB in Node.js, and it allows you to define a schema for your documents. 
- A Mongoose schema provides a way to model and structure your data, including specifying the types of fields, default values, validation rules, and more. It adds a layer of abstraction on top of MongoDB, making it easier to work with in a Node.js environment.

```javascript
const mongoose = require('mongoose');

// Defining a schema
const userSchema = new mongoose.Schema({
  name: {
    type: String, 
    required: true
  },
  age: {
    type: Number,
    min: 18
  },
  email: {
    type: String,
    unique: true,
    required: true,
    trim: true
  }
});

// Create a model based on the schema
const User = mongoose.model('User', userSchema);

// Example usage
const newUser = new User({
  name: 'John Doe',
  age: 25,
  email: 'john@example.com'
});

// Save the document to the MongoDB collection
newUser.save()
  .then(() => console.log('User saved successfully'))
  .catch(err => console.error('Error saving user:', err));

```
Lets create a schema for employees data and users data.


### By default, when mongoose creates a data model, it will set 'Employee' to LOWER Case and PLURAL. So, it will look for an 'employees' collection in MongoDB. 
![[Pasted image 20231216124704.png|700]]
The model 'Employee' is for the 'employees' collection in the database.
