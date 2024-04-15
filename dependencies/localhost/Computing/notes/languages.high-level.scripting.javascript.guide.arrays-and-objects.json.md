---
id: 3g9o0mtk64sfgybokaprk55
title: 3 - JavaScript Object Notation
desc: ''
updated: 1713201723642
created: 1713200491712
---

JSON (JavaScript Object Notation) **is a** `lightweight` `data interchange` `format` **that is** `easy for` `humans to` `read` `and` `write`, **and** `easy for` `machines to` `parse` `and` `generate`. In JavaScript, JSON **is a** `built-in` `object` **that provides** `methods for` `parsing` `JSON strings` `and` `converting` `JavaScript values to` `JSON strings`.



<!-- start of 'parse' section -->
<details>
    <summary>Definition: parse</summary>

#
To "parse" **means to** `analyze` **and** `understand` `data`.

---
</details>
<!-- end of 'parse' section -->



<!-- start of 'analyze' section -->
<details>
    <summary>Definition: analyze</summary>

#
To "analyze" **means to** `carefully` `look at` `something to` `understand it` `better`.

---
</details>
<!-- end of 'analyze' section -->



Here's how you can work with JSON in JavaScript:

1. **Parsing JSON**: You **can use the** `JSON.parse()` **method** `to parse` **a** `JSON string` **and** `convert` **it** `into` **a** `JavaScript object`.

    ```javascript
    let jsonString = '{"name": "John", "age": 30}';
    let jsonObject = JSON.parse(jsonString);
    console.log(jsonObject.name); // Output: John
    console.log(jsonObject.age); // Output: 30
    ```

2. **Converting to JSON**: You **can use the** `JSON.stringify()` **method** `to convert` **a** `JavaScript object` `into` **a** `JSON string`.

    ```javascript
    let person = { name: "John", age: 30 };
    let jsonString = JSON.stringify(person);
    console.log(jsonString); // Output: {"name":"John","age":30}
    ```

`JSON` `supports` `various data types` **including** `objects`, `arrays`, `strings`, `numbers`, `booleans`, **and** `null`. It's **commonly used** `for` `exchanging data` `between` **a** `web server` **and a** `web client`, **as well as for** `configuration files` **and** `storing data` `locally` `in` `web applications`.

When working with JSON, it's `important` **to note** that **JSON** `syntax` `is` **a** `subset of` `JavaScript object literal notation`, **meaning that** `any valid` `JSON` `is` **also** `valid` `JavaScript object literal` **syntax**. However, the `reverse` **is** `not always` `true`, **as** `JSON` **has some** `restrictions` **such as** `not allowing` `functions` **or** `undefined values`.