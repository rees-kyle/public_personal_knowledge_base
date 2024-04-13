---
id: vqpclzkjm5fvqctit9z4ak9
title: Parameters and Arguments
desc: ''
updated: 1713037747903
created: 1713018348690
---

In JavaScript, parameters and arguments are `fundamental concepts` `related to` `functions`.

**Parameters**:
- Parameters **are the** `variables` `listed` `inside` **the** `parentheses` **of a function definition**.
- **They act as** `placeholders for` `values` **that will be** `passed to` **the** `function` `when` **it is** `called`.
- Parameters **are used to** `define` **the** `inputs` **a** `function` `expects to` `receive`.
- They **are** `local variables` `to the` `function`, **meaning they are** `only accessible` `within` **the** `function's scope`.

```javascript
function greet(name) {
    console.log("Hello, " + name + "!");
}
```
**In the** `greet function`, `name` `is` **a** `parameter`.

**Arguments**:
- Arguments **are the actual** `values` **that are** `passed to` **a** `function` `when` **it is** `invoked` (`called`).



<!-- start of 'invoke' section -->
<details>
    <summary>Definition: invoke</summary>

#
To "invoke" **means to** `call upon` `something`, **like a** `rule` **or a** `power`, **often formally**. It **can also mean to** `use` **or** `activate` `something`, **like invoking a** `function` **in** `programming`.

---
</details>
<!-- end of 'invoke' section -->



<!-- start of 'upon' section -->
<details>
    <summary>Definition: upon</summary>

#
"Upon" **typically means** "`on`" **or** "`about`."

---
</details>
<!-- end of 'upon' section -->



- **They** `correspond to` **the** `parameters` `defined in` **the** `function declaration`.



<!-- start of 'correspond' section -->
<details>
    <summary>Definition: correspond</summary>

#
"Correspond" **means to** `match` **or** `be similar to` `something`, **or to** `exchange messages` `with` `someone`. **In programming**, **"correspond" usually means to match or be associated with something**, **like matching data types or variables**.

---
</details>
<!-- end of 'correspond' section -->



- Functions **can be** `called` `with` `any number` `of arguments`, `including none`.

```javascript
greet("John");
```
In this `call` **to** `greet`, `"John"` **is the** `argument`.



<!-- start of 'call' section -->
<details>
    <summary>Definition: call (in programming)</summary>

#
**In programming**, **"calling" means** `using` **a** `function` `in` **your** `code`. **It's like** `giving` **a** `command to` `run` **a specific** `set of` `instructions`.

---
</details>
<!-- end of 'call' section -->



**Parameter vs. Argument**:
- `Parameters` **are** `variables` `in` **the** `function definition`.
- `Arguments` **are the actual** `values` `passed to` **the** `function` `when` **it is** `called`.

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(5, 3)); // Here, 5 and 3 are arguments passed to the function add.
```

**In summary**, `parameters` **are** `used` `in` `function declarations` **to** `define` **the** `inputs` `a function expects`, **while** `arguments` **are the** `values` `passed to` **a** `function` `when` **it is** `called`.