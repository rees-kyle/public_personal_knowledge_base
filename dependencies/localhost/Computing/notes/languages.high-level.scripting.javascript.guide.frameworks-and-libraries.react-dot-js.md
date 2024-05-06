---
id: v284mkmeikblkwo4tq6pka8
title: 1 - React.js
desc: ''
updated: 1714880507045
created: 1714793694600
---

**React.js**, **commonly just called** `React`, **is a powerful and popular JavaScript** `library for` `building` `user interfaces`, especially complex interactive web applications. `Created by` `Facebook` (`now Meta Platforms`) and **first** `released in` `2013`, React has rapidly become one of the `most` **widely** `used` libraries **in the web development community**. It **allows developers** `to create` `large` **web** `applications that` **can** `change data`, `without reloading` **the** `page`. **Its main goal is to be** `fast`, `scalable`, **and** `simple`. It **works only on user interfaces in the application**; this **corresponds to the view in the** `MVC template`.



<!-- start of 'mvc template' section -->
<details>
    <summary>MVC template</summary>

#
The MVC (`Model-View-Controller`) `template` **is a** `design pattern` **used** `in software development` `to separate` **an** `application into` `three` **interconnected** `components`. **This separation** `helps` `manage complexity`, `facilitates` `efficient code organization`, **and** `supports` **the** `scalability` of the application. Here’s a breakdown of the three components:

1. **Model:** This component `handles` **the** `data` **and** `business logic` **of the application**. It is **responsible for** `retrieving` `data` `from databases`, `transforming it`, **and** `defining` **the** `business rules that` `data is` `subject to`.

2. **View:** The View **is the** `user interface` **of the application**. **It** `displays` `data to` **the** `user` **and** `sends` `user commands` `to` **the** `Controller`. It's **responsible** `for presenting` **the** `data` `provided by` **the** `Model in` **a** `format` **suitable** `for interaction`, often generating user interface dynamically based on the Model data.

3. **Controller:** The Controller **acts as an** `intermediary` `between` **the** `Model` `and` **the** `View`. It `receives` `user inputs and` `decisions` (**generally** `through interactions with` **the** `View`), and `then processes` **these** `inputs by` `making` `calls to` `Model objects` `to retrieve data or` `to update` **the** `View`.



<!-- start of 'intermediary' section -->
<details>
   <summary>Definition: intermediary</summary>

#
An intermediary **is a** `person or` `organization` **that acts as a** `mediator or` `agent` `between` `two parties`, **helping** `to facilitate` `communication`, `transactions`, **or** `agreements`.

---
</details>
<!-- end of 'intermediary' section -->



The `MVC` design **enables developers** `to separate concerns`, `enhance` **the** `modularity` of an application, **and** `improve` **its** `maintainability`, `scalability`, **and** `testability`.

---
</details>
<!-- end of 'mvc template' section -->



## Key Features of React.js

1. **Component-Based Architecture:**
   React is built around the concept of `reusable components`. **A** `component` **is a** `self-contained module that` `renders` **some** `output` `based on` **the** `input it` `receives`. This `modularity` **makes it** `easier to` `manage` **and** `scale` **large applications**.

2. **JSX:**
   JSX is a `syntax extension` for JavaScript **recommended by React** `for writing HTML` within JavaScript. It looks like regular HTML but actually works with JavaScript. JSX makes it `easier to` `write` and add HTML in React.

3. **Virtual DOM:**
   React uses the concept of Virtual DOM that allows it `to know` exactly `when to` `re-render or` when to `ignore` **some specific** `parts of` **the** `DOM` `based on` **the** `changes in` **the** `state of` **the** `application`. This approach `increases` the `performance` **and** `efficiency` **of applications**.

4. **One-Way Data Binding:**
   In React, the flow of data is directed in one way (`parent to child` `components`). This **makes the** `code` `more stable`, and also makes the logic of the application `easier to` `understand`.

5. **Declarative UI:**
   React makes it intuitive to build interactive UIs. `Design` `simple views` `for each` `state in` your `application`, and React will `efficiently update` **and** `render` just the right `components when` **your** `data changes`.

6. **Rich Ecosystem:**
   The React ecosystem is vast and `includes` numerous additional `libraries for` `routing`, `state management`, **and** `interaction with` `APIs`. Libraries **such as** `Redux` for state management **and** `React Router` for navigation in React applications are widely used.

## Popular Tools and Libraries in the React Ecosystem

- **Create React App:** A `CLI` `tool for` `creating` **new** `React projects`. It `sets up` **a modern** `web development` `environment` **so you can** `focus on` `writing code`.
- **Next.js:** A **React** `framework for` `building` `server-side` `rendering and` `static` `web applications`.
- **Redux:** A `state management` `library` **that can be used with React** (**among other libraries**) `to manage` the `state of` the `application` `more efficiently` `and with` `better predictability`.
- **React Router:** **A** `library` to handle routing in React applications, `enabling navigation` `from one view to` `another`.
- **Material-UI, Ant Design, and Chakra UI:** **Popular** `UI frameworks` **for React that provide** `ready-to-use` `components`.

## When to Use React

- **Single Page Applications (SPAs):** React is very effective for developing SPAs **where you need a** `fast`, `interactive` `user experience`.
- **Mobile Apps:** **With** `React Native`, you can use the `same` `design principles as` `React` to build native mobile apps for iOS and Android.
- **Complex Web Applications:** **React’s** `component-based` `architecture` **makes it** `suitable for` **complex application** `interfaces` `that require` `dynamic` `data updates`.



<!-- start of 'architecture' section -->
<details>
   <summary>Definition: architecture</summary>

#
Architecture **is the** `art and science of` `designing and constructing` `buildings and other` `physical structures`. It **involves** `planning`, `designing`, **and** `overseeing` **the** `construction process`, `balancing aesthetic considerations` `with functional and technical requirements`.

---
</details>
<!-- end of 'architecture' section -->



<!-- start of 'aesthetic' section -->
<details>
   <summary>Definition: aesthetic</summary>

#
Aesthetic **refers to the** `appreciation of` `beauty or` `good taste`, **and involves the study of what makes** `something` `visually or` `sensorially pleasing`.

---
</details>
<!-- end of 'aesthetic' section -->



<!-- start of 'sensorially' section -->
<details>
   <summary>Definition: sensorially</summary>

#
`Relating to` **the** `senses`, **such as** `sight`, `hearing`, `touch`, `taste`, **and** `smell`.

---
</details>
<!-- end of 'sensorially' section -->



<!-- start of 'pleasing' section -->
<details>
   <summary>Definition: pleasing</summary>

#
`Providing` **a** `sense of` `satisfaction or` `enjoyment`, **often by being** `attractive or` `delightful`.

---
</details>
<!-- end of 'pleasing' section -->



## Conclusion

**React** `continues to` `evolve and adapt`, gaining new features and improvements that help developers `build efficient and` `enjoyable` `web applications`. Whether you're building a `small interactive website or` **a** `large-scale enterprise application`, React’s robust `ecosystem` **and** `community` can provide the `tools` **and** `support` needed to build powerful applications efficiently.