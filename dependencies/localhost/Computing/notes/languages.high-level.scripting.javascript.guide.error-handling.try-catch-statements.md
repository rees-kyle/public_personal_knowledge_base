---
id: vavso9lyvb7q1y9qxk15qmg
title: 1 - 'try...catch' Statements
desc: ''
updated: 1714349533277
created: 1714193899701
---

In JavaScript, error handling is an **essential aspect of robust application development**, **allowing** `programs` **to** `manage` `and` `respond to` `runtime errors` **gracefully**. One of the **primary mechanisms provided by JavaScript** for error handling **is the try...catch statement**. This mechanism **helps** `prevent` **the** `application` `from crashing` **by** `catching exceptions` **that occur** `during` **the** `execution of` `code blocks`.



<!-- start of 'gracefully' section -->
<details>
    <summary>Definition: gracefully</summary>

#
The word "gracefully" **means** `doing` `something in` **a** `smooth` **and** `elegant way`. It **suggests that the action looks easy and pleasing**.

---
</details>
<!-- end of 'gracefully' section -->



<!-- start of 'elegant' section -->
<details>
    <summary>Definition: elegant</summary>

#
"Elegant" **describes** `something` **that is** `beautifully stylish` **and** `graceful`.

---
</details>
<!-- end of 'elegant' section -->



<!-- start of 'graceful' section -->
<details>
    <summary>Definition: graceful</summary>

#
"Graceful" **means** `moving in` **a** `smooth` **and** `attractive way`.

---
</details>
<!-- end of 'graceful' section -->



<!-- start of 'exception' section -->
<details>
    <summary>Definition: exception</summary>

#
An "exception" **is** `something` **that** `does not` `follow` **the** `usual rule` **or** `pattern`.

---
</details>
<!-- end of 'exception' section -->



### Basic Syntax

The try...catch statement `consists of` **a** `try block` **to wrap potentially error-prone code**, `followed by` `one or more` `catch blocks` **to handle any exceptions that are thrown within the try block**.

```javascript
try {
    // Code that may throw an exception
    
} catch (error) { // 'error' holds information about the error that occurred
    // Code to execute if an exception is thrown

    // Log the error to the console
    console.log(error);
}
```

### Example: Catching a ReferenceError

```javascript
try {
    // Attempt to access a variable that has not been defined
    // This will throw a ReferenceError because 'nonExistentVariable' does not exist in the scope
    console.log(nonExistentVariable);

// 'error' is the exception object thrown, it contains details about what went wrong
} catch (error) {
    // Log the error message to the console
    console.error("Caught an error:", error);
    // It outputs errors to the web console, making them stand out for easier debugging
}
```

In this **example**, **trying to log a non-existent variable would normally throw a ReferenceError**, **which would stop the execution of subsequent code**. **However**, **with try...catch**, **the error is caught and handled**, **allowing the program to continue running**.

### The `finally` Clause

The **try...catch statement can also include a finally clause**, which will be `executed` `after` **the** `try` `and` `catch blocks`, `regardless of` **whether an** `exception was` `thrown` `or not`. This is **useful for** `cleaning up` `resources` **or performing** `cleanup operations`.

```javascript
try {
    // Throw an error with a custom message
    throw new Error("Something went wrong!");
    // This simulates an error condition and demonstrates the use of 'throw' to create an exception

} catch (error) {
    // This block is executed if an error is thrown in the try block

    // Output the error information to the console
    console.error("Error encountered:", error);
    // The console.error method is used to log errors, and it typically displays the message in red in the console
    
} finally {
    // This block executes after the try and catch blocks, regardless of whether an error was thrown or not
    // Useful for including cleanup code or other final actions that need to run irrespective of the outcome

    console.log("This runs no matter what");
    // Log a message indicating that this block runs regardless of error occurrence
}
```



<!-- start of 'irrespective' section -->
<details>
    <summary>Definition: irrespective</summary>

#
"Irrespective" **means** `not taking` `something into` `account` **or** `regardless of`.

---
</details>
<!-- end of 'irrespective' section -->



<!-- start of 'regardless' section -->
<details>
    <summary>Definition: regardless</summary>

#
"Regardless" **means** `without` `being` `affected by`; `in spite of`.

---
</details>
<!-- end of 'regardless' section -->



<!-- start of 'in spite of' section -->
<details>
    <summary>Definition: in spite of</summary>

#
"In spite of" **means** `even though` **or** `despite something`.

---
</details>
<!-- end of 'in spite of' section -->



<!-- start of 'despite' section -->
<details>
    <summary>Definition: despite</summary>

#
"Despite" **means** `even though` `something` `exists` **or** `happens`.

---
</details>
<!-- end of 'despite' section -->



### Error Object

The **catch block receives an argumen that represents the exception thrown by the try block**. This **object usually** `contains` `at least` **a** `name` `and` **a** `message property`, **providing details about the** `type` `and` `description of` **the** `error`.

### Advanced Usage: Custom Errors

You **can also** `throw` **your own** `custom errors` **using** `throw` `followed by` **an** `Error object`. This can be **useful for** `handling` `specific` `kinds of` `errors in` **a more** `controlled way`.

```javascript
try {
    // Custom condition check
    let age = -10;
    // Initialize the 'age' variable with an invalid value of -10

    // Check if the age is less than 0, to ensure that age values are logically correct (non-negative)
    if (age < 0) {
        // If the condition is true (age is negative), throw a custom error with an explanation
        throw new Error("Age cannot be negative.");
    }
} catch (error) {
    // This catch block catches the custom Error thrown when 'age' is negative

    // Output the error message to the console
    console.error("Caught an error:", error);
    // Informs the user or developer of what went wrong
}
```

### Summary

- **try...catch**: `Helps to` `handle errors` **gracefully**.
- **finally**: `Executes code` `regardless of` **whether an** `error was` `caught`.
- **throw**: **Can be used to** `generate` `custom errors`.
- **Error object**: `Contains` `details about` **the** `error`.

Using **try...catch in JavaScript allows for** `more resilient` `code` **that can** `handle` `unexpected situations` `without crashing`. It's particularly **useful in** `situations where` **the** `input` `may not` `be predictable`, **or when** `dealing with` `external APIs` **where failures might occur due to reasons outside of your control**.