---
id: rq68qz7y3mzg2pep0390c30
title: 4 - Arrow Functions
desc: ''
updated: 1713185825829
created: 1713101129397
---

Arrow functions are a `concise way` **to** `write` `anonymous` `functions` **in JavaScript**. They were **introduced in ECMAScript 6** (`ES6`) **and** `provide` **a** `more compact` `syntax` **compared to traditional function expressions**.

Here's a basic `syntax comparison` **between traditional functions and arrow functions**:

**Traditional** function expression:
```javascript
let add = function(a, b) {
  return a + b;
};
```

**Arrow** function expression:
```javascript
let add = (a, b) => {
  return a + b;
};
```

**Or for** `single-line` `functions`, **you can** `omit` **the** `curly braces` **and the** "`return`" **keyword**, and **the expression will be implicitly returned**:

```javascript
let add = (a, b) => a + b;
```

**Arrow functions** have a few `key differences` compared to traditional functions:

1. **Lexical "this" binding**: In arrow functions, "`this`" **is** `lexically bound`, **meaning it** `inherits` **the** "`this`" `value of` **the** `enclosing scope`. **Traditional functions**, on the other hand, **have their own "this" context**, **which can change based on how they are called**.



<!-- start of 'lexical' section -->
<details>
    <summary>Definition: lexical</summary>

#
"Lexical" just **means** `anything` `to do` `with` `words` **or** `vocabulary`. So, when we talk about lexical analysis, we're basically looking at the structure of words to understand their meaning.

---
</details>
<!-- end of 'lexical' section -->



<!-- start of 'inherit' section -->
<details>
    <summary>Definition: inherit</summary>

#
When you inherit something, **it means** `you` `get it` `from` `someone else`, **like money from a relative or traits from your parents**.

---
</details>
<!-- end of 'inherit' section -->



> What is Lexical Scope in JavaScript https://www.youtube.com/watch?v=oeVbY9O6r3g

2. **No "arguments" object**: **Arrow functions** `do not` `have` **their** `own` "`arguments`" `object`. **Instead**, **they** `inherit` **the** "`arguments`" `object` `from` **the** `containing scope`.

3. **No "new" keyword**: **Arrow functions** `cannot` `be used as` `constructors`. Attempting to instantiate an arrow function with the "new" keyword **will result in a TypeError**.

4. **No "prototype" property**: Since arrow functions cannot be used as constructors, they also `do not` `have` **a** "`prototype`" `property`.

Arrow functions are particularly `useful` `for` `short`, `concise` `function expressions`, **such as** `callbacks` **or when you need to** `maintain` **the** `lexical scope of` "`this`". However, it's **essential to** `be aware of` **their** `differences` **compared to traditional functions**, **especially regarding "this" behavior**, `to avoid` `unexpected bugs`.