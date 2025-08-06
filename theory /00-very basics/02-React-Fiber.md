<h1>React Fiber</h1>

<h1>What is Virtual DOM?</h1>
<p>
    The virtual DOM (VDOM) is just a JavaScript object that represents the actual UI.

     It’s a lightweight copy of the real DOM.

       React uses it to figure out what changed and what needs updating, rather than directly touching the real DOM every time (which is slow).

</p>

=> <h1>Old React (before v16):</h1>
<p>
     Had a virtual DOM

      Used a synchronous, recursive reconciliation algorithm

        Could not:

          Pause work

          Schedule tasks

          Prioritize updates
</p>
---

<h1>React Fiber (v16+):</h1>
<p>
    Still uses a virtual DOM — this didn’t go away

      But the algorithm to manage and update the virtual DOM has been completely rewritten

        Now it's based on:

            Fibers (units of work)

              A Fiber tree (a more powerful version of the virtual DOM tree)

                Time slicing, prioritization, pausing, and resuming
</p>
--
<p>
React still uses the virtual DOM for reconciliation.
But instead of a basic recursive diffing system, React now uses the Fiber architecture to manage it more efficiently, with scheduling and prioritization built in.
</p>
---

<h1>What is React Fiber?</h1>
<p>
      Fiber = The engine React uses to update the UI.

        changed and updates the UI accordingly.
</p>
---

<h1>Why Fiber? (Problem it solves)</h1>

<h2>Old React:</h2>
<p>
    UI updates were done all at once

      Couldn't pause, stop, or prioritize work

        Big components made apps slow or laggy
</p>
<h2>React Fiber:</h2>
<p>
Can pause work and come back later

     Can cancel work if it's no longer needed

      Can prioritize more important updates

        Supports features like Concurrent Rendering, Suspense, Transitions
</p>

---

<h1>What is a Fiber?</h1>
<p>
A Fiber is a JavaScript object that holds all the information about one component.

    You can think of it as a custom lightweight stack frame for React.

Each Fiber represents:

    A component (like <App />)

      Its props and state

        Who its parent, children, and siblings are

          Whether it needs to be updated

          Its priority
</p>
---

<h1>How UI is updated using Fiber</h1>
<p>
Step-by-step:

    You call setState() or useState()

    React creates a new fiber tree (called "work in progress")

      It compares it to the old fiber tree

        Finds the differences

          Applies those changes to the DOM

This process is called reconciliation.
</p>
---

<h1>Two Trees: Current and Work-In-Progress</h1>
<p>
React keeps two versions of the fiber tree:

    Current Tree → what’s on screen now

     Work-In-Progress Tree → new version being prepared

Once the new tree is ready, it becomes the new current tree.
</p>
---

<h1>Summary (1 Line per Point)</h1>
<p>
    Fiber is React’s new rendering engine.

      It improves performance and responsiveness.

        Fiber breaks work into chunks (small tasks).

          It schedules high-priority tasks first.

            It supports features like Suspense and concurrent rendering.

              Each component = 1 fiber.

                React builds 2 trees (current and work-in-progress).

                  After diffing, changes are committed to the DOM.
</p>