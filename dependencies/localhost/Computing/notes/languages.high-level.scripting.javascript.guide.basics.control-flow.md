---
id: mx1n59eay4u10fxcvl24b3g
title: 4 - Control Flow
desc: ''
updated: 1712867474795
created: 1712858622872
---

In JavaScript, control flow **refers to the** `order` **in which** `statements` **are** `executed` `within` **a** `script` **or a** `function`. There are several constructs that help you control the flow of execution:

- **Sequential Execution:**
  By default, `JavaScript` `executes code` `line by line`, `from top` `to bottom`.
  Example:
  ```javascript
  let x = 5; // Assigning value 5 to variable x
  let y = 10; // Assigning value 10 to variable y
  let z = x + y; // Adding variables x and y, result stored in z
  ```

  if you were to use z before it's assigned a value, you would encounter an error. For example:

  ```javascript
  console.log(z); // Error: z is not defined
  let x = 5;
  let y = 10;
  let z = x + y;
  ```

- **Conditional Statements ("if statements"):**
  These are **used to** `execute` `different blocks` **of** `code` `based on` `specified conditions`.
  Example:
  ```javascript
  let hour = 15; // Assuming current hour is 3 PM

  if (hour < 12) { // Checking if hour is less than 12
    console.log("Good morning!"); // If true, print "Good morning!"
  } else if (hour < 18) { // If not, check if hour is less than 18
    console.log("Good afternoon!"); // If true, print "Good afternoon!"
  } else { // If none of the above conditions are met
    console.log("Good evening!"); // Print "Good evening!"
  }
  ```

- **Switch Statement:**
  **Similar to if...else**, switch **allows you to** `choose` `between` `multiple blocks` **of** `code` **to** `execute` `based on` **the** `value of` **an** `expression`.
  Example:
  ```javascript
  let day = 3; // Assuming day 3 is Wednesday
  let dayName;

  switch (day) { // Switching based on the value of day
    case 1: // If day is 1 (Monday)
      dayName = "Monday"; // Set dayName to "Monday"
      break; // Exit the switch statement
    case 2: // If day is 2 (Tuesday)
      dayName = "Tuesday"; // Set dayName to "Tuesday"
      break; // Exit the switch statement
    // Additional cases...
    default: // If none of the cases match
      dayName = "Unknown"; // Set dayName to "Unknown"
  }
  console.log(dayName); // Output the value of dayName
  ```

- **Loops:**
  Loops are **used to** `repeatedly` `execute` **a** `block` **of** `code` `until` **a** `specified condition` **is** `met`. **JavaScript has** `for`, `while`, **and** `do...while` `loops`.
  Examples:
  ```javascript
  // for loop
  for (let i = 0; i < 5; i++) { // Initialize i to 0; Loop until i is less than 5; Increment i by 1 in each iteration
    console.log(i); // Output the current value of i
  }

  // while loop
  let count = 0; // Initialize count to 0
  while (count < 5) { // Loop until count is less than 5
    console.log(count); // Output the current value of count
    count++; // Increment count by 1
  }

  // do...while loop
  let x = 0; // Initialize x to 0
  do { // Execute the block of code at least once
    console.log(x); // Output the current value of x
    x++; // Increment x by 1
  } while (x < 5); // Continue looping as long as x is less than 5
  ```



<!-- start of 'increment' section -->
<details>
    <summary>Definition: increment</summary>

#
The term "increment" **generally refers to the** `process` **of** `increasing` **or** `adding to` **a** `value`, `typically` **by a** `fixed amount` **or** `unit`. **In programming**, "increment" **often specifically refers to increasing the value of a variable** by a certain amount.

---
</details>
<!-- end of 'increment' section -->



<!-- start of 'iteration' section -->
<details>
    <summary>Definition: iteration</summary>

#
An "iteration" simply **refers to** `one` `cycle` **or** `repetition` `through` **a** `loop` `in` **a** `program`. **It's** `each time` **the** `loop's instructions` **are** `executed`. For example, in a loop that counts from 0 to 4, there are five iterations, one for each number.

---
</details>
<!-- end of 'iteration' section -->



- **Break and Continue:**
  These keywords **are used** `within loops` **to** `alter` **their** `flow`. `break` **is used to** `exit` **the** `loop`, **while** `continue` **is used to** `skip` **the** `current iteration` **and** `move to` **the** `next` **one**.
  Examples:
  ```javascript
  for (let i = 0; i < 10; i++) { // Loop from 0 to 9
    if (i === 5) { // If i equals 5
      break; // Exit the loop
    }
    console.log(i); // Output the current value of i
  }

  for (let i = 0; i < 10; i++) { // Loop from 0 to 9
    if (i === 5) { // If i equals 5
      continue; // Skip the rest of the loop and continue with the next iteration
    }
    console.log(i); // Output the current value of i
  }
  ```

Understanding and utilizing these constructs effectively **allows you to** `control` **the** `flow` **of** your JavaScript `code`, **making it more** `dynamic` **and** `responsive`.



<!-- start of 'dynamic' section -->
<details>
    <summary>Definition: dynamic</summary>

#
"Dynamic" **means** `something` **that's** `always` `changing` **or** `active`. It's about things being lively and `flexible` rather than staying the same.

---
</details>
<!-- end of 'dynamic' section -->



<!-- start of 'requests' section -->
<details>
    <summary>Definition: requests</summary>

#
"Requests" are simply `asking for` `something` `to be` `done` **or** `provided`, whether it's `information`, `help`, **or a** `task`.

---
</details>
<!-- end of 'requests' section -->