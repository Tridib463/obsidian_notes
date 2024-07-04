- - -
It is the process of verifying what resources a user has access to.
## User Roles and Permissions ->
- Provide different levels of access 
- Sent in access token payload
- Verified with middleware
- - -
1. Create a new file under the folder 'config' named 'roles_list'.
2. Inside the roles_list, we will create a object. Inside the object, the KEYS will be the names of the Roles and the value that identifies the Role.
![[Pasted image 20231215172808.png|400]]
3. Then export the module.

Now inside the registerController.js add another item inside the object of the 'users' array.
![[Pasted image 20231215180711.png|500]]

4. When we create a new access Token we would want to send this data with the token (Payload).
![[Pasted image 20231215184443.png|500]]

### Ideally there is no need for us to send the roles to the Refresh Token. For the Access Token we will be sending only the values of the roles.

