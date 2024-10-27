---
id: qzhmy917oz1xotdtvmplfn5
title: 1 - Fetching Data
desc: ''
updated: 1730045337621
created: 1730043055907
---

**Fetching data from an API is a core skill in JavaScript and React projects**. Here’s a quick **overview** of how to do it with both '`fetch`' **and** '`axios`'.

### Using 'fetch'

The 'fetch' API is `native to JavaScript` **and** `returns a 'Promise'`. Here’s a **basic example** of how to use it:

```javascript
// Fetching data from the API using fetch
fetch('https://api.example.com/data')
  .then(response => {
    // Check if the response is successful (status in the range 200-299)
    if (!response.ok) {
      // If response is not ok, throw an error
      throw new Error('Network response was not ok');
    }
    // Parse the JSON from the response
    return response.json();
  })
  .then(data => {
    // Handle and process the fetched data here
    console.log(data);
  })
  .catch(error => {
    // Log any errors that occur during the fetch operation
    console.error('There was a problem with the fetch operation:', error);
  });
```

#### In Async/Await Style

```javascript
// Define an asynchronous function to fetch data
async function fetchData() {
  try {
    // Await the response from the fetch request
    const response = await fetch('https://api.example.com/data');

    // Check if the response was successful
    if (!response.ok) {
      // If not successful, throw an error
      throw new Error('Network response was not ok');
    }

    // Await and parse the response data as JSON
    const data = await response.json();

    // Log the data to the console
    console.log(data);
  } catch (error) {
    // Catch and log any errors that occur during fetch
    console.error('Fetch error:', error);
  }
}

// Call the fetchData function to execute the fetch request
fetchData();
```

### Using 'axios'

'axios' is **a popular** `library` `for making HTTP requests`. It’s `easier` **to use** `than 'fetch'` **in some ways because it** `automatically transforms` **the** `response` `to JSON` **and** `simplifies` `error handling`.

```bash
# BASH
npm install axios
```

```javascript
import axios from 'axios'; // Import axios for making HTTP requests

// Make a GET request to the specified API endpoint
axios.get('https://api.example.com/data')
  .then(response => {
    // Log the data received from the response
    console.log(response.data); // Access the data directly
  })
  .catch(error => {
    // Log any errors that occur during the request
    console.error('There was an error with the request:', error);
  });
```

#### In Async/Await Style

```javascript
// Import axios to make HTTP requests
import axios from 'axios';

// Define an asynchronous function to fetch data
async function fetchData() {
  try {
    // Await the response from the axios GET request
    const response = await axios.get('https://api.example.com/data');

    // Log the received data to the console
    console.log(response.data);
  } catch (error) {
    // Catch and log any errors that occur during the request
    console.error('Axios error:', error);
  }
}

// Call fetchData function to execute the request
fetchData();
```

### Key Differences

- **Error Handling**: '`fetch`' `does not throw` `an error` `for HTTP errors` (**like** '`404`' **or** '`500`'), `whereas 'axios'` `does`.
- **Response Parsing**: '`fetch`' `requires '.json()'` `to parse the response`, `while 'axios'` `automatically parses` **it** `for JSON responses`.
- **Interceptors**: '`axios`' `supports interceptors` `to modify requests or responses` `globally`, which is **useful** `for handling authentication`. 

`Both` **approaches** `work well`, **so** `choose` `based on` **your** `project’s needs` **and** `personal preference`.