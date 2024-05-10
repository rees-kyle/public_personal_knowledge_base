---
id: hc44oh17wpn9wftdv856e9x
title: 5 - Modules
desc: ''
updated: 1715326723701
created: 1714159759852
---

One of the most impactful additions to ES6 is the **support for modules**. Modules **help in** `managing` **and** `encapsulating` `code` **in a** `maintainable` **and** `reusable` **way**. Below, I'll discuss what modules are, why they're beneficial, and how to use them in JavaScript.

### What are JavaScript Modules?

Modules **are a way** `to split up` `code` `into separate files` `while` `still sharing` `code` `between them`. Each module **can contain** `variables`, `functions`, `classes`, **or** `any other` `code construct` **and expose them to other modules as needed**.

### Why Use Modules?

- **Encapsulation**: Modules allow you to encapsulate functionality. `Each module` **can have its** `private variables` **and** `functions` **that aren't accessible from other modules unless explicitly exported**.



<!-- start of 'encapsulate' section -->
<details>
   <summary>Definition: encapsulate (in programming)</summary>

#
Encapsulate **means to** `enclose` `or` `contain` `something` `completely`, **often** `to protect` **it** `or` `keep` **it** `separate` `from` `external influences`. **In a programming context**, it **refers to the practice of bundling the data (variables) and methods (functions) that operate on the data into a single unit or class**, **and restricting access to some of the object's components**. **This makes the data and the code that manipulates it interdependent**, **simplifying the programming model and promoting security and manageability**.

---
</details>
<!-- end of 'encapsulate' section -->



<!-- start of 'interdependent' section -->
<details>
   <summary>Definition: interdependent</summary>

#
Interdependent **refers to** `two` `or more` `things` **that** `depend on` `each other`. In this relationship, **each element affects or relies on the others**, **often creating a system where the functioning of one component is linked to the functioning of another**.

---
</details>
<!-- end of 'interdependent' section -->



<!-- start of 'exported' section -->
<details>
   <summary>Definition: exported (in programming)</summary>

#
Exported **refers to** `making` **certain** `parts of` **a** `module` `or` `library` `available for` `use` `in` `other modules` `or` `programs`. **It's like marking specific functions**, **variables**, **or classes so that they can be accessed from outside the module where they are defined**.

---
</details>
<!-- end of 'exported' section -->



- **Reusability**: By isolating functionality in modules, you **can easily reuse them** `across` `different parts of` your `application` `without` `rewriting` `code`.
- **Maintainability**: Modules **help in** `organizing` `code` `logically`. `Smaller`, `module-based` codebases are **easier to maintain than large scripts**.
- **Namespace Management**: Using modules **helps** `avoid` `global` `namespace pollution`, `reducing` the chances of `variable name` `clashes`.
- **Lazy Loading**: Modules **can be loaded dynamically and lazily**, which **can** `improve` **the** `startup time of` `applications`.

### Exporting Module Features

You **can** `export functions`, `variables`, `classes`, **or** `any other` `valid` **JavaScript** `expression` `from` **a** `module`. Here are a couple of common methods to export:



<!-- start of 'exporting' section -->
<details>
   <summary>Definition: exporting (in programming)</summary>

#
Exporting **in programming means** `making parts of` **a** `module`, **such as** `functions`, `variables`, `or` `classes`, `available for` `use in` `other modules` `or` `files`. It **involves marking these components so that they can be imported and utilized elsewhere in the application**.

---
</details>
<!-- end of 'exporting' section -->



#### Named Exports
```javascript
// Exporting a constant variable 'name'
export const name = 'ChatGPT';
// 'export' keyword makes this variable available for import in other javascript files (modules)

// Exporting a function 'greet'
export function greet() {
// This function can be imported by other modules to be used elsewhere
   // Outputting text to the console
   console.log('Hello from a module!');
   // When 'greet' function is called, the string will be outputted. Useful for confirming that the module is working as expected
}
```

#### Default Export
```javascript
// Exporting a class as the default export of this module
export default class {
   // Constructor method to initialize the class with a 'message'
   constructor(message) {
      this.message = message; // Store the message passed to the constructor
   }

   // Method to output the message to the console
   greet() {
   // The 'greet' method is a function that prints the current value of 'this.message' to the console
      console.log(this.message);
   }
}
```

### Importing Module Features

To use the exported features in another module, you must import them. You **can** `import` `named exports` explicitly, `or` `import` **the** `default export`:

```javascript
// Importing named exports
import { name, greet } from './module.js'; // Imports specific, named exports

// Importing default export
import Greeting from './module.js'; // Imports the default export from 'module.js' and names it 'Greeting'

// Import everything from a module
import * as MyModule from './module.js'; // Imports all exports from 'module.js' as an object called 'MyModule'
MyModule.greet(); // Calls the 'greet' function from the 'MyModule' object

// Import with renaming
import { name as ModuleName } from './module.js'; // Imports the named export 'name' and renames it to 'ModuleName'
```

## Real-World Usage

**In a modern JavaScript project**, **especially those using frameworks** like React, Angular, or tools like Webpack and Babel, `modules` **are the** `standard` **way of** `organizing code`. For instance, you **might have a module for each component in a React app**, **and another for utility functions**.



<!-- start of 'utility functions' section -->
<details>
   <summary>Definition: utility functions (in programming)</summary>

#
Utility functions **are** `reusable` `pieces of` `code` **designed** `to perform` `common`, **often** `repeated` `tasks` **in programming**. **They simplify code management by handling specific operations that can be used across different parts of an application**.

---
</details>
<!-- end of 'utility functions' section -->



## Conclusion

`Modules` are a fundamental aspect of modern JavaScript programming. They `promote better` `coding practices` **and** `application structure`, `enhancing` `code quality`, `scalability`, **and** `performance`. **As JavaScript continues to evolve**, **the module system also sees improvements**, making it an essential feature for developers to master.