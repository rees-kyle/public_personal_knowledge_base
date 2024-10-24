---
id: cbbu9ipou2sgya25uptm52p
title: 1 - Controlled Vs Uncontrolled Components
desc: ''
updated: 1729793299629
created: 1729252673517
---

In React, `forms` **can be** `managed` `using` **either** `controlled` `or` `uncontrolled` `components`, **each with its own advantages and use cases**. Here’s a **breakdown** of both:

### Controlled Components

- **Definition**: In controlled components, the `form data` **is** `handled by` **the** `state of` **the** `React component`. The `input elements' values` **are** `controlled by` `React`, **meaning they** `rely on` `state` `to determine` **their** `values`.

- **How It Works**:
  - **You** `set` **the** `value of` **the** `input field to` **a** `state variable`.
  - **You** `handle` `changes to` **the** `input field` `by updating` **the** `state` `through` **an** `event handler`.

- **Example**:
    ```jsx
    import React, { useState } from 'react';

    // Define the ControlledForm component
    function ControlledForm() {
    // Declare a state variable 'inputValue' to hold the input field value
    const [inputValue, setInputValue] = useState('');

    // Handle input change and update state
    const handleChange = (event) => {
        setInputValue(event.target.value); // Update 'inputValue' with the current input value
    };

    // Handle form submission
    const handleSubmit = (event) => {
        event.preventDefault(); // Prevent the default form submission behavior
        alert(`Submitted value: ${inputValue}`); // Display the submitted value in an alert
    };

    // Render the form
    return (
        <form onSubmit={handleSubmit}> {/* Attach handleSubmit to form's onSubmit event */}
        <input 
            type="text" 
            value={inputValue} // Bind input value to the state variable 'inputValue'
            onChange={handleChange} // Attach handleChange to input's onChange event
        />
        <button type="submit">Submit</button> {/* Button to submit the form */}
        </form>
    );
    }

    export default ControlledForm; // Export the component for use in other files
    ```

- **Advantages**:
  - `Easier to` `manage and validate` `form data`.
  - **Provides** `a single` `source of` `truth`, **as the input value is stored in the state**.
  - Makes it `easier to` `implement` `dynamic validation`, `conditional rendering`, **and other features**.

### Uncontrolled Components

- **Definition**: In uncontrolled components, the `form data` **is** `managed by` `the DOM` **itself**. You **use** `refs` `to access` **the** `form elements` **directly**, **and** `React` `does not` `control` **the** `input's value`.

- **How It Works**:
  - **You** `access` **the** `input values` **using** `refs` **instead of using state to store the input values**.

- **Example**:
  ```jsx
  import React, { useRef } from 'react';

  function UncontrolledForm() {
    // Create a reference to the input element using useRef hook
    const inputRef = useRef(null);

    // Handle the form submission
    const handleSubmit = (event) => {
      event.preventDefault(); // Prevent the default form submission behavior
      alert(`Submitted value: ${inputRef.current.value}`); // Alert the current value of the input
    };

    return (
      // Form submission triggers handleSubmit function
      <form onSubmit={handleSubmit}>
        {/* Input field is referenced by inputRef */}
        <input type="text" ref={inputRef} />
        {/* Submit button */}
        <button type="submit">Submit</button>
      </form>
    );
  }

  export default UncontrolledForm;
  ```

- **Advantages**:
  - `Simpler` `for quick forms` `without needing` `to manage state`.
  - **Can be** `useful` `for integrating with` `non-React libraries` `or existing codebases`.
  - `Less boilerplate code` `for forms with` `many inputs`.

### Choosing Between Controlled and Uncontrolled

- **Use** `Controlled Components` **when you need** `to manage` `form data` `closely`, **such as** `for complex forms`, `validation`, **or when you want to have a** `clear flow of data`.
- **Use** `Uncontrolled Components` `for simple forms` **or** when you're `integrating` **with** `third-party libraries`, **where you don't need to manage the input state actively**.

In practice, **many** `developers prefer` `controlled components for` **their** `consistency and` **ease of** `validation`, `while` `uncontrolled components` **can be** **handy** `for less complex scenarios`.