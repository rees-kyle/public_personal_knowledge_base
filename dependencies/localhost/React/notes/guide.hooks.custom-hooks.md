---
id: 4kvlfowu5ipbgimycdjmf4l
title: 2 - Custom Hooks
desc: ''
updated: 1727750384203
created: 1727749727828
---

Custom hooks in React allow you `to extract and reuse` `stateful logic` `across multiple components`. **They follow the same rules as standard hooks but provide a way** `to share logic` `without repeating code`. **Custom hooks are** `JavaScript functions` `that begin with` **the word** "`use`," **as per React’s naming convention**.

### How to Create a Custom Hook

1. **Identify Reusable Logic:**
   If you have logic that is used by multiple components, **like** `fetching data` **or** `managing state`, it can be abstracted into a custom hook.

2. **Create a Hook Function:**
   Custom hooks are **regular** `JavaScript functions`, **but they** `can call` `other hooks` (**like** `useState`, `useEffect`, **etc**.).

3. **Naming Convention:**
   The hook’s name should `start with` "`use`" **to comply with React’s rules of hooks**.

### Example of a Custom Hook

Let’s create **a simple custom hook that fetches data from an API**.

```jsx
// useFetch.js

// Import necessary hooks from React
import { useState, useEffect } from 'react';

// Define a custom hook called useFetch that takes a URL as an argument
function useFetch(url) {
  // Declare state variables for storing the fetched data and loading status
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  // useEffect hook runs when the component mounts or when the URL changes
  useEffect(() => {
    // Define an asynchronous function to fetch data from the given URL
    async function fetchData() {
      const response = await fetch(url);  // Make an API request to the URL
      const result = await response.json(); // Convert the response to JSON
      setData(result); // Store the fetched data in the 'data' state
      setLoading(false); // Set 'loading' to false once data is fetched
    }

    // Call the fetchData function
    fetchData();
  }, [url]); // Dependency array ensures the effect runs when 'url' changes

  // Return the fetched data and loading status
  return { data, loading };
}

// Export the custom hook so it can be used in other components
export default useFetch;
```

### Using the Custom Hook in a Component

```jsx
// Import React and the custom useFetch hook
import React from 'react';
import useFetch from './useFetch';

// Define the DataDisplay component
function DataDisplay() {
  // Use the custom useFetch hook to fetch data from the given API
  const { data, loading } = useFetch('https://api.example.com/data');

  // If data is still loading, display a loading message
  if (loading) return <p>Loading...</p>;

  // Once data is loaded, map through the data and display each item
  return (
    <div>
      {data.map((item) => (
        // Each item is rendered as a paragraph with a unique key
        <p key={item.id}>{item.name}</p>
      ))}
    </div>
  );
}

// Export the DataDisplay component for use in other parts of the app
export default DataDisplay;
```

### Key Points:
- **Custom hooks allow the** `reuse` **of** `stateful logic` `between components`.
- **They can** `manage state`, `make API calls`, `or encapsulate any logic that needs to be reused`.
- **Custom hooks** `follow the same rules as built-in hooks`, **such as** `not being called inside loops`, `conditions`, `or nested functions`.