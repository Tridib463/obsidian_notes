- - -
![[Pasted image 20231104110545.png|600]]

- In JSON, all properties and strings must use "Double Quotes"....except Integers and Boolean.
- JSON does not support Functions.

![[Pasted image 20231104110822.png|800]]

## Why do we use JSON?
![[Pasted image 20231104110908.png|600]]
- JS Objects only make sense in JavaScript but JSON is Platform-Independent and is used to transfer data from one computer to another.
(use jsonviewer.stack.hu)
### JS-Object to JSON->
```javascript
const jsonData = JSON.stringify(data);
//the data is the JS Object.
```

### JSON to JS-Object->
```javascript
const data = JSON.parse(jsonData);
```

## .env ->

