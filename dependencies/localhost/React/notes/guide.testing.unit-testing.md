---
id: z03y2hhcpphswpciqwb10iw
title: 1 - Unit Testing
desc: ''
updated: 1730508702258
created: 1730507548000
---

To get started with unit testing in React `using Jest`, you can follow these steps:

### 1. **Install Jest**
   Jest `comes pre-installed` `with Create React App`, `but` **if you're setting up a** `custom` `React project`, **you’ll need to** `install it`:

   ```bash
   # BASH
   npm install --save-dev jest
   ```

   **Also**, `for testing` `React components`, **you may want to** `install` `'React Testing Library'`:

   ```bash
   # BASH
   npm install --save-dev @testing-library/react
   ```

### 2. **Setup a Test Script**
   `Add` **a** `test script to` **your** `'package.json'` **to run Jest**:

   ```json
   "scripts": {
     "test": "jest"
   }
   ```

   **If you are using Create React App**, **this will already be configured**.

### 3. **Write Unit Tests**
   `Create` `test files` **alongside the components you want to test**. **Jest will recognize files with** `'.test.js'` **or** `'.spec.js'` `extensions`.

   #### Example
   **For a component named** `Button.js`, **create a file called** `Button.test.js`.

   ```jsx
    // Button.js
    // Import React to use JSX syntax and create a functional component
    import React from 'react';

    // Define and export the Button component
    // It receives `label` (text to display on the button) and `onClick` (function to call when clicked) as props
    export default function Button({ label, onClick }) {
    // Render a button element
    // The button displays the `label` text and triggers `onClick` when clicked
    return <button onClick={onClick}>{label}</button>;
    }
   ```

   ```jsx
    // Button.test.js
    // Import necessary functions and modules from React Testing Library
    import { render, screen, fireEvent } from '@testing-library/react';
    // Import the Button component to test
    import Button from './Button';

    // Test to check if the button renders with the correct label
    test('renders button with label', () => {
    // Render the Button component with the label "Click Me"
    render(<Button label="Click Me" />);
    // Check if the button with the label text "Click Me" is in the document
    expect(screen.getByText(/click me/i)).toBeInTheDocument();
    });

    // Test to check if the onClick handler is called when the button is clicked
    test('calls onClick when clicked', () => {
    // Create a mock function to simulate the onClick handler
    const handleClick = jest.fn();
    // Render the Button component with the mock onClick handler
    render(<Button label="Click Me" onClick={handleClick} />);
    // Simulate a click event on the button
    fireEvent.click(screen.getByText(/click me/i));
    // Check if the handleClick function was called exactly once
    expect(handleClick).toHaveBeenCalledTimes(1);
    });
   ```

### 4. **Run Tests**
   Run your tests **by executing**:

   ```bash
   # BASH
   npm test
   ```

### 5. **Best Practices for Testing**
   - **Isolate components**: `Mock dependencies` **where necessary**.
   - **Keep tests simple**: `Focus on` `one thing` `per test case`.
   - **Use meaningful names**: `Describe exactly` `what each test` `does`.