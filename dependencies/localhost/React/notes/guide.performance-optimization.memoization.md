---
id: to0tmvjspo26wcd6067cgx0
title: 1 - Memoization
desc: ''
updated: 1730214476632
created: 1730211152798
---

React provides '`React.memo`' as a way `to optimize` `functional components` `by memoizing` **their** `output`. This is particularly `helpful when` **you have** `components` **that** `receive` **the** `same props` `frequently`, as it **can help** `reduce` `unnecessary re-renders`.

Here's how 'React.memo' works and **how to use** it:

### How React.memo Works
'**React.memo**' **is a** `higher-order component` (`HOC`) **that** `only re-renders` **the** `component if` **its** `props change`. `If` **the** `same props` **are** `passed again`, `React reuses` **the** `previous render`, `making` **your** `component` `faster` `by avoiding` `unnecessary updates`.

### Basic Usage of React.memo

```javascript
import React from 'react';

// Memoized component to prevent unnecessary re-renders
const MyComponent = React.memo(({ value }) => {
  // Log to check when the component is rendering
  console.log("Rendering MyComponent");
  
  // Display the 'value' prop in a div
  return <div>{value}</div>;
});

// Exporting the component to use it in other parts of the app
export default MyComponent;
```

**In this example**:
- **'MyComponent' only re-renders when 'value' changes**.
- **If 'value' stays the same, React skips the re-render, increasing performance**.

### Custom Comparison Function
**Sometimes**, you may need a custom comparison function `to determine` `whether` **the** `props are` `the same`. You **can** `pass` **a** `second argument to` `React.memo` `to control` **this** `behavior`.

```javascript
// Import React to use React.memo
import React from 'react';

// Memoized component to prevent unnecessary re-renders based on custom comparison
const MyComponent = React.memo(
  ({ obj }) => {
    // Log to check when the component is rendering
    console.log("Rendering MyComponent");
    
    // Display the 'text' property from the 'obj' prop in a div
    return <div>{obj.text}</div>;
  },
  // Custom comparison function to check if the 'id' in 'obj' has changed
  // Re-renders only if 'obj.id' is different from the previous render
  (prevProps, nextProps) => prevProps.obj.id === nextProps.obj.id
);

// Exporting the component to use it in other parts of the app
export default MyComponent;
```

**In this example**:
- **'MyComponent' only re-renders if the 'id' of 'obj' changes**, **ignoring other properties like 'text'**.

### When to Use React.memo
Use 'React.memo' when:
- **A** `component is` “`pure`” **and has** `stable props` `that rarely change`.
- **You notice** `unnecessary re-renders` `in components` `lower in` **the** `hierarchy` `due to unchanged props`.
  
### When Not to Use React.memo
- **Avoid** 'React.memo' `for components` `that frequently change props` `or are deeply nested`.
- It **can add slight overhead for complex components**, so `only use it` `where you notice` **actual** `performance gains`. 

`Using` '`React.memo`' **effectively** `can lead to` `noticeable improvements`, **especially** `in large applications`.