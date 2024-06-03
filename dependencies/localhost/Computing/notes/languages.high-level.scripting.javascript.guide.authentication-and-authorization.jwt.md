---
id: l8boapkjhe0z3oi89m7ly1n
title: 1 - JSON Web Tokens (JWT)
desc: ''
updated: 1717435621190
created: 1717428245135
---

JSON Web Tokens (JWT) are a **popular method** `for securely` `transmitting information` `between parties` `as` **a** `JSON object`. **This information** `can be` `verified and trusted` `because` **it is** `digitally signed`. **JWTs can be signed** `using` **a** `secret` (`with` **the** `HMAC algorithm`) `or` **a** `public/private` `key pair` `using` `RSA` **or** `ECDSA`.

> HMAC: Hash-based Message Authentication Code



<!-- start of 'hash-based message authentication code' section -->
<details>
    <summary>Definition: hash-based message authentication code</summary>

#
HMAC (Hash-based Message Authentication Code) **is a** `method` **used** `to verify` **the** `integrity and authenticity of` **a** `message`. It `combines` **a** `cryptographic hash function` (**like SHA-256**) `with` **a** `secret key`. The `result is` **a** `fixed-size` `string of` `characters` `that acts as` **a** `signature for` **the** `message`. `If` **the** `message or` **the** `key` `changes`, **the** `HMAC` `will change`, `allowing verification that` **the** `message` `has not been` `altered` `and confirming` **the** `identity of` **the** `sender`.

---
</details>
<!-- end of 'hash-based message authentication code' section -->



<!-- start of 'cryptographic' section -->
<details>
    <summary>Definition: cryptographic</summary>

#
Cryptographic **refers to** `techniques and methods` **used** `to secure information` `and communication` `through encoding` (**encryption**) **so that** `only those` `intended to` `receive` **the** `information` `can read` `and process it`. This `ensures` `data confidentiality`, `integrity`, `and authentication`.

---
</details>
<!-- end of 'cryptographic' section -->



> RSA: Rivest-Shamir-Adleman



<!-- start of 'rivest-shamir-adleman' section -->
<details>
    <summary>Definition: rivest-shamir-adleman</summary>

#
Rivest-Shamir-Adleman (RSA) **is a widely used** `cryptographic algorithm` `for secure` `data transmission`. It **uses a** `pair of keys`: **a** `public key` `for encrypting data` `and` **a** `private key` `for decrypting it`. This `allows` `secure communication`, **as** `only` **the** `intended recipient`, `who holds` **the** `private key`, `can decrypt` **the** `message` `encrypted with` **the** `public key`.

---
</details>
<!-- end of 'rivest-shamir-adleman' section -->



> ECDSA: Elliptic Curve Digital Signature Algorithm



<!-- start of 'elliptic curve digital signature algorithm' section -->
<details>
    <summary>Definition: elliptic curve digital signature algorithm</summary>

#
The Elliptic Curve Digital Signature Algorithm (ECDSA) **is a** `cryptographic` `method` **used** `to create` `digital signatures for` `verifying` **the** `authenticity and integrity of` `messages or documents`. It `uses` **the** `mathematics of` `elliptic curves` `to generate and verify` `signatures`, **offering** `strong` `security with` `shorter` `key lengths`, **making it** `efficient and fast`.

---
</details>
<!-- end of 'elliptic curve digital signature algorithm' section -->



<!-- start of 'elliptic curves' section -->
<details>
    <summary>Definition: elliptic curves</summary>

#
Elliptic curves **are** `mathematical curves` `defined by` **a specific** `type of` `equation`. They have a `unique` `shape and properties` **that make them** `useful in` `cryptography` `for creating` `secure algorithms`. In cryptography, elliptic curves are used `to generate keys` `for encrypting data` `and creating` `digital signatures`, **offering** `strong` `security with` `smaller` `key sizes`.

---
</details>
<!-- end of 'elliptic curves' section -->



### Structure of JWT

A JWT is **composed of** `three` `parts`:

1. **Header**: **Typically consists of** `two parts`: the `type of` `token` (**JWT**) `and` **the** `signing algorithm` (**e.g.**, **HMAC SHA256 or RSA**).

2. **Payload**: `Contains` **the** `claims`. **Claims are** `statements about` **an** `entity` (**typically**, **the user**) `and` `additional data`.

3. **Signature**: Used `to verify` **that the** `sender of` **the** `JWT is` `who it says it is` `and` `to ensure` **that the** `message` `wasn't changed` `along the way`.

These `parts` `are separated` `by dots` `and are` `base64-encoded` `strings`.



<!-- start of 'base64 encoding' section -->
<details>
    <summary>Definition: base64 encoding</summary>

#
Base64 encoding **is a** `method of` `converting` `binary data into` **a** `text string`. It `uses` `64` `different` `ASCII characters` (**letters**, **numbers**, **and symbols**) `to represent` **the** `data`. This encoding is commonly used `to safely` `transmit` `binary data` `over` `text-based protocols`, `like email` `or JSON`, `which only` `support text`.

---
</details>
<!-- end of 'base64 encoding' section -->



#### Example JWT

```markdown
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

### JWT Example in Node.js

Let's break down `how to` `create`, `sign`, `and verify` JWTs using Node.js.

#### 1. Install Required Packages

```bash
# Install required packages for JWT authentication
npm install express jsonwebtoken bcryptjs
```

#### 2. Setting Up Express Server

```js
const express = require('express');  // Import the Express framework
const jwt = require('jsonwebtoken');  // Import the JSON Web Token library
const bcrypt = require('bcryptjs');  // Import the bcrypt library for password hashing

const app = express();  // Create an instance of the Express application
const PORT = process.env.PORT || 3000;  // Set the port for the server to run on
const SECRET_KEY = 'your_jwt_secret';  // Secret key for JWT signing (should be stored securely)

app.use(express.json());  // Middleware to parse JSON requests

app.listen(PORT, () => {  // Start the server and listen on the specified port
    console.log(`Server is running on port ${PORT}`);
});
```

#### 3. User Registration Endpoint

```js
const users = []; // This should be a database in a real application

app.post('/register', async (req, res) => {
    const { username, password } = req.body; // Extract username and password from request body

    // Hash the password
    const hashedPassword = await bcrypt.hash(password, 10); // Hash the password using bcrypt with salt rounds

    // Save user to database (in this example, users are stored in-memory; in a real app, this would be a database operation)
    users.push({ username, password: hashedPassword });

    res.status(201).send('User registered'); // Send a success response
});
```

#### 4. User Login and JWT Generation

```js
app.post('/login', async (req, res) => {
    const { username, password } = req.body; // Extract username and password from request body

    // Find user in the database
    const user = users.find(u => u.username === username);
    if (!user) {
        return res.status(400).send('Invalid credentials'); // If user not found, send error response
    }

    // Check if password is correct
    const isPasswordValid = await bcrypt.compare(password, user.password); // Compare hashed password with input password
    if (!isPasswordValid) {
        return res.status(400).send('Invalid credentials'); // If password is incorrect, send error response
    }

    // Generate JWT
    const token = jwt.sign({ username }, SECRET_KEY, { expiresIn: '1h' }); // Sign JWT with username and secret key

    res.json({ token }); // Send JWT token as JSON response
});
```

#### 5. Middleware for Protected Routes

```js
const authenticateToken = (req, res, next) => {
    const authHeader = req.headers['authorization']; // Get the Authorization header from the request
    const token = authHeader && authHeader.split(' ')[1]; // Extract the token from the header

    if (!token) {
        return res.status(401).send('Access denied'); // If no token found, send unauthorized response
    }

    jwt.verify(token, SECRET_KEY, (err, user) => { // Verify the token using the secret key
        if (err) {
            return res.status(403).send('Invalid token'); // If token is invalid, send forbidden response
        }

        req.user = user; // Set the user object in the request for further processing
        next(); // Call the next middleware in the chain
    });
};
```

#### 6. Protected Route Example

```js
app.get('/protected', authenticateToken, (req, res) => {
    res.send('This is a protected route'); // If authentication is successful, send response for protected route
});
```

### Full Example Code

```js
const express = require('express');
const jwt = require('jsonwebtoken');
const bcrypt = require('bcryptjs');

const app = express();
const PORT = process.env.PORT || 3000;
const SECRET_KEY = 'your_jwt_secret'; // Should be an environment variable in a real application

app.use(express.json());

const users = [];

app.post('/register', async (req, res) => {
    const { username, password } = req.body;
    const hashedPassword = await bcrypt.hash(password, 10);
    users.push({ username, password: hashedPassword });
    res.status(201).send('User registered');
});

app.post('/login', async (req, res) => {
    const { username, password } = req.body;
    const user = users.find(u => u.username === username);
    if (!user) {
        return res.status(400).send('Invalid credentials');
    }
    const isPasswordValid = await bcrypt.compare(password, user.password);
    if (!isPasswordValid) {
        return res.status(400).send('Invalid credentials');
    }
    const token = jwt.sign({ username }, SECRET_KEY, { expiresIn: '1h' });
    res.json({ token });
});

const authenticateToken = (req, res, next) => {
    const authHeader = req.headers['authorization'];
    const token = authHeader && authHeader.split(' ')[1];
    if (!token) {
        return res.status(401).send('Access denied');
    }
    jwt.verify(token, SECRET_KEY, (err, user) => {
        if (err) {
            return res.status(403).send('Invalid token');
        }
        req.user = user;
        next();
    });
};

app.get('/protected', authenticateToken, (req, res) => {
    res.send('This is a protected route');
});

app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`);
});
```

This **example demonstrates how to set up basic authentication and authorization using JWT in a Node.js application with Express**. `For` **a** `production environment`, **remember to** `handle errors` `more gracefully`, `store secrets` `securely`, `and use` `a real database` `instead of` `an in-memory array` `for user data`.