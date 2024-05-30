---
id: m3k2sz6l6p8zwvgsi2w4qz5
title: 1 - Local Storage
desc: ''
updated: 1717091612827
created: 1714433489398
---

The Local Storage API is a `part of` the `Web Storage API`, which `enables` `web applications to` `store data` `locally` `within` **the** `user's browser`. The data stored using Local Storage is `saved across` `browser sessions`. This means that the `data persists` **even** `after` **the** `browser window is` `closed and reopened`, **unlike data stored using Session Storage**, **which persists only for the duration of the page session**.

**Local Storage provides a simple** `key-value` `store mechanism` **and is generally** `used to` `store` `non-sensitive data` (**since it is accessible by any script on the domain and is not encrypted**). Here are some key aspects of Local Storage:



<!-- start of 'domain' section -->
<details>
    <summary>Definition: domain (in computing)</summary>

#
**In computing**, **a domain can refer to a** `specific area of` `control or` `ownership on` **the** `internet`, `identified by` **a** `unique` `domain name`, such as "**example.com**". This name `serves as` **an** `address` **where the domain's associated website can be accessed**.

---
</details>
<!-- end of 'domain' section -->



<!-- start of 'key-value' section -->
<details>
    <summary>Definition: key-value</summary>

#
Key-value **refers to a** `method of` `storing` **and** `organizing` `data` **where** `each item` (`value`) **is** `associated with` **a** `unique identifier` (`key`). **This allows for efficient retrieval of data by using the key**.

---
</details>
<!-- end of 'key-value' section -->



<!-- start of 'mechanism' section -->
<details>
    <summary>Definition: mechanism</summary>

#
A mechanism **is a** `system of` `parts` `working together in` **a** `machine to` `perform` **a specific** `function`. It **usually involves moving components that transfer or transform motion or force to achieve a desired outcome**.

---
</details>
<!-- end of 'mechanism' section -->



### Key Features of Local Storage
- **Persistence**: Data stored in Local Storage is persistent `until` **explicitly** `deleted`. `Changes` **made** `are saved` **and** `available for` `all` `current and future` `visits` **to the site**.



<!-- start of 'persistence' section -->
<details>
    <summary>Definition: persistence</summary>

#
Persistence **refers to the** `ability of` `data to` `remain available` `and unchanged` `over time`, `even after` **the** `program` **that created it** `has ended or` **the** `device` **that holds it has been** `powered off`.

---
</details>
<!-- end of 'persistence' section -->



- **Domain-Specific**: `Data stored` in Local Storage `is specific to` **the** `protocol of` **the** `page`. It is `accessible only` `by pages` `from` **the** `same domain` **that set the data**.
- **Storage Limit**: **Typically**, the `limit is` **about** `5MB` `per domain`, but this `can vary` **between different browsers**.
- **Synchronous API**: Local Storage operations are synchronous, **meaning they** `can potentially` `block` **the** `main thread if` `dealing with` `large` **amounts of** `data`.

### How to Use Local Storage
#### Setting Items
`To store` `data` in Local Storage, **you can use** the `setItem()` method. **It takes** `two` `arguments`: **the** `key` **and** the `value`. Note that both the key and the value **need to be** `strings`.

```javascript
// Use 'setItem' method to store a value
localStorage.setItem('username', 'JohnDoe'); // 'username' is the key and 'JohnDoe' is the value
```

#### Getting Items
`To retrieve` `data` from Local Storage, you can **use the** `getItem()` **method** `with` **the** `key of` **the** `data` **you want to retrieve**.

```javascript
// Use 'getItem' method to retrieve a value
// Requires one argument; the key for which to retrieve the value
const username = localStorage.getItem('username'); // 'username' is the key

// Log the retrieved value to the console
console.log(username); // Output: JohnDoe
// If 'username' is not found, it will output 'null'
```

#### Removing Items
`To delete` **an** `item` from Local Storage, **use the** `removeItem()` **method** `with` **the** `key of` **the** `item` **you want to delete**.

```javascript
// Use 'removeItem' method to delete a specific item
// Requires one argument; the key of the item to remove
localStorage.removeItem('username'); // 'username' is the key
```

#### Clearing All Data
`To remove` `all data` stored in Local Storage for a domain, you can **use the** `clear()` **method**.

```javascript
// Use 'clear' method to remove all items stored under the current domain
localStorage.clear();
```

#### Checking Storage Length
You can `find out` `how many` `key/value pairs` **are** `in` **the** `Local Storage` **by** `using` **the** `length` **property**.

```javascript
// Use 'length' property to return the number of key/value pairs currently stored
const numberOfItems = localStorage.length;

// Log the number of items to the console
console.log(numberOfItems);
```

#### Looping Through Keys
You can `loop through` `all` **the** `keys` in Local Storage `using` **a** `for` **loop**:

```javascript
// Start a (for)loop that runs from 0 to the number of items in Local Storage
for (let i = 0; i < localStorage.length; i++) {
    // Retrieve the key for each item at the index 'i'
    const key = localStorage.key(i);
    // Use the retrieved key to get the corresponding value
    const value = localStorage.getItem(key);

    // Log the key-value pair to the console, showing both the key and the value
    console.log(`${key}: ${value}`);
    // Used for debugging, ensuring that the correct data is stored and can be retrieved as expected
}
```

### Use Cases
- `Saving` `user preferences or` `settings` locally.
- `Storing information` **needed across sessions**, **such as the** `user's` `last activity or` `state of` **the** `application`.
- `Caching data` locally `to reduce` `network requests`.

### Limitations and Considerations
- Local Storage is `not` `suitable for` `storing` `sensitive information` **as it is** `easily` `accessible through` **the** `browser's` `developer tools`.
- The `synchronous nature` of Local Storage means it `could affect` **the** `performance of` **your web** `applications` **if large amounts of data are read or written**.
- `Data` in Local Storage `is limited` `in size` **and** `larger` `data needs` **should** `consider` `IndexedDB or` `server-side` `storage` **solutions**.

**Local Storage is widely** `supported in` `modern browsers` **and is a powerful tool for** `enhancing` `user experience` `by keeping` `necessary data` `close` at hand `without` **the** `need for` `constant` `server queries`.