---
id: 01b6no6m0vu9dmezvbiuqwd
title: 3 - State Management in Functional Components
desc: ''
updated: 1738598741420
created: 1727313319389
---

**In React**, **state management allows components** `to manage and update` `data` `that affects` `the UI`. **With** `functional components`, **this is** `typically handled` `using` **the** '`useState`' `hook`, **which** `enables` `the component` `to remember` `values` `between renders`.

### **useState Hook**

The useState hook **allows you** `to add` `state` `to a functional component`. You `initialize it` `by passing` `the initial` `state value`, **and** `it returns` `two values`:

1. **The current state**: `A variable` `holding` **the** `state value`.
2. **A function to update the state**: **This** `function` `lets you` `change` `the state value`.

#### **Basic Syntax:**

```jsx
import { useState } from 'react';

function ExampleComponent() {
  // Declare a state variable 'count' and initialize it to 0
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
```

- **useState(0)**: **Initializes the state count to 0**.
- **setCount(count + 1)**: **Updates the state by incrementing the current count value**.

`When` **the** `state` `is updated`, **the** `component` `re-renders` **to reflect the new state**.

### **Key Points:**
- `Each` `call to` `useState` `creates` `a piece of state` `that's tied to` **the specific** `component` **instance**.
- `React` `ensures` **that the** `state is` `preserved` `between renders`.

### **Example with Multiple State Variables:**

```jsx
function UserProfile() {
  const [name, setName] = useState("John");
  const [age, setAge] = useState(25);

  return (
    <div>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
      <button onClick={() => setAge(age + 1)}>
        Increment Age
      </button>
    </div>
  );
}
```

**In this example**:
- **'name' and 'age' are** `two` **separate** `pieces of state`.
- `Each` `can be` `updated` `independently`.

### **Handling Objects in State**

`State` `can` **also** `be` `an object`, **and you** `can update` **specific** `properties` **within that object** `using` **the** `spread operator`.

```jsx
function UserSettings() {
  const [settings, setSettings] = useState({ theme: 'light', notifications: true });

  const toggleTheme = () => {
    setSettings({
        ...settings, // Spread the current settings to preserve other properties
        theme: settings.theme === 'light' ? 'dark' : 'light' }); // Toggle between 'light' and 'dark' theme
  };

  return (
    <div>
      <p>Theme: {settings.theme}</p>
      <button onClick={toggleTheme}>
        Toggle Theme
      </button>
    </div>
  );
}
```

**Here**, **'setSettings' updates only the 'theme' property**, **while keeping the 'notifications' property unchanged by spreading 'settings'**.

### **Why State Management is Important:**
- It allows you `to create` `dynamic and interactive` `user interfaces`.
- Components re-render automatically when state changes, `ensuring` **that** `the UI` `stays` `in sync` `with` `the data`.