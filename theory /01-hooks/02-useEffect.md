<h1>useEffect</h1>
<p>
=> "useEffect is a hook that runs after rendering, and it's used to handle side effects like fetching data, setting timers, or event listeners in React function components.We can control when it runs by passing a dependency array as the second argument."
</p>
---
<h1>Why does useEffect run after render?</h1>
<p>
    Because it’s a side effect — React needs to finish rendering the UI before performing operations that may affect the outside world.
</p>
---

<h1>What happens if I don’t provide a dependency array?</h1>
<p>
    The effect runs after every render, which can cause performance issues or infinite loops if not managed correctly.
</p>
---

                          useEffect(()=>{
                            // effect logic here

                            return()=>{
                              cleanUp logic (optional)  //unmount
                            };
                          },[dependencies]);

---

                          case 1: run on every render

                          useEffect(()=>{
                            alert("I will run on every render");
                          })



                          case 2: run only on first render
                          useEffect(()=>{
                            alert("I will run only on first render")
                          },[]);


                          case 3: run everytime when value changed

                          useEffect(()=>{
                            alert("I will run when value change");
                          },[value])
