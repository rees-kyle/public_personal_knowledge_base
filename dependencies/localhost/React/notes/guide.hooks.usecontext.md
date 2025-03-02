---
id: 3boy6z339ffqngws8xontma
title: 3 - useContext
desc: ''
updated: 1740591404508
created: 1729075424150
---

In React, 'useContext' **is a powerful** `Hook` `for managing` `global state`, **allowing** `data` **to be** `shared across` `different components` `without` `passing props down manually` `at each level`. Here's a breakdown of how to use it:

### Steps to Use 'useContext' for Global State Management:

1. **Create a Context:**
   **First**, you need to **create a Context**. This serves as a `container for` **the** `global state`.

   ```jsx
    import { createContext } from 'react';

    // Create a Context object to hold the global state
    // Optional: You can provide a default value in the parentheses (null in this case)
    const GlobalStateContext = createContext(null);

    export default GlobalStateContext;
   ```

2. **Create a Provider Component:**
   A Provider component is **responsible for** `passing the context value` (**global state**) `to the child components`.

   ```jsx
    import { useState } from 'react';
    import GlobalStateContext from './GlobalStateContext'; // Import the created context

    // Define the GlobalStateProvider component to wrap around parts of your app
    const GlobalStateProvider = ({ children }) => {
        // useState manages the global state, starting with 'user' set to null
        const [state, setState] = useState({
            user: null, // Example state (could be user data, theme settings, etc.)
        });

        return (
        // Provide the global state (state, setState) to any child component that needs it
        <GlobalStateContext.Provider value={{ state, setState }}>
            {children} {/* Render any child components inside the provider */}
        </GlobalStateContext.Provider>
        );
    };

    // Export the provider and the context for use in other components
    export { GlobalStateProvider, GlobalStateContext };
   ```

3. **Wrap Your App with the Provider:**
   To make the global state available throughout your app, wrap your app in the `GlobalStateProvider`.

   ```jsx
    import React from 'react';
    import ReactDOM from 'react-dom';
    import App from './App'; // Import the main App component
    import { GlobalStateProvider } from './GlobalStateProvider'; // Import the global state provider

    // Render the app and wrap it with the GlobalStateProvider to share global state
    ReactDOM.render(
    <GlobalStateProvider> 
        {/* Provide global state to the entire App */}
        <App />
    </GlobalStateProvider>,
    document.getElementById('root') // Attach the React app to the 'root' element in the HTML
    );
   ```

4. **Access the Global State in Components Using 'useContext':**
   Now, in any component, you can access and modify the global state using the `useContext` **Hook**.

   ```jsx
    import { useContext } from 'react';
    import { GlobalStateContext } from './GlobalStateProvider'; // Import the global state context

    const UserProfile = () => {
    // Use useContext to access the global state and setState from the GlobalStateContext
    const { state, setState } = useContext(GlobalStateContext);

    // Function to simulate user login by updating the global state
    const loginUser = () => {
        setState((prevState) => ({
        ...prevState, // Spread previous state to keep other state values unchanged
        user: { name: 'John Doe', loggedIn: true }, // Set a user object with name and loggedIn status
        }));
    };

    return (
        <div>
        <h1>User Profile</h1>
        {/* If user is logged in, show welcome message; otherwise, show login button */}
        {state.user ? (
            <p>Welcome, {state.user.name}!</p> 
        ) : (
            <button onClick={loginUser}>Login</button>
        )}
        </div>
    );
    };

    export default UserProfile;
   ```

### Key Points:
- **Context**: `Stores` `global data`.
- **Provider**: `Distributes` **the** `context` `to child components`.
- **useContext**: `Consumes` **the** `global data` `in any component`.

**This** `method` `eliminates` **the need for** `prop drilling and` **is** `perfect for` `managing application-wide state` **like** `authentication`, `themes`, **and** `user preferences`.