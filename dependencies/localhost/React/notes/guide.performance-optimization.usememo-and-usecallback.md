---
id: 530zssftewsm5eeguigcbow
title: 2 - useMemo and useCallback
desc: ''
updated: 1730215934922
created: 1730214631768
---

In React, '**useMemo**' **and** '**useCallback**' are used `for performance optimization` `by controlling` `when` `expensive functions` `are re-computed or re-created`. Here’s a **breakdown** of each:

---

### **useMemo**

- **Purpose**: `Memoizes` (**remembers**) **the** `output of` **a** `function` `to avoid` `recalculating` **it** `on every render`.
- **Usage**: 'useMemo' is **ideal** `for expensive calculations` **that** `only need to run` `when` **certain** `dependencies` `change`.
  
**Example**:
```javascript
import React, { useMemo } from 'react';

function ExpensiveComponent({ items }) {
  // Memoize the computedValue to avoid recalculating on every render
  const computedValue = useMemo(() => {
    // Calculate the sum of all item values in the items array
    return items.reduce((sum, item) => sum + item.value, 0);
  }, [items]); // Recalculate only when items array changes

  // Render the computed value
  return <div>Total Value: {computedValue}</div>;
}

export default ExpensiveComponent;
```

**In this case**, **the 'computedValue' will only recalculate when the 'items' array changes, avoiding unnecessary work**.

---

### **useCallback**

- **Purpose**: `Memoizes` **a** `function reference`, **so a** `new function` `isn’t created` `on each render`.
- **Usage**: Useful `for functions` **that are** `passed as props` `to child components`, `which could cause` `unnecessary re-renders`.

**Example**:
```javascript
import React, { useCallback } from 'react';

function ParentComponent() {
  // Memoize the handleClick function to prevent it from being recreated on each render
  const handleClick = useCallback(() => {
    console.log("Button clicked!");
  }, []); // No dependencies, so function is created only once

  // Pass the memoized handleClick function as a prop to ChildComponent
  return <ChildComponent onClick={handleClick} />;
}

function ChildComponent({ onClick }) {
  // Render a button that calls the onClick function when clicked
  return <button onClick={onClick}>Click Me</button>;
}

export default ParentComponent;
```

**Here**, **'handleClick' will only be created once because there are no dependencies**, **so the 'ChildComponent' won’t re-render unless explicitly required**.

---

### **Summary**:
- **'useMemo'**: `For caching` `values`.
- **'useCallback'**: `For caching` `function references`. 

`Both` **are handy** `for optimizing` `renders in large apps` `or components with costly calculations`!