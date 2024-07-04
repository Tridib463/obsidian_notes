- - -
## Why should we learn ReactJS ? 
- React is component based and each of that component can be used and reused.
- If we to change or update a single portion of a page, only that portion will get rendered without reloading the whole page.
## Installation :->
 1. Run npx create-react-app in the terminal. 'npx' is **the package runner used by npm to execute packages in place of a global install**. It basically creates a temporary install of React so that with each new project you are using the most recent version of React.
 2. npm - install packages         npx - execute packages
 - - -
## File Structure :->

![[Pasted image 20230930120512.png|700]]
- node_modules -> Has all the node modules installed
- public -> Has one index.html file that loads into the browser after that React takes over and presents the rest of the content. Has other files too but we won't really do anything with public.
- src -> This is a source folder that we will use ->
            1. index.js - > This file populates the index.html with App.js file.
            2. App.js -> This is the main file that we will be working on. This is the parent file.
- package.json -> This is a configuration file which contains all the details about the project like dependencies, script, version , etc. With the help of dependencies listed in this file, nodeJS will know which packages to pull in from the node_modules. We keep the node_modules in gitignore as we don't need to upload the modules in GIT. When another person clones or downloads our project, nodeJS will  automatically download  all the node packages necessary for the project from the node_modules by the command - npm i. 

![[Pasted image 20231001183522.png|800]]
---
## How to start the React App :->

Type the command
```bash
npm start
```
