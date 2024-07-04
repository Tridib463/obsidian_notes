- - -
#### NodeJS 
is a JavaScript runtime that enables a computer to act as a server with the help of JavaScript programming language.
But using a backend programming language is itself difficult, so there are two tools that we use to help with this - 
1. A Backend Framework (EXPRESS JS) / Python Django
2. A Package(code that other people have written) manager (npm for nodeJS / pip for python)
## Native Node Modules :->

This modules(code already written) come pre-bundled with node to be used as tool by users.
Right now, we will filesystem(fs) module which allows us to create, read, update and delete files and work with directories on the server.

### File Operations ->

Read, Write and Append File in VS-Code (Node_modules)
1. Delete a file
```javascript
await fsPromises.unlink(path.join(__dirname,'name of the folder','name of the file we want to delete'));
```

### Stream operations ->

If we have larger data, sometimes it is good to not grab all the data at once. Rather we can do chunk by chunk.  