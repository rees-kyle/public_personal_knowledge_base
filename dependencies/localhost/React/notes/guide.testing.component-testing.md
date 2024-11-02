---
id: kkwg71v77hxkwqzwsmcom40
title: 2 - Component Testing
desc: ''
updated: 1730511530852
created: 1730510359069
---

When it comes to component testing **with** `React Testing Library` (`RTL`), here are **some essentials and steps to get started**:

### 1. **Setup**

   If you haven’t installed it yet, `add` `'React Testing Library' to` your `project`:
   ```bash
   # BASH
   npm install @testing-library/react
   ```

### 2. **Basic Concepts**

   - **Render**: `Use` the `'render' function` **from RTL** `to display` **your** `component in` **a** `virtual DOM`. This **allows you** `to interact with` `and test it`.
   - **Queries**: RTL **provides** `various queries` (**like** `'getByText'`, `'getByRole'`, `'getByTestId'`, **etc.**) `to select` `and interact with` `elements within` **the** `rendered component`.
   - **User Events**: You **can** `simulate` `user interactions` `using 'userEvent'`, **like** `clicking`, `typing`, **etc.**

### 3. **Writing a Simple Test**

   Here's a **basic test example for a button component**:

   ```jsx
    // MyButton.js
    // Import React to use JSX and component functionalities
    import React from 'react';

    // Define the MyButton component
    // - Accepts two props: `onClick` (function) and `label` (string)
    // - Renders a button with the label as its text and calls `onClick` when clicked
    const MyButton = ({ onClick, label }) => (
    <button onClick={onClick}>{label}</button>
    );

    // Export the component so it can be used in other files
    export default MyButton;
   ```

   ```jsx
    // MyButton.test.js
    // Import necessary functions and components from React Testing Library
    import { render, screen } from '@testing-library/react';
    import userEvent from '@testing-library/user-event'; // For simulating user events
    import MyButton from './MyButton'; // Import the MyButton component

    // Define a test case for the MyButton component
    test('renders button with label and responds to click', () => {
    // Create a mock function to track calls to onClick
    const handleClick = jest.fn();
    
    // Render the MyButton component with props
    render(<MyButton onClick={handleClick} label="Click Me" />);

    // Query the button element by its text content
    const button = screen.getByText(/click me/i);
    
    // Simulate a user clicking the button
    userEvent.click(button);

    // Assertions to verify the button is in the document
    expect(button).toBeInTheDocument();
    // Verify the handleClick function was called exactly once
    expect(handleClick).toHaveBeenCalledTimes(1);
    });
   ```

### 4. **Common Patterns**

   - **Testing Props**: `Check` **that** `component props` `change` `behavior or output`.
   - **State Changes**: `For stateful components`, `confirm that` `they render different content` `based on state`.
   - **Conditional Rendering**: `Ensure elements` `render` `or are hidden` `based on conditions`.
   - **Async Testing**: `RTL has` `utilities` **like** `'waitFor'` **to handle asynchronous code**.

### 5. **Helpful RTL Utilities**

   - **'screen'**: An `alternative` `to destructuring` `'getBy' and 'findBy'` `from render`; **it provides** `access` `to all queries` `globally`.
   - **'waitFor'**: `Waits for` `asynchronous updates to` **the** `component`.
   - **'userEvent'**: `Mocks` `user actions` **like** `typing`, `clicking`, **etc.**