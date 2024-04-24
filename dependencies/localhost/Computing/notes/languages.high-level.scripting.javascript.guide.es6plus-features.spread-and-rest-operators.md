---
id: 2r6rnfmvonps1z1gv6k98kt
title: 3 - Spread and Rest Operators
desc: ''
updated: 1713996015529
created: 1713932889782
---

ES6 (ECMAScript 2015) introduced several new features to JavaScript, enhancing the language's capabilities and making it more versatile and efficient for developers. Two notable features from this version are the spread and rest operators, which are used extensively in modern JavaScript development. **Both operators look similar**, as they are represented by three dots (`...`), **but they serve different purposes depending on how they are used in the code**. Below, I will explain both features with examples:

## Spread Operator (`...`)

The spread operator **allows an** `iterable` **such as an** `array` **or a** `string` `to be` `expanded` **in places** `where` `zero` `or` `more arguments` (**for function calls**) **or** `elements` (**for array literals**) **are** `expected`, `or` **an** `object expression` `to be` `expanded` **in places** `where` `zero` `or` `more key-value pairs` (**for object literals**) **are** `expected`.



<!-- start of 'iterable' section -->
<details>
    <summary>Definition: iterable</summary>

#
An iterable **is an** `object that` **you** `can` `loop over`, **like a** `list` **or a** `string`. **It lets you** `go through` `each element` `one by one`.

---
</details>
<!-- end of 'iterable' section -->



### Examples

- `Combining` `arrays`:
   ```javascript
   const first = [1, 2, 3]; // Declare an array
   const second = [4, 5, 6]; // Declare a second array

   // Use the spread operator to combine both arrays into a new array called 'combined'
   const combined = [...first, ...second]; // The spread operator (...) expands both arrays into individual elements
   // The order they appear will be the order they will merge
   
   // As shown in the output
   console.log(combined); // Output: [1, 2, 3, 4, 5, 6]
   ```

- `Copying` **an** `array`:
   ```javascript
   const original = [1, 2, 3]; // Declare an array

   // Use the spread operator to create a shallow copy of the 'original' array
   const copy = [...original]; // The spread operator (...) expands the elements of 'original' into a new array 'copy'
   // 'copy' will have the same elements as 'original', but is a separate array object
   
   // Output the copied array to the console
   console.log(copy); // Output: [1, 2, 3]
   ```



<!-- start of 'shallow copy' section -->
<details>
    <summary>Definition: shallow copy</summary>

#
**A** `shallow copy of` **an** `object` `creates` **a** `new object` `but` `does not` `create copies of` **any** `objects` `contained within` **the** `original`. `Instead`, it just `copies` ***the** `references to` **those** `inner objects`. This means **if you change one of the inner objects in the original**, **that change will also appear in the shallow copy** because both the original and the copy point to the same inner object.

---
</details>
<!-- end of 'shallow copy' section -->



- `Expanding` **a** `string` `into` **an** `array` **of characters**:
   ```javascript
   // Declare a string variable
   const greeting = 'Hello';

   const chars = [...greeting]; // Use the spread operator
   // Each character in the string becomes an element in the new array 'chars'

   // Output the array to the console
   console.log(chars); // Output: ['H', 'e', 'l', 'l', 'o']
   ```

- **Using with** `objects` (`ES2018` **feature**):
   ```javascript
   // Define the first object with two properties
   const obj1 = { foo: 'bar', x: 42 };

   // Define the second object, the 'foo' property overlaps with the first object
   const obj2 = { foo: 'baz', y: 13 };

   // Use the spread operator to merge obj1 and obj2 into a new object
   const mergedObj = {...obj1, ...obj2};
   // Properties from obj2 will overwrite properties from obj1 if they have the same key

   // Output the merged object to the console
   console.log(mergedObj); // Output: { foo: 'baz', x: 42, y: 13 }
   // The foo' property is overwritten by the last provided value 'baz'
   ```

## Rest Operator (`...`)

The rest operator **allows us to** `represent` **an** `indefinite number of` `arguments as` **an** `array`. This is **particularly useful in** `function definitions`, **where the** `exact number of` `arguments` **is** `not known` **beforehand** `or` **where** `multiple arguments` **need to be** `handled as` **a** `group`.

### Examples

- `Collecting` `function arguments into` **an** `array`:
   ```javascript
   // Define a function
   function sum(...nums) {
   // The rest operator is used to gather all individual arguments passed to the function into an array named 'nums'

     // Use the 'reduce' method to sum up all elements in the 'nums' array
     return nums.reduce((a, b) => a + b, 0);
     // 'reduce' takes a callback function that processes each element (a, b) to produce a single output, starting from an initial value of 0

   }
   
   // Call the 'sum' function with five numbers as arguments
   console.log(sum(1, 2, 3, 4, 5)); // Output: 15
   // The function calculates the sum of all the provided numbers
   ```

- `Destructuring` `arrays` with rest:
   ```javascript
   // Define an array 'numbers'
   const numbers = [1, 2, 3, 4, 5];

   // Use destructuring to assign the first two elements of the array to variables
   const [first, second, ...rest] = numbers;
   // The rest operator '...' is used to gather the remaining elements into an array named 'rest'

   // Output the values of 'first' and 'second' to the console
   console.log(first, second); // Output: 1, 2
   // This shows the first two extracted elements from the array

   // Output the 'rest' array, which contains the remaining elements of the original array
   console.log(rest); // Output: [3, 4, 5]
   // This illustrates that 'rest' has captured elements 3, 4, and 5
   ```



<!-- start of 'extract' section -->
<details>
    <summary>Definition: extract</summary>

#
To "extract" **means to** `take out` **a** `specific part of` `something` `from` `where it is` `originally located` **or** `stored`. This could be **physically removing something**, like **taking seeds out of an apple**, **or digitally**, like **pulling specific information from a computer file**.

---
</details>
<!-- end of 'extract' section -->



- `Passing` **the** `rest of` **the** `properties to` **a** `function`:
   ```javascript
   // Define an object
   const person = { name: 'John', age: 28, job: 'Engineer' };

   // Use object destructuring to extract the 'name' property into a variable 'name'
   const { name, ...restProps } = person;
   // Use the rest operator to gather all remaining properties into a new object 'restProps'

   // Output the extracted 'name' property to the console
   console.log(name); // Output: John
   // This demonstrates accessing a single property directly

   // Output the 'restProps' object, which contains the remaining properties
   console.log(restProps); // Output: { age: 28, job: 'Engineer' }
   ```



<!-- start of 'demonstrate' section -->
<details>
    <summary>Definition: demonstrate</summary>

#
To "demonstrate" **means to** `show` `how` `something` `works` **or to** `explain` **it** `with` `examples` **so that** `others` **can** `understand` **it** `clearly`.

---
</details>
<!-- end of 'demonstrate' section -->



## Conclusion

Both the `spread` `and` `rest operators` **are powerful** additions to JavaScript that `simplify` `handling` `multiple parameters` `in functions` `and` `merging`, `copying`, `or` `expanding arrays` `and` `objects`. While they `share` **the** `same syntax`, **their usage and purpose differ significantly**, marking a substantial improvement in how developers **can write concise and expressive code**.