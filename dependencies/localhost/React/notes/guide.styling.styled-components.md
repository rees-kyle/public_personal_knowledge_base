---
id: ocu9mdsic2tud0ellu13wg5
title: 2 - Styled Components
desc: ''
updated: 1729962503276
created: 1729960505268
---

**Using styled-components** in React **is a popular way** `to style components with` `a clean`, `modular approach`. Styled-components **allow you** `to create` `custom`, `reusable components` `with encapsulated styles`. Here’s a quick overview:

### 1. Installing styled-components
**First**, you’ll need to `install` **the** `package`:
```bash
# BASH
npm install styled-components
```

### 2. Creating Styled Components

Once installed, you can `create` `styled components` **directly** `in` **your** `JavaScript file`. **Each** `styled component is` **essentially a** `React component` `with styles applied` **to it**.

```jsx
import styled from 'styled-components';

// Create a styled button component
const Button = styled.button`
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 5px;
  
  &:hover {
    background-color: #45a049;
  }
`;
```

### 3. Using Styled Components in Your Components

**Now**, **you can use your styled Button component like any other React component**:

```jsx
// Define the main App component
const App = () => (
  // Render a container div for the App component
  <div>
    {/* Render the styled Button component with text */}
    <Button>Click Me</Button>
  </div>
);

// Export the App component as the default export
export default App;
```

### 4. Passing Props to Styled Components

You **can also** `make` **your** `styled components` `dynamic` `by passing props`. **For instance**, **changing the button color based on a 'primary' prop**:

```jsx
const Button = styled.button`
  /* Set background color based on the 'primary' prop */
  background-color: ${props => props.primary ? '#4CAF50' : '#008CBA'};
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  /* Change background color on hover, based on the 'primary' prop */
  &:hover {
    background-color: ${props => props.primary ? '#45a049' : '#005f73'};
  }
`;
```

**Now**, **pass the 'primary' prop** to control the button’s style:

```jsx
// Render a Button component with the 'primary' prop applied, making it a "Primary Button"
<Button primary>Primary Button</Button>

// Render a Button component without the 'primary' prop, making it a "Default Button"
<Button>Default Button</Button>
```

### 5. Extending Styled Components

Styled-components also let you `extend` `existing styles` `easily`:

```jsx
// Create a styled PrimaryButton component by extending the existing Button component
const PrimaryButton = styled(Button)`
  font-size: 18px;
  font-weight: bold;
`;

// Render the PrimaryButton component with customized styles
<PrimaryButton>Extended Button</PrimaryButton>
```

### 6. Global Styles

If you want `to apply` `global styles` **across your app**, **you can** `use` `createGlobalStyle`:

```jsx
// Import createGlobalStyle function from styled-components to define global styles
import { createGlobalStyle } from 'styled-components';

// Create a GlobalStyle component to apply global styles across the app
const GlobalStyle = createGlobalStyle`
  body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
    margin: 0;
    padding: 0;
  }
`;

// Define the main App component
const App = () => (
  <>
    {/* Apply the GlobalStyle component to the app */}
    <GlobalStyle />

    {/* Render the Button component with global styles applied */}
    <Button>Button with Global Styles</Button>
  </>
);

export default App;
```

### Tips for Using Styled Components
- **Consistent theming**: `Use themes` `to maintain` `consistency` across your app.
- **Scoped styling**: Since **each component's styles are scoped to that component**, it **helps** `avoid unintended` `style bleeding`.
- **Dynamic styling**: `Pass props to components` `to create` `reusable`, `adaptable styles`.

`This approach gives` **your** `components` `modular`, `readable`, **and** `maintainable styles` `while keeping` **the** `styling concerns` `scoped and organized` **in** your **React** project.