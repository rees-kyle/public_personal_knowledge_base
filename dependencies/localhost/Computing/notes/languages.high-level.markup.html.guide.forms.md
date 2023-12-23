---
id: blkhx8whe69jkjagn4bg3qe
title: 7 - Forms
desc: ''
updated: 1703370418421
created: 1703366291296
---

Forms are used to `collect user input`, such as `text`, `selections`, **and** `buttons`. Here's a basic example of an HTML form:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Form Example</title>
</head>
<body>

    <h2>Sample Form</h2>

    <form action="/submit" method="post">
        <!-- Text Input -->
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>

        <!-- Password Input -->
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required>

        <!-- Radio Buttons -->
        <p>Gender:</p>
        <label for="male">Male</label>
        <input type="radio" id="male" name="gender" value="male">
        <label for="female">Female</label>
        <input type="radio" id="female" name="gender" value="female">

        <!-- Checkbox -->
        <p>Hobbies:</p>
        <label for="reading">Reading</label>
        <input type="checkbox" id="reading" name="hobbies" value="reading">
        <label for="traveling">Traveling</label>
        <input type="checkbox" id="traveling" name="hobbies" value="traveling">

        <!-- Select Dropdown -->
        <p>Country:</p>
        <select name="country">
            <option value="usa">United States</option>
            <option value="canada">Canada</option>
            <option value="uk">United Kingdom</option>
        </select>

        <!-- Textarea -->
        <p>Comments:</p>
        <textarea id="comments" name="comments" rows="4" cols="50"></textarea>

        <!-- Submit Button -->
        <button type="submit">Submit</button>
    </form>

</body>
</html>
```


## Breakdown

### `<form>`
This **element** `contains` various `form elements`.

### `action`
This **attribute** `specifies where` the `form data` **is** `sent` **when** the `user submits` the `form`. In this case, it's set to "`/submit`" (a `placeholder` URL).

### `method`
This **attribute** `specifies` the `HTTP method` to be **used when** `sending form data`. **Common values** are "`get`" and "`post`."



<!-- start of 'HTTP' section -->
<details>
    <summary>Definition: HTTP</summary>

#
HTTP stands for `Hypertext Transfer Protocol`. It is an `application layer protocol` that **serves as** the `foundation` **for** `data communication` **on** the `World Wide Web`.

---
</details>
<!-- end of 'HTTP' section -->



### `Text Input`
Used for `usernames`.
```html
<input type="text">
```

### `Password Input`
Used for `passwords`.
```html
<input type="password">
```

### `Radio Buttons`
Used for `gender selection`.
```html
<input type="password">
```

### `Checkboxes`
Used for **selecting** `hobbies`.
```html
<input type="checkbox">
```

### `Select Dropdown`
**Combining** the `<select>` and `<option>` **tags**, used for `selecting` **a** `country`.

### Textarea
`<textarea>` **tag** for `entering comments`.

The `label` **elements** are used **to** `provide labels` **for** the `form controls`, **improving** `accessibility` **and** `user experience`. The `for` **attribute** is `associated` **with** the `id` of the corresponding form control.



<!-- start of 'form control' section -->
<details>
    <summary>Definition: form control</summary>

#
**In** the context of **web development**, **refers to an** `interactive element` **within an** `HTML form` **that** `allows users` **to** `input data` **or** `make selections`. 

---
</details>
<!-- end of 'form control' section -->


#
Remember that **this is** just a `basic example`, and you can customize it based on your specific needs. `Form handling` **on** the `server side` **is** `not covered` **in** this `example`, but it's an essential part of working with forms in a real-world scenario.