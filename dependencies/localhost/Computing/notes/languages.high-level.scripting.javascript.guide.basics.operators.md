---
id: 0skl0t10hrw9wpuhiyy00xk
title: 3 - Operators
desc: ''
updated: 1712858260521
created: 1712782328472
---

**In JavaScript**, **operators are** `symbols` **that are used to** `perform operations` `on` `operands`. Here's an overview of the `different` `types` **of** `operators` **in JavaScript**:



<!-- start of 'operands' section -->
<details>
    <summary>Definition: operands</summary>

#
These are the `values` **or** `variables` **that are** `involved` **in an** `operation`. They're like the ingredients you use to perform an action. For example, in 5 + 3, 5 and 3 are operands.

---
</details>
<!-- end of 'operands' section -->



<!-- start of 'operations' section -->
<details>
    <summary>Definition: operations</summary>

#
These are the `actions` **or** `tasks` `performed` `on` `operands` **to** `produce` **a** `result`.

---
</details>
<!-- end of 'operations' section -->



<!-- start of 'operators' section -->
<details>
    <summary>Definition: operators</summary>

#
These are the `symbols` **or** `keywords` **that** `represent` **specific** `operations`. They're **like** the **tools** you use to perform actions.

---
</details>
<!-- end of 'operators' section -->



## Arithmetic Operators
Used for arithmetic operations **like** `addition`, `subtraction`, `multiplication`, `division`, etc.



<!-- start of 'console.log()' section -->
<details>
    <summary>console.log()</summary>

#
'console.log()' **is a** `method` **in JavaScript that** `outputs` `data to` **the** `console`. It's **commonly used for** `debugging` purposes **or for** `displaying` `information` **to the** `user` **in** `browser-based` `environments`.

---
</details>
<!-- end of 'console.log()' section -->



```javascript
let sum = 5 + 3;        // Addition: Adds two numbers
console.log(sum); // 8

let difference = 10 - 4; // Subtraction: Subtracts one number from another
console.log(difference); // 6

let product = 2 * 6;     // Multiplication: Multiplies two numbers
console.log(product); // 12

let quotient = 20 / 4;   // Division: Divides one number by another
console.log(quotient); // 5

let remainder = 15 % 4;  // Modulus: Returns the remainder of a division
console.log(remainder); // 3
```


## Assignment Operators
**Used to** `assign` `values to` `variables`.

```javascript
let x = 5;
x += 3; // Add and assign: Adds the value on the right to the variable and assigns the result back to the variable
console.log(x); // 8

let y = 10;
y -= 4; // Subtract and assign: Subtracts the value on the right from the variable and assigns the result back to the variable
console.log(y); // 6

let z = 2;
z *= 6; // Multiply and assign: Multiplies the variable by the value on the right and assigns the result back to the variable
console.log(z); // 12

let w = 20;
w /= 4; // Divide and assign: Divides the variable by the value on the right and assigns the result back to the variable
console.log(w); // 5

let m = 15;
m %= 4; // Modulus and assign: Calculates the remainder of division and assigns the result back to the variable
console.log(m); // 3
```


## Comparison Operators
**Used to** `compare` `two values` **and** `return` **a** `boolean result`.

```javascript
let a = 5;
let b = 10;

console.log(a == b);  // Equality: Checks if two values are equal
// false
console.log(a < b);   // Less than: Checks if one value is less than another
// true
console.log(a > b);   // Greater than: Checks if one value is greater than another
// false
console.log(a !== b); // Strict inequality: Checks if two values are not strictly equal
// true
```


## Logical Operators
**Used to** `combine` **or** `invert` `boolean values`.

```javascript
let p = true;
let q = false;

console.log(p && q); // Logical AND: Returns true if both operands are true
// false
console.log(p || q); // Logical OR: Returns true if at least one operand is true
// true
console.log(!p);     // Logical NOT: Returns the opposite of the operand's boolean value
// false
```


## Unary Operators
Operators **that take a** `single` `operand`.

```javascript
let num = 5;
console.log(-num);   // Unary negation: Negates a number
// -5
console.log(+num);   // Unary plus: Converts an operand into a number, with no effect here
// 5
num++;               // Increment: Increases the value of a variable by 1
console.log(num);    // 6
num--;               // Decrement: Decreases the value of a variable by 1
console.log(num);    // 4
```


## Conditional (Ternary) Operator
**A** `shorthand` **for** `if-else` `statements`.



<!-- start of 'shorthand' section -->
<details>
    <summary>Definition: shorthand</summary>

#
In general, a shorthand **refers to a** `quicker` **or** `more concise` `way` **of** `expressing` `something`. **In programming**, shorthand often **refers to syntax or techniques that allow you to achieve the same result with less code or typing effort**.

---
</details>
<!-- end of 'shorthand' section -->



<!-- start of 'concise' section -->
<details>
    <summary>Definition: concise</summary>

#
"Concise" **means** `expressing` `a lot` **of** `information` `clearly` **and** `effectively` `in` **a** `few words` **or a** `short space`.

---
</details>
<!-- end of 'concise' section -->



**Syntax**
```javascript
condition ? expression1 : expression2
```

**Example**
```javascript
let age = 20;
let status = (age >= 18) ? 'Adult' : 'Minor'; // If age is 18 or older, status is 'Adult', else 'Minor'
console.log(status); // Adult if age is 20
// Adult
```


## Bitwise Operators
Used to perform `bitwise` `operations` **on** `binary representations` **of** `numbers`.

```javascript
let c = 5; // Binary representation: 101
let d = 3; // Binary representation: 011

console.log(c & d);  // Bitwise AND: Performs a bitwise AND operation
// 1
console.log(c | d);  // Bitwise OR: Performs a bitwise OR operation
// 7
console.log(c ^ d);  // Bitwise XOR: Performs a bitwise XOR operation
// 6
console.log(~c);     // Bitwise NOT: Performs a bitwise NOT operation
// -6
```


## String Operators
**Used for** `string concatenation`.



<!-- start of 'concatenation' section -->
<details>
    <summary>Definition: concatenation</summary>

#
Concatenation **means** `putting things` `together`. **In programming**, it's **often used with strings**, where you join two or more strings **to make a longer one**.

---
</details>
<!-- end of 'concatenation' section -->



```javascript
let str1 = "Hello";
let str2 = " World!";
let result = str1 + str2; // Concatenation: Combines two strings together
console.log(result);
// Hello World!
```


## Type Operators
**Used to** `determine` **the** `type` **of an** `operand`.

```javascript
let obj = {};
console.log(typeof obj);            // typeof: Returns the data type of an operand
// object

function Car() {} // Define a function named Car. This function serves as a constructor for creating Car objects.
let myCar = new Car(); // Create a new instance of the Car object using the 'new' keyword and the Car constructor function.
console.log(myCar instanceof Car);  // instanceof: Checks if an object is an instance of a specific object type
// true
```