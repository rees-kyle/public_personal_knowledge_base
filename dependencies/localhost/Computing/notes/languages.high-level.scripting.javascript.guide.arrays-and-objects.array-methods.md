---
id: 0ugl27miyr9p7o2xutrers1
title: 1 - Array Methods
desc: ''
updated: 1713197563617
created: 1713186227829
---

Array methods in JavaScript are versatile **for both** `modifying` **and** `looping through` `arrays`. Here's a brief overview of some commonly used array methods:

1. **forEach()**: `Executes` **a provided** `function` `once` `for each` `array element`.

   ```javascript
   const array = [1, 2, 3, 4];
   array.forEach((element) => {
       console.log(element);
   });
   ```

2. **map()**: `Creates` **a** `new array` `with` **the** `results of` `calling` **a provided** `function` `on` `every element` `in` **the** `calling array`.

   ```javascript
   const array = [1, 2, 3, 4];
   const mappedArray = array.map((element) => {
       return element * 2;
   });
   ```

3. **filter()**: `Creates` **a** `new array` `with` `all elements` `that pass` `the test` `implemented by` **the provided** `function`.

   ```javascript
   const array = [1, 2, 3, 4];
   const filteredArray = array.filter((element) => {
       return element > 2;
   });
   ```

4. **reduce()**: `Applies` **a** `function` `against` **an** `accumulator` `and` `each element` `in` **the** `array` (**from left to right**) `to reduce it` `to a` `single value`.

   ```javascript
   const array = [1, 2, 3, 4];
   const sum = array.reduce((accumulator, currentValue) => {
       return accumulator + currentValue;
   }, 0);
   ```

5. **find()**: `Returns` **the** `value of` **the** `first element` `in` the `array` `that satisfies` **the provided** `testing function`.

   ```javascript
   const array = [1, 2, 3, 4];
   const foundElement = array.find((element) => {
       return element > 2;
   });
   ```

6. **some()**: `Checks if` `at least` `one element` `in` **the** `array` `passes` **the** `test` `implemented by` **the provided** `function`.

   ```javascript
   const array = [1, 2, 3, 4];
   const hasGreaterThanTwo = array.some((element) => {
       return element > 2;
   });
   ```

7. **every()**: `Checks if` `all elements` `in` **the** `array` `pass` **the** `test` **implemented by the provided function**.

   ```javascript
   const array = [1, 2, 3, 4];
   const allGreaterThanZero = array.every((element) => {
       return element > 0;
   });
   ```

These methods are quite **versatile and can greatly simplify array manipulation tasks** in JavaScript.