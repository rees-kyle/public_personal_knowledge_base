---
id: 7k22mb0lpja67c4xflmcc69
title: 2 - Oauth
desc: ''
updated: 1736667586893
created: 1718043374493
---

OAuth (`Open Authorization`) **is an** `open standard` `for access delegation` **commonly used as a way** `to grant` `websites or applications` `limited access to` `user information` `without exposing` `user passwords`. It `allows` `third-party services` `to exchange` `data on` **a** `user’s behalf with` **the** `user's consent`.



<!-- start of 'open standard' section -->
<details>
    <summary>Definition: open standard</summary>

#
An open standard **is a** `set of` `rules or guidelines` **that** `anyone` `can access and use` `for free`. **These standards help** `ensure` **that** `different` `systems and devices` **can** `work together` `easily`.

---
</details>
<!-- end of 'open standard' section -->



## Key Concepts

1. **Resource Owner**: The `user` **who** `authorizes` **an** `application` `to access` **their** `account`.
2. **Client**: The `application` **that wants** `to access` **the** `user's account`.
3. **Authorization Server**: The `server` **that** `issues` `access tokens to` **the** `client` `after authenticating` **the** `user`.
4. **Resource Server**: The `server` **that** `hosts` **the** `protected resources` (**APIs**) `and uses` `access tokens` **to grant access**.



<!-- start of 'client' section -->
<details>
    <summary>Definition: client (computer science)</summary>

#
A client **is a** `device or program` **that** `requests` `services or resources from` **a** `server in` **a** `network`. For example, **a web browser is a client that requests web pages from web servers**.

---
</details>
<!-- end of 'client' section -->



## OAuth 2.0 Flow

1. **Authorization Request**: The `client` `requests authorization from` **the** `resource owner`.
2. **Authorization Grant**: The `resource owner` `provides authorization` (e.g., **by logging in and consenting**).
3. **Access Token Request**: The `client` `requests` **an** `access token from` **the** `authorization server` `using` **the** `authorization grant`.
4. **Access Token Response**: The `authorization server` `issues` **an** `access token to` **the** `client`.
5. **Resource Request**: The `client` `uses` **the** `access token to` `request` **the** `protected resource`.
6. **Resource Response**: The `resource server` `serves` **the** `requested resource to` **the** `client`.

## OAuth 2.0 Grant Types

1. **Authorization Code Grant**: `Used by` `web and mobile` `apps`. The `client` `receives` **an** `authorization code` **which is then** `exchanged for` **an** `access token`.
2. **Implicit Grant**: `Used by` `single-page applications` (**SPAs**). The `access token is` `returned` **directly** `without` **an** `authorization code`.
3. **Resource Owner Password Credentials Grant**: The `user's credentials` (**username and password**) **are** `used` **directly** `to obtain` **an** `access token`. This is `less secure` and `should be` `avoided`.
4. **Client Credentials Grant**: `Used for` `server-to-server` `authentication`. The `client` `uses` **its** `own credentials` `to obtain` **an** `access token`.

## Example OAuth Flow (Authorization Code Grant)

1. **Authorization Request**: The `user` `clicks` "`Login with GitHub`" `on` **the** `client application`.
2. **User Authentication**: The `user` **is** `redirected to` `GitHub` `to authenticate`.
3. **Authorization Grant**: `GitHub asks` **the** `user to` `authorize` **the** `client application`.
4. **Redirect with Authorization Code**: **After the user authorizes**, `GitHub redirects` `back to` **the** `client application with` **an** `authorization code`.
5. **Access Token Request**: The `client application` `exchanges` **the** `authorization code for` **an** `access token`.
6. **Access Token Response**: `GitHub responds with` **an** `access token`.
7. **API Request**: The `client application` `uses` **the** `access token` `to request` `user data from` `GitHub's API`.
8. **API Response**: `GitHub returns` **the** `requested` `user data`.

## Step-by-Step Implementation

### 1. Set Up Project

1. `Initialize` your `project`:

    ```bash
    # Creates a new directory named "oauth-example"
    mkdir oauth-example
    # Changes the current working directory to "oauth-example"
    cd oauth-example
    # Initializes a new Node.js project in the current directory with default settings (-y flag skips the initialization prompts)
    npm init -y
    ```

2. `Install` **necessary** `packages`:

    ```bash
    # Installs required Node.js packages for the project
    npm install express axios dotenv
    ```

3. `Create` the **necessary** `files`:

    ```bash
    # Creates two new files: "index.js" and ".env"
    touch index.js .env
    ```

### 2. Configure OAuth Provider

For this **example**, we'll use **GitHub as** the **OAuth provider**. You'll need to:

1. `Register` your `application with` `GitHub`.
2. `Get` the `Client ID` **and** `Client Secret`.

`Add` **these** `credentials to` **your** '`.env`' `file`:

```markdown
GITHUB_CLIENT_ID=your_client_id
GITHUB_CLIENT_SECRET=your_client_secret
GITHUB_REDIRECT_URI=http://localhost:3000/auth/github/callback
```

### 3. Create the Express Server

`In` **your** `index.js` **file**, `set up` the `Express server`:

```js
const express = require('express'); // Import the Express library to create a web server
const axios = require('axios'); // Import the Axios library to make HTTP requests
const dotenv = require('dotenv'); // Import the Dotenv library to load environment variables

dotenv.config(); // Load environment variables from a .env file into process.env

const app = express(); // Initialize the Express application
const port = 3000; // Define the port number for the server to listen on

// Define the route for the homepage
app.get('/', (req, res) => {
    res.send('<a href="/auth/github">Login with GitHub</a>'); // Send an HTML link to the client to start the GitHub OAuth flow
});

// Define the route to redirect to GitHub for authentication
app.get('/auth/github', (req, res) => {
    const redirect_uri = process.env.GITHUB_REDIRECT_URI; // Get the redirect URI from environment variables
    const client_id = process.env.GITHUB_CLIENT_ID; // Get the client ID from environment variables

    // Redirect the client to GitHub's OAuth authorization page with the client ID and redirect URI
    res.redirect(`https://github.com/login/oauth/authorize?client_id=${client_id}&redirect_uri=${redirect_uri}`);
});

// Define the callback route for GitHub to redirect to after authorization
app.get('/auth/github/callback', async (req, res) => {
    const code = req.query.code; // Extract the authorization code from the query parameters
    const client_id = process.env.GITHUB_CLIENT_ID; // Get the client ID from environment variables
    const client_secret = process.env.GITHUB_CLIENT_SECRET; // Get the client secret from environment variables

    try {
        // Exchange the authorization code for an access token
        const response = await axios.post('https://github.com/login/oauth/access_token', {
            client_id, // Include the client ID in the request body
            client_secret, // Include the client secret in the request body
            code // Include the authorization code in the request body
        }, {
            headers: {
                accept: 'application/json' // Specify that the response should be in JSON format
            }
        });

        const access_token = response.data.access_token; // Extract the access token from the response data

        // Use the access token to request user information from GitHub
        const userResponse = await axios.get('https://api.github.com/user', {
            headers: {
                Authorization: `token ${access_token}` // Include the access token in the Authorization header
            }
        });

        res.send(userResponse.data); // Send the user information as the response
    } catch (error) {
        res.status(500).send('Error authenticating'); // Handle any errors by sending a 500 status code and an error message
    }
});

// Start the server on the specified port and log a message indicating the server is running
app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`); // Log the server URL
});
```

### 4. Run Application

1. `Start` your `server`.

    ```bash
    # Executes the Node.js script named "index.js"
    node index.js
    ```

2. `Navigate to` your `application`:

`Open` your `browser` **and** `go to` '`http://localhost:3000`'. `Click on` "`Login with GitHub`", **and you'll be redirected to GitHub for authentication**. **After authenticating**, **GitHub will redirect you back to your application**, **and you will see your GitHub user data**.

## Securing Application 

While the above example demonstrates the basic OAuth flow, **you should take additional steps to secure your application**:

- `Validate and sanitize` `all` `inputs`.
- `Use HTTPS` `to protect` `data in` `transit`.
- `Store` `sensitive information` (like **access tokens**) `securely`.

## Further Enhancements

- `Handle` `refresh tokens` `to keep` **the** `user` `logged in`.
- `Implement` **a** `logout` `functionality`.
- `Integrate with` `other` `OAuth providers` `if needed`.

**This example shows the basic steps to implement OAuth using GitHub as the provider**. **The process involves setting up an Express server**, **creating routes for authentication**, **handling callbacks**, **and making API requests with the obtained access token**.