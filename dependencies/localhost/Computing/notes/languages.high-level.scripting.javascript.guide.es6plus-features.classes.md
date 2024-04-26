---
id: kw4as7xx7lbto3hsesfx2wd
title: 4 - Classes
desc: ''
updated: 1714158946701
created: 1714151081532
---

One of the standout features of ES6 is the introduction of classes. Let’s explore how JavaScript classes work and some of their benefits.

**Before ES6**, **JavaScript used functions and prototypes to mimic an object-oriented class-like structure**. With ES6, the syntax for creating such structures has become much `cleaner` **and** `clearer` **with** the introduction of **classes**.

## Basic Syntax of a Class

**A** `class` **in JavaScript** `is` **a** `blueprint for` `creating objects`. A class **can** `include properties` `and` `methods`. Here's a simple example:

```javascript
// Define a class
class Person {
  // Constructor method to initialize new 'Person' objects
  constructor(name, age) {
    // Properties to store the person's name and age
    this.name = name;
    this.age = age;
  }

  // Method to describe the person with their age
  describe() {
    return `${this.name} is ${this.age} years old.`;
  }
}

// Creating an instance of the 'Person' class
const person1 = new Person("Alice", 30);

// Outputting the description of 'person1'
console.log(person1.describe()); // Output: "Alice is 30 years old."
```

### Constructor Method

The constructor method is a special method **for** `creating` `and` `initializing` **an** `object` `created with` **a** `class`. **There can** `only` **be** `one` `constructor` **method** `in` **a** `class`.

### Class Methods

`Methods` `inside` **a** `class` `define` **what** `actions` **the** `class objects` **can** `perform`. '**describe**' **in the above example is a method which all instances of 'Person' can use**.

### Static Methods

Static methods are `defined on` **the** `class` **itself**, **and** `not on` `any` `instance of` **the** `class`. They **can be** `called` `without` `instantiating` **the** `class`, **but** `cannot be` `called through` **a** `class instance`.



<!-- start of 'instantiating' section -->
<details>
    <summary>Definition: instantiating</summary>

#
Instantiating **is like** `making` **an** `actual item` `from` **a** `blueprint`. **In computer programming**, when you instantiate a class, **you** `create` **an** `actual object` `from` **a** `set of` `instructions` `or` `template` `defined in` **the** `class`. This `object` then `has` **its** `own` **specific** `characteristics` **and can** `perform` **certain** `actions` `defined by` **the** `class`.

---
</details>
<!-- end of 'instantiating' section -->



```javascript
// Define a class to represent a point in a 2D space
class Point {
  // Constructor to initialize new Point instances
  constructor(x, y) {
    this.x = x; // x-coordinate of the point
    this.y = y; // y-coordinate of the point
  }

  // Static method to calculate and return the Euclidean distance between two points
  static distance(a, b) {
    const dx = a.x - b.x; // Difference in x-coordinates
    const dy = a.y - b.y; // Difference in y-coordinates
    // Calculate square root of the sum of squares of dx and dy
    return Math.sqrt(dx * dx + dy * dy);
  }
}

// Create a new 'Point' instance with coordinates (5, 5)
const p1 = new Point(5, 5);
// Create another new Point instance with coordinates (10, 10)
const p2 = new Point(10, 10);

// Log the distance between point 'p1' and 'p2' using the static method 'distance'
console.log(Point.distance(p1, p2)); // Output: 7.0710678118654755
```



<!-- start of 'euclidean distance' section -->
<details>
    <summary>Definition: Euclidean distance</summary>

#
The Euclidean distance **is the** `term` **used** `to describe` **the** `straight-line` `distance` `between` `two points` `in space`. **This distance is calculated using a formula derived from the Pythagorean theorem**, which most people learn in basic geometry.

---
</details>
<!-- end of 'euclidean distance' section -->



### Inheritance

`Classes` **in JavaScript** `support` `inheritance` **through the** `extends keyword`, `allowing` **one** `class to` `inherit` `from another`.

```javascript
// Define a class `Student` which extends the `Person` class to inherit its properties and methods
class Student extends Person {
  // Constructor method to initialize a new instance of Student
  constructor(name, age, grade) {
    super(name, age);  // Call the parent class (Person) constructor to initialize name and age
    this.grade = grade; // Additional property specific to Student: their current grade in school

  // Override the `describe` method to add additional details about the student
  describe() {
    // Call the parent class (Person) 'describe' method and append additional student-specific information
    return `${super.describe()} and is in grade ${this.grade}.`;
  }
}

// Create a new instance of 'Student'
const student1 = new Student("Bob", 12, 7);

// Output the description of the student using the describe method
console.log(student1.describe()); // Output: "Bob is 12 years old and is in grade 7."
```

## Benefits

- **Simplicity:** `Classes` provide a much `clearer` **and** `simpler` **syntax for** `creating objects` **and dealing with** `inheritance`.
- **Readability and Organization:** Helps in organizing code better and makes it more readable.
- **Encapsulation:** `Encourages` `encapsulation` **and** `object-oriented` **programming** `techniques`.



<!-- start of 'encapsulation' section -->
<details>
    <summary>Definition: encapsulation</summary>

#
Encapsulation **is a** `concept in` `object-oriented` `programming` `where data` `and` **the** `methods that` `work on` `that data` `are wrapped together` `in one unit`, **called** `a class`. It also **involves keeping some parts of a class hidden from the outside**, **so they can't be changed unexpectedly**. This **helps in managing complexity and ensuring that data is used safely and correctly**.

---
</details>
<!-- end of 'encapsulation' section -->



**JavaScript** `classes are` `syntactical sugar` **over JavaScript's existing prototype-based inheritance and** `do not` `introduce` **a** `new` `object-oriented` `inheritance model` **to the language**. **They** `make` **the** `code` `more modular`, `maintainable`, **and** `understandable`.



<!-- start of 'syntactic' section -->
<details>
    <summary>Definition: syntactic</summary>

#
"Syntactic" **refers to the** `rules` `and` `structures` **used** `to organize` `words into` `sentences` **in a language**. **In programming**, it pertains to the **rules that determine how code must be structured to be valid and understood by a computer**.

---
</details>
<!-- end of 'syntactic' section -->



<!-- start of 'syntactic sugar' section -->
<details>
    <summary>Definition: syntactic sugar</summary>

#
Syntactic sugar **refers to** `features in` **a** `programming language` `that make` `code` `easier to` `write` `and` `read` `but don't` `add any` `new functionality`. It's **like a shortcut** that makes code clearer without changing what it does. For **example**, **shortcuts that let you write loops or conditions** in a simpler way are considered syntactic sugar.

---
</details>
<!-- end of 'syntactic sugar' section -->