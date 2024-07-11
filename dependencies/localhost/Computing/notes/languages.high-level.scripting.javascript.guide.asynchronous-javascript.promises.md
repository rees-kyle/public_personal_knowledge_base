---
id: fogeozkfnklsusyryzlpbhw
title: 2 - Promises
desc: ''
updated: 1720723269969
created: 1713657768320
---

Promises **are a core part of handling asynchronous operations in JavaScript**, `providing` **a** `cleaner`, `more manageable` `approach to` `handling` `asynchronous code` **than older techniques such as callbacks**.

A Promise in JavaScript **is an** `object` **that** `represents` **the** `eventual completion` `or` `failure of` **an** `asynchronous operation`. It **acts as a** `placeholder for` **a** `value` `that is` **initially** `unknown`, **usually because the computation of its value is yet to be completed**.

## States of a Promise

A `Promise` `can be` `in` `one` `of three` `states`:
1. **Pending**: The initial state of a Promise. The operation has `not` `completed` yet.
2. **Fulfilled**: The state of a Promise representing a `successful` `operation`. **This state means that the** `promised value` **is** `available`.
3. **Rejected**: This state means that the `operation` `failed`, **and the** `Promise` **is** `holding` **an** `error value`.

## Creating a Promise

**A Promise is** `created` `using` **the** `Promise constructor` `which` `takes` **an** `executor function`. **This function is** `executed` `immediately` **by the Promise implementation**, **and it** `receives` `two` `functions` `as` `arguments`: `resolve` **and** `reject`.



<!-- start of 'constructor' section -->
<details>
    <summary>Definition: constructor (in programming)</summary>

#
A constructor **is a** `special` `function` **in programming that's** `used to` `create` **and** `set up` `new objects`. **It** `initializes` **the** `object's` `properties` `when` **the** `object` **is** `created`.

---
</details>
<!-- end of 'constructor' section -->



<!-- start of 'initialize' section -->
<details>
    <summary>Definition: initialize</summary>

#
The word "initialize" **means to** `set up` **or** `prepare` `something` **so it's** `ready` `to be` `used`. This **could involve setting starting values**, **configuring settings**, **or doing other preparatory tasks before using an** `object`, `device`, **or** `system`.

---
</details>
<!-- end of 'initialize' section -->



<!-- start of 'preparatory' section -->
<details>
    <summary>Definition: preparatory</summary>

#
The word "preparatory" **refers to** `actions` **or** `steps taken` `to get` `ready` `for something else` **that's** `coming up`. **It's about** `preparing` **or** `setting things up` `in advance`.

---
</details>
<!-- end of 'preparatory' section -->



```javascript
const myPromise = new Promise((resolve, reject) => {
    // Asynchronous operation here
    const success = true; // Simulate a condition
    if (success) {
        resolve("Operation was successful");
    } else {
        reject("Operation failed");
    }
});
```

## Consuming a Promise

To use a Promise, you consume it `by registering` `callbacks` **using** `.then()`, `.catch()`, **and** `.finally()` **methods**.

- **`.then()`** — This method **is used to** `schedule` **a** `callback` `to be` `executed` `when` **the** `Promise` **is** `fulfilled`. You `can` **also** `chain` **.then() methods** `to perform` `additional` `asynchronous operations` `sequentially`.



<!-- start of 'sequentially' section -->
<details>
    <summary>Definition: sequentially</summary>

#
The word "sequentially" **means** `doing` `things` `in` **a** `specific` `order`, **one after another**. For **example**, **following steps in a guide from start to finish** `without` `skipping` **any**.

---
</details>
<!-- end of 'sequentially' section -->



```javascript
myPromise
    .then(result => {
        console.log(result);  // Output: Operation was successful
        return result + " with more data";
    })
    .then(newResult => {
        console.log(newResult); // Output: Operation was successful with more data
    });
```

- **`.catch()`** — This method **is used to** `schedule` **a** `callback` `to be` `executed` `when` **the** `Promise` **is** `rejected`.

```javascript
myPromise
    .catch(error => {
        console.error(error);
    });
```

- **`.finally()`** — **This method** `schedules` **a** `callback` `to be` `executed` `when` **the** `Promise` **is** `settled`, **regardless of its outcome**. It’s **useful** `for cleaning up` `resources` **or** `logging`.

```javascript
myPromise
    .finally(() => {
        console.log('This is called regardless of the outcome');
    });
```

## Promises and Error Handling

Proper error handling in Promises **is** `crucial`. `Errors` `in` **the** `executor function` (**in the code within the new Promise**) `should be` `caught` **and** `handled` `to avoid` `uncaught` `promise rejections`.



<!-- start of 'proper' section -->
<details>
    <summary>Definition: proper</summary>

#
"Proper" **means** `suitable`, `correct`, **or** `done` `the right way` **for a** `particular` `situation`.

---
</details>
<!-- end of 'proper' section -->



<!-- start of 'uncaught' section -->
<details>
    <summary>Definition: uncaught</summary>

#
In programming, "uncaught" **specifically refers to** `errors` **or** `exceptions` `that occur` `but` **are** `not` `handled by` **the** `program`. These uncaught errors **can cause the program to stop unexpectedly or behave in an unintended way because there is no code to manage these issues when they arise**.

---
</details>
<!-- end of 'uncaught' section -->



```javascript
new Promise((resolve, reject) => {
    try {
        throw new Error('Something went wrong');
        resolve('Success');
    } catch (error) {
        reject(error);
    }
})
.catch(error => {
    console.error(error.message);  // Output: Something went wrong
});
```

## Benefits of Using Promises

1. **Chainability**: Allows you to `chain` `multiple` `asynchronous operations` **easily**.
2. **Error Handling**: `Centralizes` **error handling using** `.catch()`.
3. **Synchronization**: `Facilitates` `handling` `multiple` `asynchronous operations` `together` **using methods like** `Promise.all()`.



<!-- start of 'facilitates' section -->
<details>
    <summary>Definition: facilitates</summary>

#
The word "facilitates" **means to** `make` `something` `easier` **or** `less difficult`. It **involves** `providing` `support` **or** `simplifying` **a** `process` `to help` **someone** `achieve` **a** `goal` **or** `complete` **a** `task` `more efficiently`.

---
</details>
<!-- end of 'facilitates' section -->



Promises are **a foundational element in modern JavaScript asynchronous programming**, **helping manage complex asynchronous flows more effectively**. With **ES2017 and later**, **'async/await' syntax builds on Promises**, **offering an even cleaner syntax for working with asynchronous code**.