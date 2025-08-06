<h1>What is useState ?</h1>
<p>
useState is a hook in Reactjs.
    it allows functional components to store and manage local state. something that was previously only possible in class components using this.state.
          With useState, we can make components interactive and dynamic.
            It triggers a re-render whenever the state changes.
</p>

<h3>=> Syntax :</h3>
<p> 
const [state, setState] = useState(initialValue);

    state=> current state value
    setState=> function to update the state
    initialValue=> default value when components load

</p>
<p>
import React, { useState } from 'react';

function Counter() {
const [count, setCount] = useState(0);

return (

<div>
<h2>Count: {count}</h2>
<button onClick={() => setCount(count + 1)}>Increase</button>
</div>
);
}
</p>
___________________________________________________________________________________________________________
<h1>Can you update state directly?</h1>
<p>
=> No , directly updating state will not re-render the component
</p>
---

<h1>What if the new state depends on the previous state?</h>
<p>
=>
setCount(prev => prev + 1);

     Always use callback form when using previous state to avoid race conditions.

 </p>

<h1>What types of data can you store in useState?</h1>
<p>
    Any type: string, number, boolean, array, object, or even a function.
</p>
---

<h1> Why doesn’t React update the state immediately?</h1>
<p>
    State updates in React are asynchronous. React batches updates for performance.
</p>
---

<h2>Object State Example (Handling complex objects)</h2>
<p>
        const [user, setUser] = useState({ name: '', age: 0 });

        function updateName(newName) {
          setUser(prev => ({ ...prev, name: newName }));
        }

</p>

<h2>Array State Example (Add item to list)</h2>
<p>
const [todos, setTodos] = useState([]);

function addTodo(newTodo) {
setTodos(prev => [...prev, newTodo]);
}

</p>
