---
id: c83d8hp0677ltqv2qn14nfv
title: 2 - Cross-Origin Resource Sharing (CORS)
desc: ''
updated: 1716127146754
created: 1716120770678
---

Cross-Origin Resource Sharing (CORS) is a `security feature` implemented **in web browsers** `to prevent` `malicious websites` `from making` `unauthorized requests to` `resources on` **a** `different domain`. **CORS is** `controlled through` `HTTP headers` `that specify` `which origins` `are permitted` `to access` `resources on` **the** `server` `and which` `HTTP methods` `are allowed`.



<!-- start of 'permitted' section -->
<details>
    <summary>Definition: permitted</summary>

#
"Permitted" **means** `something` `that is` `allowed` `or authorized`.

---
</details>
<!-- end of 'permitted' section -->



<!-- start of 'authorized' section -->
<details>
    <summary>Definition: authorized</summary>

#
"Authorized" **means** `having` `official` `permission or approval` `to do` `something`. **It indicates that someone has been given the** `power or right` `to carry out` **a specific** `action`.

---
</details>
<!-- end of 'authorized' section -->



### Understanding CORS

**When a** `web page` `makes` **a** `request to` **a** `different domain` (**e.g.**, a request **from** `https://example.com` **to** `https://api.anotherdomain.com`), **the** `browser` `checks` **the** `response headers` `to determine if` **the** `request is` `allowed`. `CORS` **is** `used to` `manage` **these** `cross-origin` `requests`.

### Key Concepts

1. **Simple Requests**: These are `basic` `HTTP requests` `that meet` `certain criteria`, such as using `standard methods` **like** `GET`, `POST`, or `HEAD`, `and having` `safe headers` (**e.g.**, `Accept`, `Content-Type`).

2. **Preflight Requests**: For more `complex requests`, the `browser sends` **an HTTP** `OPTIONS` `request to` **the** `server` `to determine if` **the actual** `request is` `safe to` `send`. This is called a preflight request. The `server` `responds with` `headers` **indicating whether the actual request is allowed**.

3. **CORS Headers**:
    - **Access-Control-Allow-Origin**: `Specifies which` `origins can` `access` **the** `resource`. A wildcard (`*`) `allows access` `from any` `origin`.
    - **Access-Control-Allow-Methods**: `Lists` **the** `HTTP methods` `that are` `permitted when` `accessing` **the** `resource`.
    - **Access-Control-Allow-Headers**: `Specifies which` `headers` **can be** `used in` **the actual** `request`.
    - **Access-Control-Allow-Credentials**: `Indicates` `whether or not` **the** `response to` **the** `request` `can be` `exposed when` **the** `credentials flag is` `true` (**e.g.**, `cookies`, `HTTP authentication`).
    - **Access-Control-Max-Age**: `Indicates` `how long` **the** `results of` **a** `preflight request` **can be** `cached`.



<!-- start of 'cookies' section -->
<details>
    <summary>Definition: cookies</summary>

#
Cookies **are** `small pieces of` `data` `stored on` **a** `user's device` `by` **a** `website` **they visit**. They **serve various purposes like** `remembering` `user preferences`, `enabling` `login sessions`, **and** `tracking` `user activity for` `analytics or advertising`.

---
</details>
<!-- end of 'cookies' section -->



### Example Configuration

Here's an example of `how to` `configure` **a** `server to` `handle` `CORS`:

#### Using Express.js (Node.js)

```javascript
// Import the Express module
const express = require('express');
// Import the CORS module
const cors = require('cors');
// Create an instance of an Express application
const app = express();


// Enable CORS for all origins and HTTP methods by default
app.use(cors());

// Define advanced CORS options for more specific control
const corsOptions = {
  origin: 'https://example.com', // Specify the allowed origin
  methods: 'GET,POST,PUT,DELETE', // Specify the allowed HTTP methods
  allowedHeaders: 'Content-Type,Authorization', // Specify the allowed headers in requests
  credentials: true, // Allow sending credentials such as cookies
  optionsSuccessStatus: 204 // Set the response status code for successful OPTIONS preflight requests
};

// Apply the advanced CORS configuration with the defined options
app.use(cors(corsOptions));

// Define a route handler for the /data endpoint
app.get('/data', (req, res) => {
  // Respond with a JSON object
  res.json({ message: 'This is CORS-enabled for a specific origin.' });
});

// Start the server on port 3000 and log a message to the console when it starts
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

### Security Considerations

1. **Least Privilege Principle**: `Only allow` **the** `minimum necessary` `access` `by specifying` **the** `exact origins`, `methods`, **and** `headers` **required**.
2. **Credentials**: `Be cautious` when allowing credentials. **If** `Access-Control-Allow-Credentials` **is** `set to` `true`, **you** `cannot use` **a** `wildcard` (`*`) `for` `Access-Control-Allow-Origin`.
3. **Preflight Caching**: `Use` `Access-Control-Max-Age` `to reduce` **the** `number of` `preflight requests`, `improving performance`.

### Troubleshooting CORS Issues

1. **Check Headers**: `Ensure` **the** `server response` `includes` **the** `correct` **CORS** `headers`.
2. **Preflight Requests**: `Verify` **that** `preflight requests are` `correctly handled on` **the** `server`.
3. **Browser Console**: `Look at` the `browser console for` **CORS-related** `errors`, **which** `often provide` `clues` **about what went wrong**.

By properly configuring CORS, you can `enable` `secure and controlled` `cross-origin requests in` **your** `web applications`, `enhancing` **both** `security` `and user experience`.