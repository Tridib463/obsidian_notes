- - -
![[Pasted image 20231101120911.png|700]]

## HTML Forms ->
```javascript
<form action="/login" method = "POST">
```
action - In most cases will refer to the route that you want your server to handle this request.
method - Describe how you want this data to be processed in the backend.


```javascript
<label for="email">EMAIL</label>
<input type="text" name="email" required>
```
type - What kind of input is this?
name - Will label the data that goes into this input. So, the email will have a key associated with this value(email)
We can also add a 'required' attribute, that this input will not be submitted until there is a piece of data in this field.


```javascript
<label for="password">PASSWORD</label>
<input type="text" name="password" required>
```


```javascript
<input type="submit" value="submit">
</form>
```


![[Pasted image 20231101122236.png|1000]]
### Body-parser is a pre-processing middleware
### Morgan is a logger middleware