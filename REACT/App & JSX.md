- - -
## JSX :->

 In JSX File we can write JavaScript independently  and also we can write JavaScript inside the HTML. When writing inside  HTML we will write JavaScript inside { } curly brackets.

```JSX
import './App.css';

function App() //main parent component
{
  const handleName = () =>{
    const names = ['Tridib', 'Parthiv', 'Pradip'];
    const int = Math.floor(Math.random() * 3);     //this is a javascript code
    return names[int];
	 }

  return (
    <div className="App">
      <p>
        Hello {handleName()} !
      </p>  
    </div>
  );
}

export default App
```

### OUTPUT - >
![[Pasted image 20231001193053.png|600]]
![[Pasted image 20231001193120.png|600]]
![[Pasted image 20231001193147.png|600]]