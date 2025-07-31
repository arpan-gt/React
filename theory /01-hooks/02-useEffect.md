useEffect
=> "useEffect is a hook that runs after rendering, and it's used to handle side effects like fetching data, setting timers, or event listeners in React function components.We can control when it runs by passing a dependency array as the second argument."

---

Q: Why does useEffect run after render?

    Because it’s a side effect — React needs to finish rendering the UI before performing operations that may affect the outside world.

---

Q: What happens if I don’t provide a dependency array?

    The effect runs after every render, which can cause performance issues or infinite loops if not managed correctly.

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
