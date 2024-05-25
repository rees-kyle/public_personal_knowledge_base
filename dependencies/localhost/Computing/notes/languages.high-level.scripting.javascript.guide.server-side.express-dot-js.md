---
id: mmqhnrdrluefrb6fn46f5ww
title: 2 - Express.js
desc: ''
updated: 1716643873095
created: 1716642630492
---

Express.js **is a popular** `framework for` `building` `web applications` `and APIs` `with Node.js on` **the** `server side`. Below is an overview and a basic example to get you started.

### Getting Started with Express.js

#### 1. Setup

First, make sure you have `Node.js` installed. You can `download it from` [nodejs.org](https://nodejs.org/). `Node.js includes` `npm` (**Node Package Manager**), **which you'll use to install Express**.

To `create` **a** `new project`, follow these steps:

```bash
# Create a new directory for your project
mkdir my-express-app
# Change into the new directory
cd my-express-app

# Initialize a new Node.js project with default settings
npm init -y
# The -y flag automatically answers 'yes' to all prompts, creating a package.json file with default values

# Install Express.js
npm install express
```

#### 2. Basic Express.js Server

`Create` **a** `file named` `app.js` `in` **your** `project directory`. **This will be the** `main file for` **your** `Express server`.

```javascript
// app.js

// Import the express module
const express = require('express');

// Create an instance of express
const app = express();

// Define a port to listen on
const PORT = process.env.PORT || 3000;
// using an environment variable if available, otherwise defaulting to 3000

// Define a simple route for the root URL
app.get('/', (req, res) => {
  res.send('Hello, World!'); // Send a response to the client
});

// Start the server and listen on the defined port
app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`); // Log that the server is running
});
```

#### 3. Running the Server

To `start` **your** `server`, `run` **the following** `command in` **your** `project directory`:

```bash
# Run the app.js file using Node.js to start the Express server
node app.js
```

**You should see the message** `'Server is running on port 3000' in` **your** `terminal`. `Open` **your web** `browser` `and navigate to` `http://localhost:3000`, **and you should see the message "Hello, World!"**.

### Adding More Functionality

`Express.js is` **highly** `flexible` **and allows you** `to add` `middleware`, `define more routes`, `handle errors`, **and much more**.

#### Routing

You can `define` `more routes for` `different endpoints`. For example:

```javascript
// Define another route for the '/about' URL
app.get('/about', (req, res) => {
  res.send('This is the about page.'); // Send a response to the client
});

// Define a route with a parameter in the URL
app.get('/user/:name', (req, res) => {
  const name = req.params.name; // Extract the parameter from the URL
  res.send(`Hello, ${name}!`); // Send a personalized response to the client
});
```

#### Middleware

`Middleware functions` **are** `functions that` `have access to` **the** `request object` (`req`), **the** `response object` (`res`), `and` **the** `next` `middleware function in` **the** `application’s` `request-response cycle`.

```javascript
// Middleware to log the request method and URL
app.use((req, res, next) => {
  console.log(`${req.method} request for '${req.url}'`); // Log the HTTP method and the requested URL
  next(); // Pass control to the next middleware function in the stack
});
```

#### Error Handling

You can handle errors `by defining` **an** `error-handling` `middleware function`.

```javascript
// Error handling middleware
app.use((err, req, res, next) => {
  console.error(err.stack); // Log the error stack trace to the console
  res.status(500).send('Something broke!'); // Send a 500 Internal Server Error response to the client
});
```

### Full Example

Here’s a full example **combining the concepts mentioned above**:

```javascript
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

// Middleware to log requests
app.use((req, res, next) => {
  console.log(`${req.method} request for '${req.url}'`);
  next();
});

// Simple route
app.get('/', (req, res) => {
  res.send('Hello, World!');
});

// Another route
app.get('/about', (req, res) => {
  res.send('This is the about page.');
});

// Route with a parameter
app.get('/user/:name', (req, res) => {
  const name = req.params.name;
  res.send(`Hello, ${name}!`);
});

// Error handling middleware
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});

// Start the server
app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});
```

This should give you a **good** `starting point for` `building` `web applications` `and APIs` `using Express.js`.