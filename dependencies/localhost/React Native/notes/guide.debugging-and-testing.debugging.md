---
id: by1a4r6s9uv6mi183j4q0l2
title: 1 - Debugging
desc: ''
updated: 1749738311503
created: 1749736084240
---

## Debugging with Flipper and React Native Debugger

### Flipper

Flipper is **a powerful**, `extensible` `debugging tool` for React Native apps.



<!-- start of 'extensible' section -->
<details>
    <summary>Definition: extensible</summary>

#
Extensible **refers to** `something` that is `designed to be` `easily expanded` **or** `enhanced with new features or components` `without changing its core structure`.

---
</details>
<!-- end of 'extensible' section -->



####
**Key features:**

* `Inspect` React Native `logs and performance`
* `Visualize` the `component tree`
* `Monitor` `Redux` (with plugin)
* `View and edit` `layout hierarchy` (similar to Chrome DevTools for native views)
* `Inspect` `network requests` **and** `responses`
* `SQLite` **and** `AsyncStorage` `inspectors`



<!-- start of 'visualize' section -->
<details>
    <summary>Definition: visualize</summary>

#
Visualize **means** `to form a mental image of something` `or to make something visible`, **especially through** `diagrams`, `graphics`, **or** `tools` that help you `see abstract or complex information` `clearly`.

---
</details>
<!-- end of 'visualize' section -->



####
**Setup:**

1. `Install Flipper` **from** [https://flipper.io](https://flipper.io)
2. For `bare React Native`, **most setups** `work out of the box` (RN 0.62+)
3. `Plugins` like **React DevTools**, **Redux DevTools**, **and Network** `are pre-installed`

**If you're using** `Expo`, **Flipper is** `not officially supported` — you’ll **need a bare workflow to use it**.

---

### React Native Debugger

React Native Debugger is **a** `standalone app` `combining Chrome DevTools`, `Redux DevTools`, **and** `React DevTools`.

**Key features:**

* `View` `console logs`
* `Inspect` `network traffic`
* `Inspect` **and** `time-travel through` `Redux state`
* `Debug JavaScript` **and** `inspect components`

**Setup:**

1. `Download from` [https://github.com/jhen0409/react-native-debugger](https://github.com/jhen0409/react-native-debugger)
2. `Open` it **and** `set port to` `8081`
3. `In` **your React Native** `app`, `run`:

```bash
react-native start
```

4. `Press` '`Cmd+D`' `or 'Ctrl+M'` **in the emulator**, **then** `select` '`Debug JS Remotely`'

**With Redux:**

* If you use Redux, **it** `auto-detects` `and shows the state tree and actions in` **the** `Debugger window`