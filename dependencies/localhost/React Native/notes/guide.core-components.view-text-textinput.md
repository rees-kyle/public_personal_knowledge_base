---
id: ljbhrme6a3b4cv7rmdkkbu4
title: 1 - View, Text and TextInput
desc: ''
updated: 1747097987001
created: 1747096815468
---

### 🧱 1. `View`

**What it is**:
The **basic** `building block` **for layout** in React Native. It’s **similar to a 'div' element in HTML**, but designed `for mobile styling` **and** `touch handling`.

```js
import { View } from 'react-native';

<View style={{ flex: 1, padding: 20 }}>
  {/* other components */}
</View>
```

**Key differences**:

* No 'div', 'span', or CSS classes — you use 'View' and inline or StyleSheet styles.
* Accepts 'style' as an object, often with Flexbox layout.

---

### 📝 2. `Text`

**What it is**:
Used `to render` `text` **content**. **React Native doesn’t use 'p', 'h1', or 'span'** — **all text is rendered using the 'Text' component**.

```js
import { Text } from 'react-native';

<Text style={{ fontSize: 18, color: 'blue' }}>Hello, React Native!</Text>
```

**Key differences**:

* All text must be wrapped in 'Text' components.
* `Nesting` 'Text' inside 'Text' **works** (for bold, italic, etc.).
* Inline styling is common, but can be extracted into a 'StyleSheet'.

---

### ⌨️ 3. `TextInput`

**What it is**:
An `input field` component `for user` **text input**, like 'input type="text"' in HTML.

```js
import { TextInput } from 'react-native';
import { useState } from 'react';

const [text, setText] = useState('');

<TextInput
  value={text}
  onChangeText={setText}
  placeholder="Type something"
  style={{ borderColor: 'gray', borderWidth: 1, padding: 10 }}
/>
```

**Key differences**:

* Uses `'onChangeText'` **instead of 'onChange'**.
* `Styling` requires `explicit` borders, padding, etc. (**no default browser styles**).
* `No` `'type' attribute` — `all behavior` (**like password input**) is `controlled via` `props` **like 'secureTextEntry'**.

---

### 🧠 Good to Know

* `Components` **use** `Flexbox` **by** `default` **for layout**.
* `Style properties` **are in** `camelCase`: 'backgroundColor', 'fontSize', etc.
* **Use** '`StyleSheet.create({})`' `to define` `reusable styles`.