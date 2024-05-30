---
id: 7xki5ha3nyu1fubyruafjbv
title: 2 - MySQL
desc: ''
updated: 1717078817326
created: 1717076639849
---

`To integrate` **a** `MySQL database` **with a JavaScript application**, **you typically** `use` `Node.js` **along** `with` **a** `MySQL library`. Below are the steps to set up and integrate a MySQL database with a Node.js application:

### 1. Set Up Your MySQL Database
First, make sure you `have` `MySQL` `installed and running`. `Create` **a** `database and` **a** `table` to interact with. Here's a quick example:

```sql
-- SQL
-- Create a new database named 'mydatabase'
CREATE DATABASE mydatabase;

-- Select the 'mydatabase' to perform operations on it
USE mydatabase;

-- Create a new table named 'users'
CREATE TABLE users (
  -- Define an 'id' column as the primary key, with auto-increment
  id INT AUTO_INCREMENT PRIMARY KEY,
  
  -- Define a 'name' column to store user names, cannot be NULL
  name VARCHAR(255) NOT NULL,
  
  -- Define an 'email' column to store user emails, cannot be NULL and must be unique
  email VARCHAR(255) NOT NULL UNIQUE
);
```

### 2. Set Up Your Node.js Project
`Initialize` **a new** `Node.js project` `and install` **the required** `dependencies`.

```bash
# Bash
# Create a new directory for the Node.js project
mkdir mynodeproject

# Change the current directory'
cd mynodeproject

# Initialize a new Node.js project with default settings
npm init -y

# Install the 'mysql' library, which allows Node.js to interact with MySQL databases
npm install mysql
```

### 3. Create a MySQL Connection
`Create` **a** `file named` `db.js` `to handle` **the** `MySQL connection`.

```javascript
// JavaScript
// Import the 'mysql' module to interact with the MySQL database
const mysql = require('mysql');

// Create a connection to the MySQL database with the specified configuration
const connection = mysql.createConnection({
  host: 'localhost',      // The hostname of the database server
  user: 'yourusername',   // Your MySQL username
  password: 'yourpassword', // Your MySQL password
  database: 'mydatabase'  // The name of the database to connect to
});

// Establish the connection to the database
connection.connect((err) => {
  if (err) {
    // If an error occurs, log it to the console and terminate the connection attempt
    console.error('Error connecting to the database:', err.stack);
    return;
  }
  // If the connection is successful, log a success message with the connection ID
  console.log('Connected to the database as id ' + connection.threadId);
});

// Export the connection object for use in other parts of the application
module.exports = connection;
```

### 4. Create a Simple Server
`Create` **a** `file named` `server.js` `to set up` **a basic** `Express server` `and handle requests`.

```bash
# Bash
# Install the 'express' library, a web framework for Node.js
npm install express
```

```javascript
// JavaScript
// Import the Express module
const express = require('express');
// Create an instance of an Express application
const app = express();
// Define the port on which the server will listen
const port = 3000;
// Import the database connection module
const db = require('./db');

// Middleware to parse JSON bodies in incoming requests
app.use(express.json());

// Route to get all users from the database
app.get('/users', (req, res) => {
  // Execute a SQL query to select all users
  db.query('SELECT * FROM users', (err, results) => {
    if (err) {
      // If there's an error, send a 500 status code and the error message
      res.status(500).send(err);
    } else {
      // If successful, send the results as a JSON response
      res.json(results);
    }
  });
});

// Route to add a new user to the database
app.post('/users', (req, res) => {
  // Destructure the name and email from the request body
  const { name, email } = req.body;

  // Execute a SQL query to insert a new user
  db.query('INSERT INTO users (name, email) VALUES (?, ?)', [name, email], (err, results) => {
    if (err) {
      // If there's an error, send a 500 status code and the error message
      res.status(500).send(err);
    } else {
      // If successful, send the inserted user's details as a JSON response
      res.json({ id: results.insertId, name, email });
    }
  });
});

// Start the server and listen on the defined port
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}/`);
});
```

### 5. Run Your Application
`Start` **your** `Node.js` `server`:

```bash
# Bash
# Run the Node.js server by executing the 'server.js' file
node server.js
```

**Your** `application` **should now be** `running on` `http://localhost:3000`. **You can** `test` **the** `endpoints` `using` **a** `tool` **like** `Postman` **or** `cURL`:

- **Get all users:**

  ```bash
  # Send a GET request to the '/users' endpoint on the local server 
  curl http://localhost:3000/users
  ```

- **Add a new user:**

    ```bash
    # Send a POST request to the '/users' endpoint on the local server
    curl -X POST -H "Content-Type: application/json" -d '{"name": "John Doe", "email": "john.doe@example.com"}' http://localhost:3000/users
    # -X POST: Specifies the request method as POST
    # -H "Content-Type: application/json": Sets the Content-Type header to 'application/json' indicating that the request body contains JSON data
    # -d '{"name": "John Doe", "email": "john.doe@example.com"}': Sends the specified JSON data as the request body
    ```

This setup provides **a basic example of how to integrate a MySQL database with a Node.js application**. You can `expand` **this** `by adding` `more routes`, `error handling`, `and using` `environment variables for` `sensitive information` **like** `database credentials`.