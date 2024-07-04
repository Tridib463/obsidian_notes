- - -
- Create the .env file to store the DATABASE_URI String to connect to the database.
- Import the .env file to the server.
```javascript
require('dotenv').config();
```

### File Creation ->
1. User.js - User data model ( Refer to 9, 13 and 15 of Project Description)
- Define the Schema
 ![[Pasted image 20231220095551.png|250]]
- username and password for each user.
- roles for different user. Users can be Employees, Managers, or Admins. A user can have multiple roles. The default role is 'Employee'.
- active -> Any new user will automatically be active without first sending data to our API(Server).
- - -

2. Note.js -> Note data model( Refer to 10, 11 and 12 of Project Description)
![[Pasted image 20231220101614.png|400]]
- Notes are assigned to specified users. 'ref' options is used to Link to the 'User' Schema.  MongoDB automatically creates objectID but, it is very long so we install a package .
- ObjectId is a special type used in MongoDB to uniquely identify documents in a collection.
![[Pasted image 20231220102402.png|400]]
- timestamps for start time and end time.

## Connecting to Database ->

- Create a file named 'dbConn.js' under the model directory.
- Import 'mongoose' and 'connectDB' from 'dbConn' inside the server file.
### Call the ConnectDb() function at the first and at the last write these codes->
![[Pasted image 20231220105757.png|800]]