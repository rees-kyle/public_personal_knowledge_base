---
id: qjb3fxna5e4dhemwgtueowq
title: 1 - Declaration Vs Expression
desc: ''
updated: 1713018045372
created: 1713014254935
---

1. **Function Declaration:**
   - Function declarations `define` **a** `named` `function`.
   - They are `hoisted`, **meaning they are** `available` `throughout` `their` `scope`, `even` `before` **the actual** `declaration` `in` **the** `code`.



<!-- start of 'hoist' section -->
<details>
    <summary>Definition: hoist (in javascript)</summary>

#
Hoisting, **is a** `behavior` **where** `variable` **and** `function declarations` **are** `moved to` **the** `top` **of their** `containing scope` `during` `compilation`, **allowing them to be used before they're declared**.

---
</details>
<!-- end of 'hoist' section -->



<!-- start of 'scope' section -->
<details>
    <summary>Definition: scope (in javascript)</summary>

#
Scope **refers to** `where` `variables` **and** `functions` **can be** `accessed` **within code**. **Global scope means they're visible everywhere**, **while local scope restricts them to specific blocks or functions**. 

---
</details>
<!-- end of 'scope' section -->



```javascript
function add(a, b) {
    return a + b;

// Testing the function:
console.log(add(2, 3)); // Output: 5
}
```

2. **Function Expression:**
   - Function expressions `define` **a** `function` **as** `part of` **an** `expression`, `often` **by** `assigning` `it` `to` **a** `variable`.
   - They are `not` `hoisted`, so they **can** `only` **be** `called` `after` **they are** `defined`.

     ```javascript
     const add = function(a, b) {
         return a + b;

    // Testing the function:
    console.log(add(5, 7)); // Output: 12
     };
     ```

These are the `main ways` **to** `define functions` **in JavaScript**. Each has its own use cases, and the `choice` `between them` **often** `depends on` **factors like** `readability` **and** `hoisting behavior`.