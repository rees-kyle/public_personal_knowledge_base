---
id: wqctkju1uc0yt9sbwsyp6im
title: 2 - Object Properties and Methods
desc: ''
updated: 1719989187845
created: 1713198033293
---

**In JavaScript**, `objects are` **one of the fundamental** `data types`, and **they** `consist of` `key-value` `pairs` **where** `keys` `are` `strings` (**or** `symbols`) `and` `values` `can be` `any` **valid JavaScript** `data type`, `including` `other objects`. Objects can have properties and methods:

1. **Properties**: These **are** `values` `associated with` **a JavaScript** `object`. **They** `describe` `characteristics` **of the object**. Properties **can be** `accessed` `using` `dot notation` (**object.property**) **or** `bracket notation` (**object['property']**).

    ```javascript
    // Creating an object
    let person = {
        name: "John",
        age: 30,
        email: "john@example.com"
    };

    // Accessing properties using dot notation
    console.log(person.name); // Output: John

    // Accessing properties using bracket notation
    console.log(person['age']); // Output: 30
    ```

2. **Methods**: These **are** `functions` `associated with` **an** `object`. They `allow` **the** `object to` `perform actions` **and** `manipulate` **its** `own properties`. Methods **are** `defined as` `key-value pairs` **where the** `value is` **a** `function`.

    ```javascript
    let person = {
        name: "John",
        age: 30,
        email: "john@example.com",
        greet: function() { // Method
            console.log("Hello, my name is " + this.name);
        }
    };

    // Calling the method
    person.greet(); // Output: Hello, my name is John
    ```

In the example above, '**name**', '**age**', **and 'email' are properties of the 'person' object**, while '**greet**' **is a method**. Note the use of '**this**' **inside the method is to refer to the current object ('person' in this case)**.

`Additionally`, `JavaScript` `provides` `a way` `to create` `objects` `using` `constructor functions` **or** `classes`, **and** `methods` `can be` `defined` `inside` **these** constructor functions or classes as well. This `allows for` **the** `creation of` `multiple instances of` `objects` `with` `shared methods`.

Examples of **creating objects using** both **constructor functions and classes** in JavaScript.

### Using Constructor Functions

Constructor functions are a `traditional way` `to create` `objects` in JavaScript.

```javascript
// Define a constructor function
function Person(name, age) {
    this.name = name; // Assign the name property
    this.age = age; // Assign the age property
}

// Add a method to the prototype
Person.prototype.greet = function() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

// Create an instance of Person
const person1 = new Person('Alice', 30);

// Call the greet method
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

### Using Classes

Classes provide a `more modern` `and clearer syntax for` `creating objects` `and dealing with` `inheritance`.

```javascript
// Define a class
class Person {
    // Constructor method to initialize object properties
    constructor(name, age) {
        this.name = name; // Assign the name property
        this.age = age; // Assign the age property
    }

    // Method defined within the class
    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

// Create an instance of Person
const person2 = new Person('Bob', 25);

// Call the greet method
person2.greet(); // Output: Hello, my name is Bob and I am 25 years old.
```

`Both methods` `achieve` **the** `same goal`, `but` **the** `class syntax` **is generally** `preferred for` **its** `clarity and` `ease of use`, **especially in complex applications**.