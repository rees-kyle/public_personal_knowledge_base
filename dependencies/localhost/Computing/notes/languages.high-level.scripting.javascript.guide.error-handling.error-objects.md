---
id: vhdwyz9e3ogs9isgkmxi7ht
title: 2 - Error Objects
desc: ''
updated: 1714361742016
created: 1714349507260
---

Understanding the use of Error objects is essential to effectively handle errors.

**An** `Error object` **in JavaScript** `is` **a** `built-in constructor` `used for` `creating` `error objects`. `When` `errors occur`, `JavaScript generates` **an** `Error object` **that** `describes` **the** `error` `and` `stores information` **about where it happened**.

## Creating an Error Object

You can create an Error object `using` **the** '`Error`' `constructor`:

```javascript
// Create a new Error object with a specified message
let error = new Error(message);
```

Here, `message` **is an** `optional` `string` `that describes` **the** `error`. The `Error object has` `two main` `properties`:

- `name`: The name `of` the `error` (`defaults to` `"Error"`).
- `message`: The message `passed` `when` **the** `error was` `constructed`.

```javascript
let error = new Error("Something went wrong!");
console.log(error.name);    // Output: "Error"
console.log(error.message); // Output: "Something went wrong!"
```

## Types of Built-in Error Objects

JavaScript provides several types of built-in error objects **that extend from the basic Error object**. **Each represents** `different` `error types`:

- `RangeError`: Thrown **when a** `value` **is** `not in` **a** `set or range of` `allowed values`.
- `ReferenceError`: Thrown **when there is an** `illegal reference`.



<!-- start of 'reference' section -->
<details>
    <summary>Definition: reference</summary>

#
A "reference" **is a** `mention or` `citation of` **a** `source of information`, `or` **a** `person who` `can provide` **a** `testimonial about` `one's character` `or abilities`.

---
</details>
<!-- end of 'reference' section -->



<!-- start of 'citation' section -->
<details>
    <summary>Definition: citation</summary>

#
A "citation" **is a** `reference to` **a** `source`, **such as a** `book`, `article`, **or** `website`, **typically used** `to provide` `evidence` `or` `support for` `a point made` `in a text`.

---
</details>
<!-- end of 'citation' section -->



<!-- start of 'testimonial' section -->
<details>
    <summary>Definition: testimonial</summary>

#
A "testimonial" **is a** `statement or` `endorsement`, **typically** `written or` `spoken`, **that** `praises` `someone's qualities or` `vouches for` **their** `character or` `abilities` `based on` `personal experience`.

---
</details>
<!-- end of 'testimonial' section -->



<!-- start of 'statement' section -->
<details>
    <summary>Definition: statement</summary>

#
A "statement" **is a** `clear` `expression of` `something in` `spoken or` `written words`.

---
</details>
<!-- end of 'statement' section -->



<!-- start of 'endorsement' section -->
<details>
    <summary>Definition: endorsement</summary>

#
An "endorsement" **is a** `public or` `official statement of` `support or` `approval`.

---
</details>
<!-- end of 'endorsement' section -->



<!-- start of 'illegal' section -->
<details>
    <summary>Definition: illegal</summary>

#
"Illegal" **refers to** `something` **that is** `prohibited by` `law` `or` `against` **the** `rules` `established by` `legal authority`.

---
</details>
<!-- end of 'illegal' section -->



- `SyntaxError`: Thrown when a syntax error `occurs while` `parsing code`.
- `TypeError`: Thrown **when a** `value` `is not of` **an** `expected type`.
- `URIError`: Thrown **when** `incorrect use of` `global URI` `handling functions` `occurs`.



<!-- start of 'uniform resource identifier' section -->
<details>
    <summary>Definition: uniform resource identifier</summary>

#
`URI` **stands for** `Uniform Resource Identifier`. **It is a** `string of` `characters` `used to` `identify` `a resource` **either** `on` **the** `internet or` **a** `local network`. The **primary purpose of a URI is to enable interaction with representations of resources over a network using specific protocols**.

---
</details>
<!-- end of 'uniform resource identifier' section -->



```javascript
// Function to check if a number exceeds 100
function checkNumber(num) {
    // If the number is greater than 100, throw a RangeError
    if (num > 100) {
        throw new RangeError('The number should be less than or equal to 100');
    }
    // If the number is 100 or less, return the number
    return num;
}

// Try block to attempt the 'checkNumber' function and handle potential errors
try {
    // Call 'checkNumber' function with 101, which is above the threshold and should cause an error
    console.log(checkNumber(101));

// Catch block to handle errors thrown by the 'checkNumber' function
} catch (e) {
    // Log the name of the error
    console.log(e.name);  // Output: "RangeError"
    // Log the message of the error
    console.log(e.message);  // Output: "The number should be less than or equal to 100"
}
```

Understanding these error handling mechanisms in JavaScript `improves` **your** `ability to` `write` `resilient`, `error-resistant` `applications`.



<!-- start of 'resilient' section -->
<details>
    <summary>Definition: resilient</summary>

#
"Resilient" **refers to the** `ability to` `recover` `quickly` `from difficulties or` `adapt well to` `challenges`.

---
</details>
<!-- end of 'resilient' section -->



<!-- start of 'resistant' section -->
<details>
    <summary>Definition: resistant</summary>

#
"Resistant" **refers to the** `ability to` `withstand or` `not be` `affected by` **a particular** `thing or` `condition`.

---
</details>
<!-- end of 'resistant' section -->