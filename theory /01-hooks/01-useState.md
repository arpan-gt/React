Q. What is useState ?
=> useState is a hook in Reactjs.
=> it allows functional components to store and manage local state. something that was previously only possible in class components using this.state.
=> With useState, we can make components interactive and dynamic.
=> It triggers a re-render whenever the state changes.

=> Syntax : 
const [state, setState] = useState(initialValue);

    state=> current state value
    setState=> function to update the state
    initialValue=> default value when components load

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

___________________________________________________________________________________________________________
Q2. Can you update state directly?
=> No , directly updating state will not re-render the component

________________________________________________________________________________________________________
Q3. What if the new state depends on the previous state?
=>
    setCount(prev => prev + 1);

     Always use callback form when using previous state to avoid race conditions.

________________________________________________________________________________________________________
Q4. What types of data can you store in useState?

    Any type: string, number, boolean, array, object, or even a function.

_________________________________________________________________________________________________________
Q5. Why doesn’t React update the state immediately?

    State updates in React are asynchronous. React batches updates for performance.

___________________________________________________________________________________________________________
🛠 Object State Example (Handling complex objects)

        const [user, setUser] = useState({ name: '', age: 0 });

        function updateName(newName) {
          setUser(prev => ({ ...prev, name: newName }));
        }

___________________________________________________________________________________________________________
🔄 Array State Example (Add item to list)
          const [todos, setTodos] = useState([]);

          function addTodo(newTodo) {
            setTodos(prev => [...prev, newTodo]);
          }

