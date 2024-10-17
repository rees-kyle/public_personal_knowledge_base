---
id: cjb496fv00la8awcfqh8ave
title: 1 - React Router
desc: ''
updated: 1729165159596
created: 1729162327379
---

To set up routing in a React project, you'll use React Router, **a popular** `library` `for managing navigation` `between different views`. Here's a breakdown of how to implement the `different` `routing functionalities`:

### 1. **Install React Router**
First, install `react-router-dom` in your React project:
```bash
# Bash
npm install react-router-dom
```

### 2. **Setting up Basic Routes**
You can set up routes to different components like this:

#### App.js:
```jsx
import React from "react";
import { BrowserRouter as Router, Route, Routes } from "react-router-dom"; // Import necessary modules from react-router-dom
import Home from "./components/Home"; // Import Home component
import About from "./components/About"; // Import About component

function App() {
  return (
    <Router> {/* Wrap the app with Router to enable routing */}
      <Routes> {/* Define the routes for different components */}
        <Route path="/" element={<Home />} /> {/* Route for the Home component, accessible at "/" */}
        <Route path="/about" element={<About />} /> {/* Route for the About component, accessible at "/about" */}
      </Routes>
    </Router>
  );
}

export default App; // Export the App component as the default export
```
- The **path** prop `defines` the `URL` path.
- The **element** prop is the `component` `to render when` **the** `path matches`.

### 3. **Nested Routes**
You can **nest routes inside another route**. **For example**, suppose you want to have **a user dashboard with subpages**:

#### Dashboard.js:
```jsx
import { Outlet, Link } from "react-router-dom"; // Import Outlet and Link components from react-router-dom

function Dashboard() {
  return (
    <div>
      <h1>Dashboard</h1>
      <nav>
        {/* Links to nested routes */}
        <Link to="profile">Profile</Link> {/* Link to the Profile page */}
        <Link to="settings">Settings</Link> {/* Link to the Settings page */}
      </nav>
      <Outlet /> {/* Renders the nested route component based on the current route */}
    </div>
  );
}

export default Dashboard; // Export the Dashboard component as the default export
```

#### App.js:
```jsx
import Dashboard from "./components/Dashboard"; // Import the Dashboard component
import Profile from "./components/Profile"; // Import the Profile component
import Settings from "./components/Settings"; // Import the Settings component

function App() {
  return (
    <Router> {/* Wrap the application with the Router component to enable routing */}
      <Routes> {/* Define all routes within the Routes component */}
        <Route path="/" element={<Home />} /> {/* Route for the Home component at the root path "/" */}
        <Route path="/about" element={<About />} /> {/* Route for the About component at "/about" */}
        
        {/* Nested routes under the Dashboard */}
        <Route path="/dashboard" element={<Dashboard />}> {/* Dashboard route at "/dashboard" */}
          <Route path="profile" element={<Profile />} /> {/* Nested route for Profile inside Dashboard at "/dashboard/profile" */}
          <Route path="settings" element={<Settings />} /> {/* Nested route for Settings inside Dashboard at "/dashboard/settings" */}
        </Route>
      </Routes>
    </Router>
  );
}

export default App; // Export the App component as the default export
```
- `Outlet` **is** `used in` **the** `parent route` '**Dashboard.js**' `to render` `child routes` ('**Profile.js**, '**Settings.js**').
- The `child routes` **are** `nested inside` '**/dashboard**'` with their respective paths.

### 4. **Dynamic Routing**
Dynamic routing **allows you** `to pass` `parameters` `via` **the** `URL`. **For example**, if you want **a user profile page that varies by user ID**:

#### UserProfile.js:
```jsx
import { useParams } from "react-router-dom"; // Import useParams hook to access route parameters

function UserProfile() {
  const { id } = useParams(); // Extract the "id" parameter from the URL

  return <h1>User Profile: {id}</h1>; // Display the user profile with the dynamic id
}

export default UserProfile; // Export the UserProfile component as the default export
```

#### App.js:
```jsx
import UserProfile from "./components/UserProfile"; // Import the UserProfile component

function App() {
  return (
    <Router> {/* Wrap the application with the Router component for routing */}
      <Routes> {/* Define all routes within the Routes component */}
        <Route path="/" element={<Home />} /> {/* Route for the Home component at the root path "/" */}
        <Route path="/about" element={<About />} /> {/* Route for the About component at "/about" */}
        
        {/* Nested routes inside the Dashboard component */}
        <Route path="/dashboard/*" element={<Dashboard />}> {/* Parent route for Dashboard with nested routes */}
          <Route path="profile" element={<Profile />} /> {/* Child route for Profile at "/dashboard/profile" */}
          <Route path="settings" element={<Settings />} /> {/* Child route for Settings at "/dashboard/settings" */}
        </Route>

        {/* Dynamic route for user profiles */}
        <Route path="/user/:id" element={<UserProfile />} /> {/* Route for UserProfile with dynamic "id" parameter */}
      </Routes>
    </Router>
  );
}

export default App; // Export the App component as the default export
```
- The '`:id`' in the route 'path="/user/:id"' **is a** `dynamic parameter`.
- **You can** `access it` inside the component **with** '`useParams`'.

### Additional Features:
- **Navigation**: Use `Link` `for internal navigation` (**like an anchor tag**).
- **Redirects**: You can use '`<Navigate>`' `to redirect users`.
- **Protected Routes**: Create routes that **are** `accessible only` `to certain users` `by wrapping them in` `a custom component`.

These are the **basics** to get you started with React Router.