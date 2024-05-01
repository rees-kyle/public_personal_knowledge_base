---
id: zoegga4ijdxrl5lp7m6i34n
title: 2 - Fetch API
desc: ''
updated: 1714607700100
created: 1714440457882
---

The Fetch API is a modern interface that **allows JavaScript to** `make` `HTTP requests to` `servers` `from web browsers`. **This API provides a more powerful and flexible feature set compared to older methods such as XMLHttpRequest**. With the Fetch API, developers can easily handle various aspects of making HTTP requests and `processing responses`. **This API** `returns Promises`, **thereby enabling a** `cleaner` **and** `more efficient` **way** `to manage` `asynchronous operations` **compared to callbacks**.

### Key Features of the Fetch API:

- **Promise-based**: Makes use of Promises to handle asynchronous operations, allowing for `more manageable` **and** `cleaner` `code`.
- **Flexible and powerful**: `Supports` **a** `wide range of` **HTTP** `requests` **and can** `handle` `various` `data formats`.



<!-- start of 'format' section -->
<details>
  <summary>Definition: format</summary>

#
The term "format" **refers to the** `way` **in which** `something is` `arranged`, `organized`, **or** `presented`. In **different contexts**, it **can describe the layout of a document**, **the structure of data**, the **configuration of a media file**, **or the design of an event**.

---
</details>
<!-- end of 'format' section -->



<!-- start of 'data formats' section -->
<details>
  <summary>Definition: data formats</summary>

#
Data formats **refer to the** `specific ways` **in which** `data is` `structured` **and** `encoded for` `storage`, `processing`, **and** `communication`. These formats **ensure that data can be correctly interpreted and used by different software and systems**.

---
</details>
<!-- end of 'data formats' section -->



- **Stream interface**: The **API provides a stream interface for the response body which allows you to start** `processing` `received data` **as soon as chunks are available**, **instead of waiting for the entire response**.



<!-- start of 'interface' section -->
<details>
  <summary>Definition: interface</summary>

#
An interface **is a** `point of` `interaction` `between` `different systems`, `devices`, **or** `software`, **allowing them** `to communicate` **and** `work together`. **It defines a set of rules or methods for exchanging information or commands**.

---
</details>
<!-- end of 'interface' section -->



<!-- start of 'stream interface' section -->
<details>
  <summary>Definition: stream interface</summary>

#
A stream interface **is a type of** `interface that` `allows for` **the** `sequential input` `or output` `of data`. **It enables the continuous flow of data between a source and a destination**, **typically in a one-directional manner**, **such as reading from or writing to a file or network connection**.

---
</details>
<!-- end of 'stream interface' section -->



- **Control over request and response**: **Allows detailed** `setting of` `request headers`, `caching strategies`, `credentials`, **and more**. Also, **it provides** `access to` `metadata` `about` **the** `response` (**like status code and headers**).

### Basic Usage:

Here’s a simple example of how to use the Fetch API to make a `GET` **request**:

```javascript
// Use `fetch` API to make an HTTP GET request to specified URL
fetch('https://api.example.com/data')

  // First `.then` checks if response from server is successful, if response status is not in range 200-299, throw error
  .then(response => {
    if (!response.ok) {
        throw new Error('Network response was not ok');
    }

    // If response is successful, parse the JSON body of the response
    return response.json();
  })

  // After converting response to JSON, log JSON data to console
  .then(data => console.log(data))
  // If there is any error during fetch or during response processing, it will be caught here and logged to console
  .catch(error => console.error('There was a problem with the fetch operation:', error));
```

### Making a POST Request:

You can also `send` `data to` **a** `server` using the Fetch API `by specifying` **an additional** `init` **object** that allows you `to control` **various** `settings like` `method`, `headers`, `body`, `etc`.

```javascript
// Define data object that will be sent to server
const data = { username: 'example' };

// Use fetch API to send HTTP POST request to server
fetch('https://api.example.com/users', {
  // Specifies method for request, 'POST' or 'PUT'
  method: 'POST',
  headers: {
    // Sets content type of request to JSON
    'Content-Type': 'application/json', 
  },
  // Converts data object into JSON string; to be sent in request body
  body: JSON.stringify(data),
})

.then(response => {
  // Parses JSON response into a JavaScript object after the request is completed
  return response.json();
})
.then(data => {
  // Logs success message and data received from server to console
  console.log('Success:', data);
})
.catch(error => {
  // Catches and logs any errors that occurred during fetch operation
  console.error('Error:', error);
});
```

### Error Handling:

The `Fetch API` **itself** `does not` `throw` **an** `error` `for HTTP error statuses` (**like 404 or 500**). **Instead**, the `promise` `resolves normally` (**with** `response.ok` **set to** `false`), **and it** `must be` `handled explicitly`:

```javascript
// fetch request to specified URL
fetch('https://api.example.com/data')
  .then(response => {
    // Checks if the response from the server is successful
    if (!response.ok) {
        // If the response has an HTTP status code indicating an error (outside 200-299),
        throw new Error(`HTTP error! status: ${response.status}`); // throw an Error with a message including the status code
    }
    // If response is successful, parse JSON body of response; to convert it into JavaScript object
    return response.json();
  })

  // After parsing JSON, log data object to console
  .then(data => console.log(data))
  // Catch any errors thrown in fetch or JSON parsing phase, and log a custom error message along with error object
  .catch(error => console.error('There was a problem with your fetch operation:', error));
```

### Advanced Features:

- **Abort a fetch**: This **can be useful if you need** `to cancel` **a** `request` `due to` `user interaction` (`like navigation or` simply `aborting` **a** `file download`).
- **Integrating with Service Workers**: Fetch is **fully** `compatible with` `service workers` **allowing you** `to easily cache or` `modify requests` **and** `responses`.



<!-- start of 'service workers' section -->
<details>
  <summary>Definition: service workers</summary>

#
Service workers **are** `scripts` `that run in` **the** `background on` **a** `user's browser`, `providing features that` `don't need` **a** `web page or` `user interaction`. They are **primarily used** `to handle` `network requests`, `cache app resources`, **enable** `push notifications`, **and help develop** `offline capabilities for` `web applications`.

---
</details>
<!-- end of 'service workers' section -->



The `Fetch API is` `widely supported` **across modern browsers**, **making it a** `robust` **choice** `for performing` `HTTP requests in` the `web development` world.