---
id: 8iwzhqbie6acmt6ki33x4m3
title: 2 - Hooks
desc: ''
updated: 1727570917110
created: 1727569823789
---

**React** `Hooks`, **such as** '`useEffect`' **and** `'useLayoutEffect`', **are used** `to control` `and interact with` `lifecycle phases` `in functional components`.

### **Component Lifecycle Phases**
1. **Mounting** – When the `component` **is** `initialized` `and added to the DOM`.
2. **Updating** – When the `component` **is** `re-rendered` `due to changes` `in state or props`.
3. **Unmounting** – When the `component` **is** `removed` `from the DOM`.

### **'useEffect' Hook**
'useEffect' **allows you** `to perform` `side effects` `in function components`. It `runs after the component renders` **and** `can optionally clean up` `when the component unmounts` `or before the next render`.

#### Syntax:
```javascript
useEffect(() => {
  // Your side-effect code here (like API calls, data fetching, etc.)

  return () => {
    // Clean up code (optional)
  };
}, [dependencies]);
```
- The **callback** `runs` `after the render`.
- The **cleanup** (`if provided`) `runs` `when the component is unmounted` `or before the next effect`.
- The **dependencies array** `tells React` `when to run the effect`. `If empty` '[]', it `runs` `only once` (`after` **the** `initial render`). `If there are values` (**e.g.**, '**[prop, state]**'), it `runs` `whenever those values change`.

#### Common Use Cases:
- **Data fetching**: `Load data` `after a component mounts`.
- **Event listeners**: `Attach or clean up` `event listeners`.
- **Subscribing/unsubscribing** `to services or sockets`.

### **'useLayoutEffect' Hook**
'useLayoutEffect' is `similar to 'useEffect'` `but differs in timing`. It `runs synchronously` `after all DOM mutations` `but before the browser has painted the screen`. This is **useful when you need** `to measure or adjust` `the DOM` `before it becomes visible` `to the user`.

#### Syntax:
```javascript
useLayoutEffect(() => {
  // DOM-related side-effects

  return () => {
    // Clean up code
  };
}, [dependencies]);
```

#### When to Use 'useLayoutEffect':
- **Measuring DOM elements**: If you need `to measure or calculate layout` `before the browser paints`, **like** `getting the size of an element` `after it renders`.
- **Syncing animations**: `Ensuring` **that** `visual updates happen synchronously` `with the rendering process` `to avoid layout shifts`.

### Key Differences
- **'useEffect'** `runs asynchronously` `after the DOM is painted`.
- `'useLayoutEffect'` `runs synchronously` `after the DOM updates` `but before painting`. It **can block the paint**, **so avoid heavy calculations**.

### Summary:
- **Use** `'useEffect'` `for side effects` `that don’t affect layout` `or need to happen after the render` (**e.g.**, **API calls**).
- **Use** `'useLayoutEffect'` **when you need** `to manipulate the DOM` `or perform measurements before the browser paints`.

**These** `hooks` **are powerful tools** `to manage the lifecycle and effects` `in functional components`.