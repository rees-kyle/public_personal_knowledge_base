---
id: v31v6mc5imq4laxbnasw87d
title: 1 - Node.js
desc: ''
updated: 1716566598711
created: 1716476911267
---

Node.js **is a powerful** `runtime` `environment` **that allows you** `to run` `JavaScript on` **the** `server side`. **Built on** `Chrome's V8` `JavaScript engine`, Node.js is **known** `for` **its** `non-blocking`, `event-driven architecture`, making it **ideal** `for building` `scalable and efficient` `network applications`.

## Key Features
1. **Asynchronous and Event-Driven:** `All APIs of` `Node.js` **are** `asynchronous`, **meaning** `non-blocking`. It essentially **means a** `Node`.js-based `server` `never waits for` **an** `API` `to return` `data`. The `server moves to` **the** `next API` `after calling it`, and a `notification mechanism of` `Events` **of Node.js helps the server get a response from the previous API call**.
2. **Very Fast:** Being built on **Google Chrome's V8 JavaScript Engine**, **Node.js library is very fast** `in code execution`.
3. **Single-Threaded but Highly Scalable:** Node.js uses a `single-threaded model with` `event looping`. The event mechanism helps the server to respond in a non-blocking way, making it `highly scalable`, `as opposed to` `traditional servers` **which create** `limited threads` `to handle requests`. **Node.js uses a** `single-threaded program` and the same program **can** `provide service to` **a** `much larger number of` `requests` than traditional servers like Apache HTTP Server.
4. **No Buffering:** Node.js applications never buffer any data. These `applications` simply `output` **the** `data in` `chunks`.

## Setting Up Node.js
1. **Installation:**
   - `Download` the `Node.js installer from` the [official Node.js website](https://nodejs.org/).
   - `Run` the `installer`, which **also installs the Node Package Manager (npm)**.
   - Verify the installation by running:
     ```sh
     node -v
     npm -v
     ```

2. **Creating a Simple Server:**
   - `Create` **a** `file` **named** `server.js`.
   - **Add the following code to server.js**:

     ```javascript
     // Import the http module
     const http = require('http');

     // Define the hostname and port number
     const hostname = '127.0.0.1';
     const port = 3000;

     // Create the HTTP server
     const server = http.createServer((req, res) => {
       // Set the response status code to 200 (OK)
       res.statusCode = 200;
  
       // Set the Content-Type header to plain text
       res.setHeader('Content-Type', 'text/plain');
  
       // End the response with the message 'Hello World'
       res.end('Hello World\n');
     });

     // Make the server listen on the specified hostname and port
     server.listen(port, hostname, () => {
       // Log a message to the console indicating the server is running
       console.log(`Server running at http://${hostname}:${port}/`);
     });
     ```

   - Run the server using:
     ```sh
     # Run in shell (terminal)
     node server.js
     ```

   - `Open` **your** `browser` **and** `go to` `http://127.0.0.1:3000/` **to see the "Hello World" message**.

## Using Express.js
Express.js **is a** `minimal and flexible` `Node.js` `web application framework` **that provides** `robust features for` `web and mobile` `applications`.

1. **Installation:**
   - `Initialize` **your** `project`:
     ```sh
     # Shell
     npm init -y
     ```
   - `Install` `Express`:
     ```sh
     # Shell
     npm install express
     ```

2. **Creating an Express Server:**
   - `Create` a `file` **named** `app.js`.
   - **Add the following code to app.js**:

     ```javascript
     // Import the express module
     const express = require('express');
     // Create an instance of the express application
     const app = express();
     // Define the port number the server will listen on
     const port = 3000;

     // Define a route handler for the root URL ('/') that sends a response
     app.get('/', (req, res) => {
       // Send a response with the text 'Hello World from Express!'
       res.send('Hello World from Express!');
     });

     // Make the server listen on the specified port
     app.listen(port, () => {
       // Log a message to the console indicating the server is running
       console.log(`Server running at http://localhost:${port}/`);
     });
     ```

   - Run the server using:
     ```sh
     # shell
     node app.js
     ```

   - `Open` your `browser` **and** `go to` `http://localhost:3000/` **to see the "Hello World from Express!" message**.

## Key Modules
1. **http:** Used `to create` `HTTP server` `and client`.
2. **fs:** Used `to handle` `file system` `operations`.
3. **path:** Used `to handle` `and transform` `file paths`.
4. **url:** Used `to parse` `URL strings`.
5. **os:** `Provides` `operating system-related` `utility methods` `and properties`.

## Example of Reading a File
Here's an example of reading a file `using` **the** `fs` `module`:

```javascript
// Import the fs (file system) module
const fs = require('fs');

// Read the contents of 'example.txt' with UTF-8 encoding
fs.readFile('example.txt', 'utf8', (err, data) => {
  // If an error occurs, log the error and return
  if (err) {
    console.error(err);
    return;
  }
  // If no error occurs, log the content of the file to the console
  console.log(data);
});
```

`Node.js` **allows you** `to run` `JavaScript on` **the** `server side`, **providing a** `non-blocking`, `event-driven architecture` that is `perfect for` `building` `scalable` `network applications`. Using **frameworks like** `Express.js` **can** `simplify development` `and enhance` **the** `capabilities of` **your** `applications`. By leveraging Node.js and its powerful modules, you can `efficiently handle` `server-side tasks` `and create` `dynamic` `web applications`.