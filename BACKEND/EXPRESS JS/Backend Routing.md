- - -
Now,  we will do proper routing to different pages from different directories.
Instead of routing only the main index.html , We will route the html files from 'Subdir' directory.

### STEP-1 
Create a routes 'folder' and inside it create a subdir.js file which will handle all the routings for the "subdir" only.
![[Pasted image 20231206211953.png|300]]

### STEP-2
- Inside the subdir.js file export the 'router' object from Express.Router().
![[Pasted image 20231206214150.png|400]]
- Instead of app.get() or app.post.....replace 'app' with 'router'.
- Export the router.
![[Pasted image 20231206214311.png|400]]
### STEP-3
- In the server.js file import the router .
![[Pasted image 20231206214530.png|600]]
### STEP-4
![[Pasted image 20231206221534.png|500]]
## Imp - > the 'subdir' word gets added to the route inside subdir.js , so need not add subdir again.

Similarly do this for the main routes under the root.js file under the routings folder.


### Chaining of http requests->
![[Pasted image 20231207121500.png|500]]
All will go to the same route but have different request methods.