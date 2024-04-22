---
id: zu0lxqmqydi9b7ixbfq4cm3
title: 3 - Async and Await
desc: ''
updated: 1713806421678
created: 1713726706019
---

One of the most powerful and modern ways to handle asynchronous code in JavaScript is through async/await, which is `built` `on` **top of** `promises`.

## Understanding Async/Await

`Introduced` **in** `ES2017`, async/await `provides` **a** `cleaner`, `more readable` `syntax for` **working with** `asynchronous operations` **compared to callbacks and promises**. Here’s a quick rundown on how they work:

- **Async Function**: An async function **is declared with the async keyword**. It **allows the** `function` **to implicitly** `return` **a** `promise`, **which** `resolves` with `whatever` **the** `function` `returns`, `or` `rejects` with whatever the function throws.

- **Await Keyword**: `Within` **an** `async function`, you **can use the 'await'** `keyword` `before` **a** `promise`. The **await keyword** `pauses` **the** `execution of` **the** `async function` `until` **the** `promise` `resolves`, `after` which it `returns` **the** `resolved value`.



<!-- start of 'until' section -->
<details>
    <summary>Definition: until</summary>

#
"Until" **is used to show when** `something will` `continue` `to happen` **or** `be true`, `stopping at` **a** `specific time` **or** `event`. For example, "You need to wait here until I come back" means you keep waiting here and stop when I return.

---
</details>
<!-- end of 'until' section -->



## Basic Syntax

```javascript
// Define an asynchronous function named fetchData
async function fetchData() {
  try {
    // Attempt to fetch data from the API endpoint
    const response = await fetch('https://api.example.com/data');
    // Await the resolution of the fetch call and then convert the response to JSON
    const data = await response.json();
    // Return the JSON data if fetch and conversion are successful
    return data;
  } catch (error) { // Catch any errors that occur during the fetch or conversion process
    // Log the error to the console for debugging purposes
    console.error('Error fetching data:', error);
  }
}
```

In this **example**, **fetchData is an async function**. Inside this function, **we wait for fetch to complete by prefixing it with** `await`. **This** `tells` `JavaScript` `to pause at` **this** `line` `until` **the** `promise resolves`. **If the fetch is successful, the function continues to the next line**, **again using 'await' to convert the response into JSON**.

## Error Handling

Error handling in async/await is straightforward **using** `try`/`catch` `blocks`, **as shown in the example above**. The `try` **block** `executes` **the** `await` **statements**, **and** `if` **any of the** `promises` `get rejected`, **the** `catch` **block** `catches` **these** `rejections`.

## Chaining Async Operations

One of the advantages of async/await is the way it handles asynchronous sequences. **This can make your code look almost synchronous**, **improving readability and maintainability**.



<!-- start of 'synchronous' section -->
<details>
    <summary>Definition: synchronous (in computing)</summary>

#
**In computing**, **synchronous means that** `operations` `happen` `one after` `another`. **Each operation must be completed before the next one starts**, **causing the program to wait until the task is finished before moving on to the next task**.

---
</details>
<!-- end of 'synchronous' section -->



```javascript
// Define an asynchronous function named processUsers
async function processUsers() {

  
  const users = await fetchData('https://api.example.com/users');
  // Await the fetchData function call to retrieve users from the API endpoint
  // The 'await' ensures that the function waits here until the promise resolves with the data
  

  const profile = await fetchData(`https://api.example.com/users/${users[0].id}`);
  // Fetch data for the first user's profile using the ID from the first user in the list
  // This assumes that 'users' is an array and users[0] is the first user object
  // The fetchData function is called again, this time with the URL dynamically constructed to include the first user's ID
  
  return profile;
  // Return the profile data of the first user. This profile is the resolved value of the promise returned by processUsers when it is called
}
```

**In this example**, **processUsers fetches a list of users**, then immediately **fetches the profile of the first user**, **demonstrating how** `multiple` `asynchronous requests` `can be` `chained linearly` `without` `nesting`.

## Mixing Promises and Async/Await

While async/await is powerful, sometimes you might want to **use** `plain promises` **for** `simple cases` `or` **when performing** `multiple` `operations` **that can run** `concurrently`.



<!-- start of 'concurrently' section -->
<details>
    <summary>Definition: concurrently</summary>

#
**Concurrently means** `things` `happening` `at` **the** `same time`. **In computing**, it **refers to multiple tasks or processes running simultaneously or in an overlapping manner to increase efficiency**.

---
</details>
<!-- end of 'concurrently' section -->



```javascript
// Define an asynchronous function named fetchMultipleResources
async function fetchMultipleResources() {
  
  // Use Promise.all to fetch both resources concurrently
  const [resource1, resource2] = await Promise.all([
  // Promise.all takes an array of Promises and returns a single Promise that resolves when all of the input Promises have resolved
    fetch('https://api.example.com/resource1'), // Fetch the first resource from the API
    fetch('https://api.example.com/resource2')  // Fetch the second resource from the API
  ]);

  // After both fetch calls resolve, convert the first fetched resource to JSON
  const data1 = await resource1.json();
  // Await the resolution of calling .json() on resource1, which is a Promise that resolves with the parsed JSON
  
  // Convert the second fetched resource to JSON in the same way
  const data2 = await resource2.json();

  // Return an array containing the data from both resources
  return [data1, data2];
  // This array is what the function ultimately provides when the returned Promise resolves
}
```

Here, `Promise.all` **is used to** `concurrently fetch` `multiple resources`, **and we** `await` **its** `resolution`. **This approach is** `more efficient` **than awaiting each fetch call sequentially**.

## Conclusion

`Async`/`await` **syntax** `simplifies` **writing** `asynchronous JavaScript`, **making your asynchronous code** `easier to` `write`, `read`, **and** `debug`. It’s a **powerful tool** in modern JavaScript development, **especially when combined with other features** of the language **like promises and modules**.