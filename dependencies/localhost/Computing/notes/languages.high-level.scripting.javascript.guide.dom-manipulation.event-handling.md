---
id: 62pj3cd31w4r2jidgryuqe7
title: 2 - Event Handling
desc: ''
updated: 1715416287067
created: 1713297485810
---

Event handling in DOM manipulation using JavaScript **involves** `listening for` **specific** `actions` **or** `occurrences` `on` `HTML elements` **and** `executing` appropriate JavaScript `code` **in response to those events**. Here's a basic overview of how it works:



<!-- start of 'event' section -->
<details>
    <summary>Definition: event</summary>

#
An "event" **is** `something that` `happens`.

---
</details>
<!-- end of 'event' section -->



<!-- start of 'occurrences' section -->
<details>
    <summary>Definition: occurrences</summary>

#
Occurrences are simply **when** `something` `happens` **or** `exists`.

---
</details>
<!-- end of 'occurrences' section -->



1. **Select the element**: First, you need to select the HTML element **you want to attach the event handler to**. This can be done using `various` `methods` **like** `getElementById`, `getElementsByClassName`, `getElementsByTagName`, `querySelector`, or `querySelectorAll`.

2. **Attach the event listener**: Once you have selected the element, you attach an event listener to it. An event listener **is a** `function` **that will be** `executed` `when` **a** `specified event` `occurs` **on the selected element**. You can attach event listeners **using** the `addEventListener` method.

3. **Specify the event**: When adding an event listener, you need to specify the type of event you want to listen for, **such as** `click`, `mouseover`, `keydown`, **etc**. You can find a `list of` all possible `events` `in` the [MDN Web Docs](https://developer.mozilla.org/en-US/).

> MDN: Mozilla Developer Network

4. **Define the event handler function**: The event handler function **is the** `JavaScript code` **that will be** `executed` when the specified event occurs on the element. This function can perform any actions you want in response to the event, **such as** `changing` **the** `element's` `style`, `updating` **its** `content`, `making` **an** `HTTP request`, **etc**.

Here's **an example** that demonstrates how **to add a click event handler to a button element**:

HTML:
```html
<button id="myButton">Click me</button>
```

JavaScript:
```javascript
// Step 1: Select the button element
const button = document.getElementById('myButton');

// Step 2: Attach an event listener for the 'click' event
button.addEventListener('click', function(event) {
    // Step 4: Define the event handler function
    console.log('Button clicked!');
    // You can perform any actions you want here
});
```

In this example, **when the button with the ID 'myButton' is clicked**, **the event handler function logs 'Button clicked!' to the console**. You can replace this code with any other actions you want to perform in response to the click event.

**Event handling** is fundamental in web development as it **allows you to** `create` `interactive` **and** `dynamic` `web pages`. With event handling, you **can** `respond to` `user actions` **and** `create` `engaging` `user experiences`.