Q.1 What is React?
=> React is a javascript library that is used to create SPA(single page application) .it is used for building fast, interactive, and reusable user interfaces using a component-based architecture.

---

Q.2 JSX?
JSX- Javascript XML allows html like code within javascript.JSX is not valid JavaScript, so it needs to be transpiled (usually by Babel) into standard JavaScript (e.g., React.createElement) before it can run in the browser.”

JSX example- const element = <h1>Hello, JSX!</h1>;
This will be transpiled into:=> const element = React.createElement("h1", null, "Hello, JSX!");

---

Q.3 Component
A component in React is a JavaScript function or class that returns a piece of JSX to define what should be rendered on the screen. React uses these components to build UIs in a modular and maintainable way.

---

Q.4 Reconciliation

reconciliation is the process React uses to diff one tree with another to determine what changes it has to made.

=>React creates a new virtual DOM everytime a component's state changes.
=>it then compares new virtual DOM to previous DOM(this is called diffing).
=>based on difference,it updates on the part of real DOM that changed.

==> this makes react fast and efficient avoiding full DOM re-render.

---
