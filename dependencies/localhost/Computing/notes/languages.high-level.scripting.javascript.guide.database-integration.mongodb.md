---
id: kfx4iu0shdsdyb0v3zvldk5
title: 1 - MongoDB
desc: ''
updated: 1716825785430
created: 1716823919506
---

`Integrating MongoDB into` **a** `JavaScript application` **typically involves** `using` **a** `Node.js environment with` **the** `MongoDB Node.js driver or` **an** `Object Data Modeling (ODM) library` **like** `Mongoose`. Below is a step-by-step guide on **how to set up a basic integration using both methods**.

### Using the MongoDB Node.js Driver

1. **Install MongoDB Node.js Driver:**

   `First`, ensure you `have Node.js` `installed`. `Then`, `create` **a** `new project` `and install` **the** `MongoDB driver`:

    ```shell
    # Create a new directory for your project
    mkdir myproject

    # Change into the new directory
    cd myproject

    # Initialize a new Node.js project with default settings
    npm init -y

    # Install the MongoDB Node.js driver
    npm install mongodb
    ```

2. **Create a MongoDB Client:**

   `Create` a `JavaScript file` (**e.g., app.js**) `and set up` the `MongoDB client`:

    ```javascript
    // Import the MongoClient class from the mongodb package
    const { MongoClient } = require('mongodb');

    // Define an asynchronous main function to perform MongoDB operations
    async function main() {
        // MongoDB connection string (replace with your actual connection string)
        const uri = "your_mongodb_connection_string";

        // Create a new MongoClient instance with the connection string
        const client = new MongoClient(uri, { useNewUrlParser: true, useUnifiedTopology: true });

        try {
            // Connect to the MongoDB server
            await client.connect();
            console.log("Connected successfully to MongoDB");

            // Select the database and collection you want to use
            const database = client.db('testdb');
            const collection = database.collection('testcollection');

            // Insert a document into the collection
            const insertResult = await collection.insertOne({ name: "John", age: 30 });
            console.log('Inserted document:', insertResult);

            // Find a document in the collection
            const findResult = await collection.findOne({ name: "John" });
            console.log('Found document:', findResult);

        } finally {
            // Close the connection to the MongoDB server
            await client.close();
        }
    }

    // Run the main function and catch any errors that occur
    main().catch(console.error);
   ```

3. **Run the Application:**

    ```shell
    # Run the Node.js application (app.js)
    node app.js
    ```

### Using Mongoose ODM

1. **Install Mongoose:**

   ```shell
    # Install the Mongoose library for MongoDB object modeling
    npm install mongoose
   ```

2. **Create a Mongoose Model:**

   `Create` **a** `JavaScript file` (**e.g., app.js**) `and set up` `Mongoose`:

   ```javascript
    // Import the mongoose package
    const mongoose = require('mongoose');

    // Define an asynchronous main function to perform MongoDB operations using Mongoose
    async function main() {
        // Connect to the MongoDB server with the connection string (replace with your actual connection string)
        await mongoose.connect('your_mongodb_connection_string', { useNewUrlParser: true, useUnifiedTopology: true });
        console.log("Connected successfully to MongoDB");

        // Define a schema for the collection
        const userSchema = new mongoose.Schema({
            name: String,
            age: Number
        });

        // Create a model based on the schema
        const User = mongoose.model('User', userSchema);

        // Create a new document instance
        const user = new User({ name: "John", age: 30 });

        // Save the document to the database
        await user.save();
        console.log('Inserted document:', user);

        // Find a document in the collection
        const foundUser = await User.findOne({ name: "John" });
        console.log('Found document:', foundUser);

        // Close the connection to the MongoDB server
        await mongoose.connection.close();
    }

    // Run the main function and catch any errors that occur
    main().catch(console.error);
   ```

3. **Run the Application:**

    ```shell
    # Run the Node.js application
    node app.js
    ```

### Summary

- **MongoDB Node.js Driver:** Directly `interacts with` `MongoDB`, `providing` `flexibility and control`.
- **Mongoose:** An `ODM` **that** `provides` **a** `more structured` `and schema-based` `approach` `to interact with` `MongoDB`, `simplifying` `data modeling and validation`.

`Choose` the `method that` **best** `fits` **your** `project's needs`. `Mongoose` **is often preferred for its** `ease of use` **and** `powerful features`, **especially in applications** `where data relationships` `and schema validation` `are important`.