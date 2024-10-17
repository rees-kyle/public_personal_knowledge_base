---
id: 40gb1wntjb04b1d4djnz2v5
title: 1 - Context API
desc: ''
updated: 1729166771829
created: 1729165399460
---

The Context API **is a** `built-in feature` **in React** `for managing state` `across different components` `without` `the need to pass props` `manually at every level`. It **allows you** `to create` `global variables` **that can be** `shared across` `a React component tree`, **making it easier** `to manage state` `in medium-sized applications`.

### How it works:

1. **Creating Context:**
   - First, you `create` `a context object` **using** `React.createContext()`. This object **will be used to share the state between components**.

2. **Provider:**
   - The `Provider component` **allows consuming components** `to subscribe` `to context changes`. It **takes a value prop that contains the state you want to share**.

3. **Consumer or useContext:**
   - There are `two ways` `to consume context`. You can either use the `Context.Consumer` **component or** the `useContext` **hook**, **which is simpler and more concise**.

### Example:

```jsx
import React, { createContext, useState, useContext } from 'react';

// Create a context for the theme
const ThemeContext = createContext();

// ThemeProvider component that manages the theme state
const ThemeProvider = ({ children }) => {
  // Set initial theme state to 'light'
  const [theme, setTheme] = useState('light');

  return (
    // Provide the theme and setTheme function to the context
    <ThemeContext.Provider value={{ theme, setTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

// Component that consumes the theme context
const ThemedComponent = () => {
  // Access the current theme and the function to change it
  const { theme, setTheme } = useContext(ThemeContext);

  return (
    <div>
      {/* Display the current theme */}
      <p>The current theme is {theme}</p>
      {/* Button to toggle between light and dark themes */}
      <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
        Toggle Theme
      </button>
    </div>
  );
};

// Main App component
export default function App() {
  return (
    // Wrap the ThemedComponent in the ThemeProvider to provide theme context
    <ThemeProvider>
      <ThemedComponent />
    </ThemeProvider>
  );
}
```

### Key Points:
- **Context API** is ideal `for managing` `global state`, **like** `theme`, `user authentication`, **or** `language settings`.
- It `prevents` "`prop drilling`", **where props are passed through multiple levels of components unnecessarily**.
- It's `more lightweight` `compared to` `state management libraries` **like** `Redux`, **making it** `perfect for` `small to medium-sized` `applications`.