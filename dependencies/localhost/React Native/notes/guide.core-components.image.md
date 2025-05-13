---
id: qoobgf2rqogve7l37w4bxk8
title: Image
desc: ''
updated: 1747113878097
created: 1747112958498
---

Image, the React Native component `for displaying pictures`. It’s functionally **similar to the 'img' tag in HTML but with a mobile-first API and styling system**.

---

### 🖼️ `Image` Component

**What it is**:
Used `to display` `static or dynamic images` `from local files` `or remote URLs`.

```js
import { Image } from 'react-native';

<Image
  source={{ uri: 'https://example.com/image.png' }}
  style={{ width: 100, height: 100 }}
/>
```

---

### 📂 Local Images

`To load images` `from` **your** `project`:

```js
<Image
  source={require('./assets/logo.png')}
  style={{ width: 100, height: 100 }}
/>
```

The `require` **syntax is** `only for` `local images` — **not URLs**.

---

### 🌐 Remote Images

`To load images` `from` **a** `URL`:

```js
<Image
  source={{ uri: 'https://example.com/image.png' }}
  style={{ width: 200, height: 200 }}
/>
```

You `must define` '`width`' **and** '`height`' **in the 'style'** — otherwise, the image won’t appear.

---

### 🛠️ Common Props

| Prop         | Description                                       |
| ------------ | ------------------------------------------------- |
| **source**     | `Image URI` **or** `'require()'` **for local files**          |
| **style**      | Defines size, shape, borders, etc.                |
| **resizeMode** | '`cover`', '`contain`', '`stretch`', '`center`', '`repeat`' |
| **onLoad**     | `Called when` the `image` **has** `loaded`                  |
| **onError**    | `Called if` `loading fails`                           |

---

### 🧠 Summary

* Use '`require()`' `for local assets` and '`{ uri: ... }`' `for remote`.
* `Always set` '`width`' **and** '`height`'.
* **Customize appearance with** '`resizeMode`' **and** '`style`'.