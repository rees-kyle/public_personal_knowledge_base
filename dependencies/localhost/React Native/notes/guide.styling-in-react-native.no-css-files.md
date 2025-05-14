---
id: 6f1gfjr1iq0stpxyqlgnjda
title: 3 - No CSS Files
desc: ''
updated: 1747199101664
created: 1747187149698
---

## 🎨 Styling in React Native

**No CSS files** — `all styling` `is JavaScript objects`

---

### 🧠 Key Concept

Unlike web development (HTML + CSS), React Native does not use external CSS files.
All styling is done through JavaScript objects `using` **the** `'style' prop`.

---

### 📌 What This Means

* **No '.css', '.scss', or 'className' usage**.
* **All styles are** `inline or` via `'StyleSheet.create'`, **using** `camelCase` properties.
* `Values` **are** `unitless` — `numbers` are `interpreted as` `dp` (`density-independent pixels`).

---

### ✅ Example

```js
import { Text, View } from 'react-native';

const styles = {
  container: {
    padding: 16,
    backgroundColor: '#f0f0f0',
  },
  text: {
    fontSize: 20,
    color: 'darkblue',
  },
};

<View style={styles.container}>
  <Text style={styles.text}>Styled with JS!</Text>
</View>
```

---

### 🆚 Web vs React Native

| Web (CSS)            | React Native (JS Object) |
| -------------------- | ------------------------ |
| **background-color**   | `backgroundColor`        |
| **font-size: 16px;**   | `fontSize: 16`           |
| **Uses** `classes`         | **Uses** `style props`         |
| **Units like** `px`, `%` | `No units` — `numbers only`  |

---

### ⚠️ Notes

* `No` `global stylesheets`
* `No support for` **standard** `CSS features` **like**:

  * `Media queries` (**need a JS workaround or lib**)
  * `Pseudo-classes` **like** '`:hover`'
  * `Cascade or selector` `chaining`

---

### 🔁 Summary

* `React Native` `styles live` **in JavaScript**.
* `No` `CSS or classes` — `use 'style' props` `with objects`.
* `CamelCase keys`, `unitless numbers`, **and optional** '`StyleSheet.create()`' **for optimization**.