---
id: wqrll1dxsk3be3tuml27spr
title: 3 - Emotion
desc: ''
updated: 1729966077069
created: 1729963268332
---

Emotion **is a powerful** `CSS-in-JS` `library` `for styling components` `in React`. It allows you **to write CSS directly within your JavaScript** and can be particularly **helpful in** `creating` `dynamic and themeable` `components`.

Here’s a quick breakdown of using Emotion in React:

### 1. **Setup**

To `install` Emotion, **you can use either** `npm` **or yarn**:
```bash
# BASH
npm install @emotion/react @emotion/styled
```

### 2. **Using Emotion in React**

There are `two` **primary** `ways` `to use` **Emotion**: 

- '`@emotion/react`' **for the** `css prop` `and creating styled components`
- '`@emotion/styled`' **for building** `styled components` `similar to` **the** `Styled Components library`.

#### a. **The 'css' Prop**

The 'css' prop **allows you** `to add` `CSS styles` **directly** `to` **your** `component`:
```javascript
/** @jsxImportSource @emotion/react */
// This pragma tells the compiler to use Emotion's JSX transformation,
// enabling the use of the `css` prop for styling without needing to 
// import the `css` function in every component.

import { css } from '@emotion/react'; // Importing Emotion for the `css` prop functionality

// Defining a React component
const MyComponent = () => (
  // Applying styles using the `css` prop from Emotion
  <div
    css={css`
      background-color: lightblue;
      padding: 20px;
      font-size: 1.2rem;
    `}
  >
    Hello Emotion! // Content of the component
  </div>
);

export default MyComponent; // Exporting the component for use in other parts of the application
```

#### b. **Styled Components with Emotion**

You can also create reusable styled components with `@emotion/styled`:
```javascript
import styled from '@emotion/styled'; // Importing the styled function from Emotion

// Creating a styled button component using Emotion
const Button = styled.button`
  padding: 10px 20px;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;

  &:hover {
    background-color: #0056b3;
  }
`;

// Defining the main App component
const App = () => <Button>Click Me</Button>; // Rendering the Button component

export default App; // Exporting the App component for use in other parts of the application
```

### 3. **Theming with Emotion**

`Emotion supports` `themes` **that can be** `passed through` **React’s** `ThemeProvider`:
```javascript
import { ThemeProvider } from '@emotion/react';  // Importing ThemeProvider from Emotion to manage themes

// Defining a theme object with primary and secondary colors
const theme = {
  colors: {
    primary: '#007BFF',     // Primary color for the button
    secondary: '#0056b3'    // Secondary color for the button hover effect
  }
};

// Creating a styled button component using Emotion
const Button = styled.button`
  padding: 10px 20px;
  background-color: ${({ theme }) => theme.colors.primary};
  color: white;

  &:hover {
    background-color: ${({ theme }) => theme.colors.secondary};
  }
`;

// Defining the main App component
const App = () => (
  // Wrapping the Button component in ThemeProvider to pass the theme
  <ThemeProvider theme={theme}>
    <Button>Click Me</Button> // Rendering the Button component
  </ThemeProvider>
);
```

`Emotion’s` `flexibility` **with themes**, **the 'css' prop**, **and styled components** `makes it` **a** `versatile` **tool** `for styling` `React applications`. This approach **helps** `keep` `styles scoped` `and reduces` **the potential for** `styling conflicts`, **especially** `in large projects`.