---
id: eql4xjd0h5y5xpwsjw0zdyd
title: 3 - RESTful APIs
desc: ''
updated: 1716732908900
created: 1716729910532
---

A `RESTful API` (`Representational State Transfer`) **is an** `architectural style for` `designing` `networked applications`. It **relies on a** `stateless`, `client-server`, `cacheable communications protocol` **-- the** `HTTP`. RESTful APIs are `designed around` **the** `concept of` `resources`, **which can be** `any type of` `object`, `data`, `or service` **that can be accessed by clients**.

To create a server-side application using JavaScript that exposes RESTful APIs, you typically `use` `Node.js` along `with` **a** `framework` **like** `Express`. Below is a step-by-step guide to setting up a basic RESTful API with Node.js and Express.

### Step 1: Set Up Your Project

1. **Initialize your project:**
   `Open` **your** `terminal` `and create` **a** `new directory` **for your project**, then `navigate into it` `and initialize` **a new** `Node.js project`.
   ```shell
    # Create a new directory for your project
    mkdir my-api

    # Navigate into the newly created project directory
    cd my-api

    # Initialize a new Node.js project with default settings
    npm init -y
    ```

2. **Install dependencies:**
   `Install Express` `and` **any other necessary** `middleware`.
   ```shell
    # Install the Express framework, which will help in creating the server and handling routes
    npm install express
   ```

### Step 2: Create the Server

1. **Create the entry point file:**
   `Create` **a** `file named` `index.js` `in` **the** `root directory of` **your** `project`.

2. **Set up the basic server:**
   `Open` `index.js` `and add` **the** `following code` **to set up a basic Express server**.
    ```js
    // Import the Express module
    const express = require('express');

    // Create an instance of an Express application
    const app = express();

    // Define the port on which the server will listen
    const port = 3000;

    // Middleware to parse JSON bodies of incoming requests
    app.use(express.json());

    // Define a route for the root URL that sends a "Hello World!" message
    app.get('/', (req, res) => {
    res.send('Hello World!');
    });

    // Start the server and have it listen on the specified port
    app.listen(port, () => {
        console.log(`Server is running on http://localhost:${port}`);
    });
    ```

### Step 3: Define RESTful Routes

1. **Create a folder for routes:**
   `Create` **a** `routes folder and` **a** `file named` `api.js` `inside` **it**.

2. **Define your API routes:**
   `Open` `routes/api.js` `and define` **your** `RESTful routes`. **For example**, **a simple** `CRUD interface for` `managing users`:
    ```js
    // Import the Express module
    const express = require('express');

    // Create a new router object
    const router = express.Router();

    // In-memory array to store users
    let users = [
        { id: 1, name: 'John Doe' },
        { id: 2, name: 'Jane Doe' }
    ];

    // Route to get all users
    router.get('/users', (req, res) => {
        res.json(users);
    });

    // Route to get a single user by ID
    router.get('/users/:id', (req, res) => {
        // Find the user with the given ID
        const user = users.find(u => u.id === parseInt(req.params.id));
        // If user is not found, send a 404 response
        if (!user) return res.status(404).send('User not found');
        // If user is found, return the user data
        res.json(user);
    });

    // Route to create a new user
    router.post('/users', (req, res) => {
        // Create a new user object with the next available ID
        const newUser = {
            id: users.length + 1,
            name: req.body.name
        };
        // Add the new user to the users array
        users.push(newUser);
        // Send a 201 status code and the new user data
        res.status(201).json(newUser);
    });

    // Route to update an existing user
    router.put('/users/:id', (req, res) => {
        // Find the user with the given ID
        const user = users.find(u => u.id === parseInt(req.params.id));
        // If user is not found, send a 404 response
        if (!user) return res.status(404).send('User not found');
        // Update the user's name
        user.name = req.body.name;
        // Return the updated user data
        res.json(user);
    });

    // Route to delete a user
    router.delete('/users/:id', (req, res) => {
        // Find the index of the user with the given ID
        const userIndex = users.findIndex(u => u.id === parseInt(req.params.id));
        // If user is not found, send a 404 response
        if (userIndex === -1) return res.status(404).send('User not found');
        // Remove the user from the users array
        const deletedUser = users.splice(userIndex, 1);
        // Return the deleted user data
        res.json(deletedUser);
    });

    // Export the router object so it can be used in other files
    module.exports = router;
    ```

3. **Use the routes in your main server file:**
   `Update` `index.js` `to use` the `routes defined in` `routes/api.js`.
    ```js
    // Import the Express module
    const express = require('express');

    // Create an instance of an Express application
    const app = express();

    // Define the port on which the server will listen
    const port = 3000;

    // * Import the API routes from the 'routes/api.js' file *
    const apiRoutes = require('./routes/api');

    // Middleware to parse JSON bodies of incoming requests
    app.use(express.json());

    // * Use the imported API routes for any requests starting with '/api' *
    app.use('/api', apiRoutes);

    // Define a route for the root URL that sends a "Hello World!" message
    app.get('/', (req, res) => {
        res.send('Hello World!');
    });

    // Start the server and have it listen on the specified port
    app.listen(port, () => {
        console.log(`Server is running on http://localhost:${port}`);
    });
    ```

### Step 4: Test Your API

`Start` your `server`:
```shell
# Start the Node.js server using the 'index.js' file as the entry point
node index.js
```

Your `API` **will be** `running at` `http://localhost:3000`. You can `use` `tools` **like** `Postman or curl` `to test` **the** `endpoints`.

- **GET /api/users** - `Retrieves` `all users`.
- **GET /api/users/:id** - `Retrieves` a `user` `by ID`.
- **POST /api/users** - `Creates` **a** `new user`.
- **PUT /api/users/:id** - `Updates` a `user` `by ID`.
- **DELETE /api/users/:id** - `Deletes` a `user` `by ID`.

This is a **basic example of setting up a RESTful API with Node.js and Express**. You can `expand it by` `adding` **more** `features`, `integrating` **with a** `database`, `adding authentication`, **and more**.