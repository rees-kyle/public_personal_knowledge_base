---
id: qaklwwmar2ukw9vuvsb7t3w
title: 1 - Flexbox
desc: ''
updated: 1747184760498
created: 1747183757556
---

It **works similarly to CSS Flexbox**, but there are **a few differences** worth noting (**like default direction and unit handling**).

---

## 📐 Flexbox in React Native

`React Native uses` `Flexbox by default` **for layout**.

### ✅ Key Differences from CSS

* `Default flexDirection` **is** `column` (**not row** like in web).
* `All units` **are** `unitless` `and interpreted as` `density-independent pixels` (`dp`).

---

### 🔑 Core Flexbox Properties

#### 1. flexDirection

`Controls` **the** `main axis` `direction`.

```js
// Horizontal layout
flexDirection: 'row'

// Vertical layout (default)
flexDirection: 'column'
```

---

#### 2. justifyContent

`Aligns children` `along` **the** `main axis` (**row or column**).

```js
// Main axis: center, start, end, spaced
justifyContent: 'flex-start' | 'center' | 'flex-end' | 'space-between' | 'space-around' | 'space-evenly'
```

---

#### 3. alignItems

`Aligns children` `along` **the** `cross axis`.

```js
alignItems: 'flex-start' | 'center' | 'flex-end' | 'stretch' | 'baseline'
```

---

#### 4. flex

`Defines` `how much space` `a component` `should take up` `relative to others`.

```js
// Take all available space
flex: 1

// Take twice as much space as others
flex: 2
```

---

#### 5. flexWrap

`Wraps children onto` `multiple lines` (**useful in rows**).

```js
flexWrap: 'wrap' | 'nowrap'
```

---

### 🧪 Example

```js
import { View, Text } from 'react-native';

<View style={{ flex: 1, flexDirection: 'row', justifyContent: 'space-around', alignItems: 'center' }}>
  <Text>Box 1</Text>
  <Text>Box 2</Text>
  <Text>Box 3</Text>
</View>
```

**This lays out the 3 boxes horizontally, evenly spaced, and centered vertically**.

---

### 📌 Summary Table

| Property         | Description                      |
| ---------------- | -------------------------------- |
| **flexDirection**  | `Main` `axis direction` (**row**/**column**) |
| **justifyContent** | `Alignment on` `main axis`           |
| **alignItems**     | `Alignment on` `cross axis`          |
| **flex**           | `Proportional` `sizing`              |
| **flexWrap**       | `Multi-line` `wrapping`              |