---
id: 3pvwzt9w4mz89i5znyfw5js
title: 2 - Error Handling and Loading States
desc: ''
updated: 1730049479087
created: 1730047598676
---

To implement error handling and loading states effectively during API interactions, here are the **main approaches** you might consider, especially in React:

### 1. **Loading State**
   - **Purpose**: `Indicate to` **the** `user` **that the** `data` **is** `being fetched`.
   - **Implementation**: `Use` **a** `'loading' state variable` `to show` **a** `loading spinner or placeholder content` `while` **the** `data` **is** `being fetched`.

   ```javascript
    // Set up a loading state to track if data is being fetched
    const [loading, setLoading] = useState(true);

    useEffect(() => {
    // Start loading when the component mounts
    setLoading(true);

    // Call fetchData function, which fetches data from an API
    fetchData()
        // If successful, stop loading
        .then(() => setLoading(false))
        // If there’s an error, stop loading (you could also handle errors here)
        .catch(() => setLoading(false));
    }, []); // Empty dependency array means this only runs on mount

    return (
    <>
        {/* Show a loading spinner if loading is true, otherwise show the content */}
        {loading ? <LoadingSpinner /> : <DataContent />}
    </>
    );
   ```

### 2. **Error Handling**
   - **Purpose**: Gracefully `handle errors` `by displaying` **appropriate** `messages or retry options`.
   - **Implementation**: `Use` **an** `'error' state variable` `to capture errors`, `display them`, **and** `provide an option to retry`.

   ```javascript
    // Initialize an error state to store any error messages
    const [error, setError] = useState(null);

    const fetchData = async () => {
    try {
        // Set loading to true when fetching starts
        setLoading(true);

        // Send a request to the API
        const response = await fetch('API_URL');

        // Check if the response is successful
        if (!response.ok) throw new Error('Failed to fetch data');

        // Parse the JSON data from the response
        const data = await response.json();

        // Update your data state with the fetched data (assuming setData is defined elsewhere)
        setData(data);

    } catch (err) {
        // If there's an error, store the error message in the error state
        setError(err.message);
    } finally {
        // Set loading to false after the fetch completes, regardless of success or error
        setLoading(false);
    }
    };

    return (
    <>
        {/* If there's an error, show the error message with a retry button; otherwise, show the data content */}
        {error ? <ErrorMessage message={error} onRetry={fetchData} /> : <DataContent />}
    </>
    );
   ```

### 3. **Combine Loading and Error States**
   - **Purpose**: `Create` **a** `more robust` `user experience` `by ensuring` `only one state` `is active at a time`.
   - **Implementation**: `Display` **the** `loading spinner` `while fetching data`, `show` `error messages` **if an error occurs**, **and** `only show content` `when data is` `loaded successfully`.

   ```javascript
    return (
    <>
        {/* Show a loading spinner while data is being fetched */}
        {loading && <LoadingSpinner />}

        {/* If there's an error, display the error message with a retry option */}
        {error && <ErrorMessage message={error} onRetry={fetchData} />}

        {/* If not loading and no error, display the data content */}
        {!loading && !error && <DataContent />}
    </>
    );
   ```

### 4. **User-Friendly Elements**
   - **Loading Indicator**: A `spinner or skeleton loader` **is helpful** `for loading states`.
   - **Error Retry Option**: An `option` `to retry the API call` **can** `improve usability`, **especially** `if` **the** `error` **could be** `transient`.

`This setup` **makes** `API interactions` **in React** `user-friendly` **and** `resilient`, **addressing both the need** `for immediate feedback` `during` `loading and error handling` **if issues arise**.