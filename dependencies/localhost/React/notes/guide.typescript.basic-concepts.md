---
id: h961wlny7a3m7q9a8xmdmsb
title: 1 - Basic Concepts
desc: ''
updated: 1730760359329
created: 1730573136996
---

Using TypeScript in React can **greatly** `improve` **the** `development experience` `by adding type safety`, `reducing runtime errors`, **and** `making` **your** `code` `more understandable`. Here’s a breakdown of **some fundamental TypeScript concepts** in React:

### 1. **Setting Up TypeScript in a React Project**
   - `For new projects`, **you can set up TypeScript** `with 'create-react-app'`:
     ```bash
     # BASH
     npx create-react-app my-app --template typescript
     ```
   - `In existing` **React** `projects`, `add` **TypeScript** `by installing` **the** `dependencies`:
     ```bash
     # BASH
     npm install typescript @types/react @types/react-dom
     ```
   - `Create or edit` **a** `tsconfig.json` **file** `to configure` **TypeScript**.

### 2. **Typing Functional Components**
   - `Use 'React.FC'`
```typescript
// Importing React to use JSX and type definitions
import React from 'react';

// Defining the component using React.FC, which automatically types 'children' and other common props
const MyComponent: React.FC<{ message: string }> = ({ message }) => {
  // Renders the 'message' prop within a div
  return <div>{message}</div>;
};
```

   - `or define` **the** `component’s prop types` **directly**, `without 'React.FC'`:
```typescript
// Importing React to use JSX
import React from 'react';

// Defining a type for the component’s props
type MyComponentProps = { 
  message: string; // Message must be a string
};

// Defining the component without React.FC, explicitly typing the props
const MyComponent = ({ message }: MyComponentProps) => {
  // Renders the 'message' prop within a div
  return <div>{message}</div>;
};
```


### 3. **Typing Props**
   - `Define` **a** `'Props' type` **and** `use it for` **your** `component’s props`. This `adds` `type-checking for` **the** `component’s properties`:
     ```typescript
    // Define a type for the Button component's props
    type ButtonProps = {
    label: string;          // Label text to display on the button
    onClick: () => void;    // Function to handle button click events
    };

    // Define the Button component, typing its props with ButtonProps
    const Button: React.FC<ButtonProps> = ({ label, onClick }) => {
    // Renders a button element with an onClick event and label
    return <button onClick={onClick}>{label}</button>;
    };
     ```

### 4. **Using 'useState' with Types**
   - **TypeScript can** `infer` **the** `type of` `'useState'`, `but` **you** `can also` `specify it`:
     ```typescript
    // Declares a state variable 'count' of type number, initialized to 0
    const [count, setCount] = useState<number>(0);

    // Declares a state variable 'user' which can be an object with 'name' and 'age' properties or null, initialized to null
    const [user, setUser] = useState<{ name: string; age: number } | null>(null);
     ```



<!-- start of 'infer' section -->
<details>
    <summary>Definition: infer (in typescript)</summary>

#
In TypeScript, infer **means** "`automatically determine` `the type`." When **TypeScript** "infers" a type, it `looks at` **the** `value` `assigned to` `a variable` `or the way` `a function` `is used` `and decides` `the type` `based on` **that** `context`, `without requiring` **you** `to specify it` **explicitly**.

---
</details>
<!-- end of 'infer' section -->



### 5. **Typing 'useEffect' Dependencies**
   - Types in 'useEffect' dependencies **can** `prevent issues` `with missing dependencies` `or incorrect types`, **though you usually** `don’t need to` `add type annotations` `unless` `working with` `complex objects`.

### 6. **Event Handling**
   - TypeScript `provides built-in types` `for DOM events`:
     ```typescript
    // Define a function to handle button click events
    // The 'event' parameter is typed as a MouseEvent occurring on an HTMLButtonElement
    const handleClick = (event: React.MouseEvent<HTMLButtonElement>) => {
    // Handle the click event (e.g., add logic here)
    };

    // Define a function to handle input change events
    // The 'event' parameter is typed as a ChangeEvent occurring on an HTMLInputElement
    const handleChange = (event: React.ChangeEvent<HTMLInputElement>) => {
    // Logs the current value of the input field
    console.log(event.target.value);
    };
     ```

### 7. **Typing Refs**
   - `Use 'useRef'` `with types` `to access` `DOM elements`:
     ```typescript
    // Create a ref for an HTML input element, initialized to null
    const inputRef = useRef<HTMLInputElement>(null);

    // Define a function to focus the input element
    const focusInput = () => {
    // Check if the ref currently points to an input element
    if (inputRef.current) {
        // Focus the input element if it exists
        inputRef.current.focus();
    }
    };
     ```

### 8. **Typing Context and Custom Hooks**
   - `Context values` **and** `custom hooks` **can be typed** `to ensure` `safe usage` `across components`:
     ```typescript
    // Define a union type 'Theme' that can be either 'light' or 'dark'
    type Theme = 'light' | 'dark';

    // Create a context for the theme, which can be of type Theme or undefined (defaulting to undefined)
    const ThemeContext = React.createContext<Theme | undefined>(undefined);

    // Define a custom hook to use the ThemeContext
    const useTheme = (): Theme => {
    // Retrieve the current theme value from the context
    const context = useContext(ThemeContext);
    
    // Throw an error if there's no context value (e.g., if the hook is used outside of a ThemeProvider)
    if (!context) throw new Error("useTheme must be used within a ThemeProvider");
    
    // Return the current theme value
    return context;
    };
     ```

### 9. **Typing Higher-Order Components (HOCs)**
   - `HOCs` **can be** `tricky`, `but` **they’re** `manageable` **with TypeScript** `using` `generic types`:
     ```typescript
    // Define a higher-order component (HOC) that adds logging functionality to a component
    // 'withLogging' takes a component as an argument, with props of any type 'T'
    function withLogging<T>(Component: React.ComponentType<T>) {
    // Return a new component that wraps the original component with additional functionality
    return (props: T) => {
        // Log a message each time the component renders
        console.log('Rendering', Component.name);
        
        // Render the original component, passing along all props
        return <Component {...props} />;
    };
    }
     ```

> HOC: Higher-Order Component



<!-- start of 'higher-order component' section -->
<details>
  <summary>Definition: higher-order component</summary>

#
A Higher-Order Component (HOC) **is a** `pattern` `in React` **used** `to enhance or modify` `the behavior of` `a component`. It’s **a** `function` `that takes` **a** `component as` **an** `argument` `and returns` **a** `new component` `with additional features or functionality`.

---
</details>
<!-- end of 'higher-order component' section -->



### 10. **Using Generics in Components**
   - **Generics** `make components` `more flexible` **by allowing you** `to pass` `types dynamically`:
     ```typescript
  // Define a generic type 'ListProps' that can take any type 'T'
  // 'items' is an array of type 'T' and 'renderItem' is a function that takes an item of type 'T' and returns a JSX element
  type ListProps<T> = {
    items: T[];                           // Array of items of type 'T'
    renderItem: (item: T) => JSX.Element; // Function to render each item as a JSX element
  };

  // Define a List component that accepts props of type ListProps<T> and uses generics
  const List = <T,>({ items, renderItem }: ListProps<T>) => {
    // Renders a <ul> element with each item in 'items' rendered using 'renderItem'
    return <ul>{items.map(renderItem)}</ul>;
  };
     ```

**With these concepts, you’ll have a solid foundation for working with TypeScript in React**, **enabling** `stronger code structure` **and** `reducing bugs`.