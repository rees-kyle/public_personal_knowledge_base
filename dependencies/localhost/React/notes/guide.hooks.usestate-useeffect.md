---
id: c7lwlknunyocml5bckeenii
title: 1 - useState, useEffect
desc: ''
updated: 1727663435454
created: 1727659194893
---

Hooks like '`useState`' **and** '`useEffect`' are `fundamental to` **React's** `functional components`.

### 1. **useState**
The useState hook **allows you** `to add` `state` `to a functional component`. Here's a basic **example**:

```jsx
import React, { useState } from 'react';

function Counter() {
  // Declare a state variable 'count' initialized at 0
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

export default Counter;
```
- **useState takes the initial state value** (**e.g.**, **0 for the count**) **and returns an array with two elements**: **the current state and a function to update that state**.

### 2. **useEffect**
The useEffect hook **allows you** `to perform` `side effects` `in function components`. It's **commonly used** `for data fetching`, `subscriptions`, `or manually changing the DOM`.

```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
  const [seconds, setSeconds] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds(seconds => seconds + 1);
    }, 1000);

    // Cleanup the interval on component unmount
    return () => clearInterval(interval);
  }, []); // Empty array ensures this effect runs once (after initial render)

  return (
    <div>
      <p>{seconds} seconds have passed.</p>
    </div>
  );
}

export default Timer;
```
- **useEffect takes two arguments**: **a function containing the side-effect logic and an optional dependency array**. **If the dependency array is empty** (**[]**), **the effect runs only once**, **after the initial render**. **If you provide dependencies** (**state or props**), **it runs whenever those values change**.