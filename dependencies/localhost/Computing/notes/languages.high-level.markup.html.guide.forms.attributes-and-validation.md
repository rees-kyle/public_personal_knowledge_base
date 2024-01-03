---
id: xhk54rxi6mnofjgflure69j
title: 1 - Attributes and Validation
desc: ''
updated: 1704246180670
created: 1704074245892
---

Attributes and validation play a crucial role in **ensuring** that the `data` entered by users **is** `accurate` **and** `meets` **certain** `criteria`. Here are some common form attributes and validation techniques in HTML:

### Form Attributes:

1. **action:**
   - `Specifies` the `URL` `where` the `form data` **should be** `sent` **upon** `submission`.

   ```html
   <form action="/submit_form" method="post">
   ```

2. **method:**
   - `Specifies` the `HTTP method` **to be** `used` **when** `submitting` the `form` (usually "`GET`" or "`POST`").

   ```html
   <form action="/submit_form" method="post">
   ```

3. **enctype:**
   - `Specifies` **how** the `form data` **should be** `encoded` **when** `submitting` (e.g., "`application/x-www-form-urlencoded`" or "`multipart/form-data`").

   ```html
   <form action="/submit_form" method="post" enctype="multipart/form-data">
   ```

4. **target:**
   - `Specifies where` **to** `display` **the** `response` **after** `submitting` the form (e.g., "`_blank`" **for** a `new window`).

   ```html
   <form action="/submit_form" method="post" target="_blank">
   ```

### Input Element Attributes:

1. **type:**
   - `Specifies` the `type` **of** `input` (e.g., text, password, checkbox, radio, etc.).

   ```html
   <input type="text" name="username">
   ```

2. **name:**
   - `Identifies` **the** `input field` when the form is submitted.

   ```html
   <input type="text" name="username">
   ```

3. **placeholder:**
   - `Provides` a short `hint` **that** `describes` the `expected value` **of** the `input field`.

   ```html
   <input type="text" name="username" placeholder="Enter your username">
   ```

4. **required:**
   - `Specifies` that the `input field` `must be` `filled out` before submitting the form.

   ```html
   <input type="text" name="username" required>
   ```

### Validation:

1. **Pattern Attribute:**
   - `Specifies` a regular `expression pattern` **that the** `input's value` **must** `match`. It is particularly `useful` **for** `enforcing` **specific** `formats` for text input fields, **such as** `email addresses` and `phone numbers`.

   ```html
   <input type="text" name="zip_code" pattern="\d{5}" title="Enter a valid 5-digit ZIP code">
   ```

2. **Min and Max Attributes:**
   - Specifies the minimum and maximum `values` **for** `numeric input`.

   ```html
   <input type="number" name="age" min="18" max="99">
   ```

3. **Length Attributes:**
   - Specifies the minimum and maximum `length` **for** `text input`.

   ```html
   <input type="text" name="username" minlength="3" maxlength="20">
   ```

4. **Custom JavaScript Validation:**
   - You can use the `oninput` **or** `onchange` **attributes** to `trigger` `custom JavaScript functions` **for** `dynamic validation`.

   ```html
   <input type="text" name="email" oninput="validateEmail()">
   <script>
       function validateEmail() {
           // Custom validation logic
       }
   </script>
   ```

These are just `a few examples` of form attributes and validation techniques in HTML. The specific attributes and validation rules you use will depend on the requirements of your form and the type of data you are collecting.