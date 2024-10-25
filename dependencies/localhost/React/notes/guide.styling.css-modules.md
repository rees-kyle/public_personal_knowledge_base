---
id: p4ajmjyyv8r3xj7yticj5qr
title: 1 - CSS Modules
desc: ''
updated: 1729869422965
created: 1729864854659
---

**CSS Modules** are a great way `to style components` **in React** `with scoped`, `modular CSS`. They allow you `to write` `CSS` `that’s local to a` **specific** `component`, `preventing` your `styles` `from leaking across` **your** `app`, and they `integrate smoothly` **with modern React development**.

Here’s a **quick guide** to get you started with CSS Modules in React:

### 1. **Set Up CSS Modules**

   - `Create` **a** `CSS file` **with a** `.module.css` **extension**, such as **'MyComponent.module.css'**.
   - **In** your **React component**, `import` **the** `CSS module`:
     ```jsx
     // Import the CSS module file. This will create an object where each CSS class becomes a property.
     import styles from './MyComponent.module.css';
     ```

### 2. **Using CSS Modules**

   - **Once imported**, `each class from` the `CSS module file` **is** `available as` `a property on` **the** `styles object`.
   - **Apply a class** from the module like so:

```jsx
     function MyComponent() {
	return (
		// Render a div element with a CSS module class applied
		<div className={styles.container}> 
			
			{/* Render a heading with a CSS module class for styling */}
			<h1 className={styles.title}>Hello, CSS Modules!</h1> 

		</div>
	);
}

export default MyComponent;
```

   - **Each class name in the generated HTML will be unique**, so **styles won’t conflict with those in other components**.

### 3. **Example: CSS Module File**
   
   `Create` `MyComponent.module.css`:
   ```css
/* Styles for the main container */
.container {
	background-color: #f9f9f9; /* Light grey background color */
	padding: 20px;            /* Adds padding inside the container */
	border-radius: 5px;       /* Rounds the corners slightly */
}

/* Styles for the title text */
.title {
	color: #333;              /* Dark grey text color */
	font-size: 24px;          /* Large font size for emphasis */
}
   ```

### 4. **Conditional Styling**

   **You can also use conditional styling** `by dynamically applying` `classes`:
   ```jsx
    // Apply the 'active' class if someCondition is true; otherwise, apply the 'inactive' class
    <div className={someCondition ? styles.active : styles.inactive}>Content</div>
   ```
#
```css
/* Style for the 'active' state */
.active {
	background-color: #4CAF50; /* Green background for active state */
	color: white;              /* White text color */
	border: 2px solid #388E3C; /* Darker green border */
	padding: 10px;             /* Padding inside the element */
	border-radius: 5px;        /* Rounded corners */
}

/* Style for the 'inactive' state */
.inactive {
	background-color: #f0f0f0; /* Light grey background for inactive state */
	color: #666;               /* Dark grey text color */
	border: 2px solid #ccc;    /* Light grey border */
	padding: 10px;             /* Padding inside the element */
	border-radius: 5px;        /* Rounded corners */
}
```

### 5. **Combining Classes**

   **To combine multiple classes**, you can **use** `template literals`:
   ```jsx
    // Combine multiple CSS module classes using template literals
    <div className={`${styles.class1} ${styles.class2}`}>Content</div>
   ```

### Benefits of CSS Modules

- `Write` `modular and reusable` `CSS`.
- `Keep` `styles` `scoped to` **the** `component`.
- `Avoid` `global` `namespace conflicts`.



<!-- start of 'namespace' section -->
<details>
    <summary>Definition: namespace</summary>

#
A namespace **is a** `container` **that** `holds` `a set of` `identifiers` (**such as** `variable names`, `function names`, `classes`, **etc**.) **and** `allows for` **the** `organization and management of` **these** `identifiers` `to avoid` `naming conflicts`. Namespaces are **particularly useful in programming to group related code together and prevent collisions between names in larger projects**.

---
</details>
<!-- end of 'namespace' section -->