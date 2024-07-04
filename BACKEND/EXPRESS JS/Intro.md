- - -
![[Pasted image 20231029195824.png|700]]
This app.get , app.post, etc are called Route Handlers.
In this, we can also add regular Expressions.
The Regular Expression says, the path must begin and end with a slash OR should have index.html

![[Pasted image 20231029201149.png|700]]
Now,  we have made .html optional

- - -
WE can chain route handlers by using (req,res,next) method 