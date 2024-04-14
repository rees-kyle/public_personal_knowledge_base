---
id: wmj55sm4djtp4i8o48q92nm
title: 3 - Return Statements
desc: ''
updated: 1713100694216
created: 1713038899760
---

In JavaScript, return statements **are used to** `specify` **the** `value that` **a** `function` `should return` `when` **it is** `invoked`. Here's a basic example:

```javascript
function add(a, b) {
    return a + b;
}

let result = add(3, 4); // result will be 7
```

In this example, the **add function takes two parameters (a and b)**, **adds them together**, and **then returns the result using the return statement**. **When the add function is called with arguments 3 and 4**, **it returns 7**, **which is stored in the variable result**.

A `return statement` **can** `appear` `anywhere` `in` **a** `function`, and `once` **a** `return statement` **is** `executed`, **it immediately** `exits` **the** `function`, `ignoring` **any** `subsequent` `code`.



<!-- start of 'subsequent' section -->
<details>
    <summary>Definition: subsequent</summary>

#
"Subsequent" **refers to** `something` **that** `follows` **or** `comes after` `something else` **in** `time`, `order`, **or** `sequence`.

---
</details>
<!-- end of 'subsequent' section -->



<!-- start of 'sequence' section -->
<details>
    <summary>Definition: sequence</summary>

#
"Subsequent" **refers to** `something` **that** `follows` **or** `comes after` `something else` **in** `time`, `order`, **or** `sequence`.

---
</details>
<!-- end of 'sequence' section -->



```javascript
function foo() {
    console.log("Hello");
    return 42; // This will cause the function to exit immediately after printing "Hello"
    console.log("World"); // This line will never be executed
}

foo(); // Output: "Hello"
```

`Functions` **in JavaScript** `without` **an explicit** `return statement` **implicitly** `return` `undefined`.



<!-- start of 'explicit' section -->
<details>
    <summary>Definition: explicit</summary>

#
"Explicit" **means** `something` **is** `very clear` **and** `straightforward`, **leaving** `no` **room for** `confusion`.

---
</details>
<!-- end of 'explicit' section -->



<!-- start of 'implicitly' section -->
<details>
    <summary>Definition: implicitly</summary>

#
"Implicitly" **means** `something` **is** `understood` `without` `being said` `directly`.

---
</details>
<!-- end of 'implicitly' section -->



```javascript
function greet(name) {
    console.log("Hello, " + name + "!");
}

let message = greet("Alice"); // Output: "Hello, Alice!"
console.log(message); // Output: undefined
```

Here, **message is assigned the return value of greet("Alice")**, which is **undefined because greet doesn't have a return statement**.

**To ensure that the greet function returns a value**, **you can modify it to explicitly return a greeting message instead of just logging it**. Here's the **fixed code**:

```javascript
function greet(name) {
    return "Hello, " + name + "!";
}

let message = greet("Alice"); // Output: "Hello, Alice!"
console.log(message); // Output: "Hello, Alice!"
```

Now, the **greet function returns the greeting message**, `allowing` **you** `to capture` **and** `use` **it** `elsewhere` `in` **your** `code`.