---
id: efivfk8zogc7lq7khfi50nv
title: 3 - Code Splitting
desc: ''
updated: 1730507236878
created: 1730506301625
---

In React, performance optimization is key, **especially for larger applications**. Code splitting is one effective method. It allows you `to break down` **your** `code into` `smaller chunks` `and load` **them** `only` `when needed`, `reducing` **the** `initial` `load time`. Here's how it works in React:

### 1. **Code Splitting with 'React.lazy' and 'Suspense'**

React’s **'React.lazy()' and 'Suspense' make it** `easy` `to code split at` **the** `component level`. By using these, you **can** `load components` `only when` **they’re** `needed`, rather than at the start.

#### Example:

**Suppose you have a component that’s not immediately needed, like a 'UserProfile'**.

```javascript
// Import necessary modules from React
import React, { Suspense } from 'react';

// Lazy load the UserProfile component
// This tells React to load the component only when it's rendered for the first time
const UserProfile = React.lazy(() => import('./UserProfile'));

// Define the main App component
function App() {
  return (
    <div>
      {/* Display a welcome message */}
      <h1>Welcome to the App</h1>

      {/* Use Suspense to wrap the lazy-loaded component */}
      {/* This will show the fallback content ("Loading...") while UserProfile is loading */}
      <Suspense fallback={<div>Loading...</div>}>
        {/* Render the lazy-loaded UserProfile component */}
        <UserProfile />
      </Suspense>
    </div>
  );
}

// Export the App component as the default export
export default App;
```

Here’s how it works:

- **'React.lazy()'**: This `function` `takes` `a function` `that dynamically imports` `the component`, **splitting it** into a separate chunk.
- **'Suspense'**: `Wraps around` **the** `lazy-loaded component`, `showing` `a fallback UI` (**like "Loading..."**) `while` **the** `component loads`.

### 2. **Route-Based Code Splitting with React Router**

In applications using React Router, you can `split code at` **the** `route level` `to load only` **the** `required components` **for each route**. This is **ideal** `for multi-page` `apps`.

#### Example:

```javascript
// Import necessary modules from React and React Router
import React, { Suspense } from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';

// Lazy load the Home and About components
const Home = React.lazy(() => import('./Home'));
const About = React.lazy(() => import('./About'));

// Define the main App component
function App() {
  return (
    // Set up React Router for navigation
    <Router>
      {/* Wrap Routes in Suspense to show fallback UI while components load */}
      <Suspense fallback={<div>Loading...</div>}>
        <Routes>
          {/* Define the routes for Home and About components */}
          <Route path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
        </Routes>
      </Suspense>
    </Router>
  );
}

// Export the App component as the default export
export default App;
```

**In this setup**:

- **Only the components needed for each route are loaded initially**.
- **Additional components load as users navigate to different routes**, **reducing the initial bundle size**.

### 3. **Using Webpack for Advanced Code Splitting**

Webpack, which is `commonly used` **with React**, **can handle** `more advanced` **forms of** `code splitting`, **such as** `creating` `separate bundles` `for different sections of` **the** `app or` **even** `for libraries`.

`By incorporating` `code splitting`, **you’ll be able to** `make` **your** `app` `more efficient`, `improving` `load times` **and** `user experience`. This technique is **especially** `valuable` `in large applications`, `helping` **you** `scale` `React performance as` **your** `app grows`.