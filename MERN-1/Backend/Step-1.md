- - -
## 1. Initialize NPM ->
- Run the command npm init to initialise npm.
- Install all the necessary packages.
- npm i nodemon -D    FOR INSTALLING DEVELOPMENT DEPENDENCY
- Inside the packages.json in the script , write this 
![[Pasted image 20231216222210.png|400]]
1. **"scripts"**: This section is used to define custom scripts that can be executed using npm (Node Package Manager). These scripts can be invoked using the `npm run` command.
    
2. **"start" : "node server"**: This script is named "start". When you run `npm run start`, it will execute the command `node server`. This is typically used to start the application in a #production environment. It assumes that there is a file named `server.js` (or something similar) in the project, and it will be executed by the Node.js runtime.
    
3. **"dev":"nodemon server"**: This script is named "dev". When you run `npm run dev`, it will execute the command `nodemon server`. Unlike the "start" script, this is typically used for #development purposes. `nodemon` is a tool that monitors for changes in files and automatically restarts the Node.js application when changes are detected. This is useful during development because it saves you from manually restarting the server every time you make a change to your code.


## 2. Include the files inside the .gitignore file.

## 3. Don't forget to serve the static files inside the 'public folder'.

- - -


