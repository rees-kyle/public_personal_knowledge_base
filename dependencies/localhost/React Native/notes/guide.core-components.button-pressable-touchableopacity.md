---
id: bvdeli4pfneyqhw7p38auvz
title: 3 - Button, Pressable, TouchableOpacity
desc: ''
updated: 1747101658619
created: 1747100517697
---

**These components** `handle` `user interaction` **like** `clicks or taps` and are **similar** in function **to buttons in web development**, but with key mobile-specific behavior.

---

### 🟦 1. `Button`

**What it is**:
A **simple**, **built-in button with** `limited styling` capabilities. It’s **easy to use** `for basic interactions`.

```js
import { Button } from 'react-native';

<Button
  title="Click Me"
  onPress={() => console.log('Button pressed')}
/>
```

**Pros**:

* `Simple` to use.
* `Cross-platform` **appearance**.

**Cons**:

* `Minimal styling` **options** (e.g., **can’t change font or shape**).
* **Can** `only` **modify** '`color`' **and** '`title`'.

---

### 🟪 2. `Pressable`

**What it is**:
The `most flexible` **and** `modern` **way** to create `touchable components`. **Allows** `full control` **over styling and press feedback** (like scaling, highlighting, etc.).

```js
import { Pressable, Text } from 'react-native';

<Pressable
  onPress={() => console.log('Pressed!')}
  style={({ pressed }) => [
    {
      backgroundColor: pressed ? 'lightgray' : 'white',
      padding: 10,
      borderRadius: 5,
    },
  ]}
>
  <Text>Custom Button</Text>
</Pressable>
```

**Pros**:

* Complete `control over` `styles and animations`.
* `Supports events` **like** '`onPressIn`', '`onPressOut`', '`onLongPress`'.

**Use when**:

* **You want a** `custom` `look and feel`.
* **You need** `fine-grained control` `over press behavior`.

---

### 🟧 3. `TouchableOpacity`

**What it is**:
`A wrapper` `that reduces opacity` `when pressed` — **useful** `for making` `custom buttons` `or touchable UI components`.

```js
import { TouchableOpacity, Text } from 'react-native';

<TouchableOpacity
  onPress={() => console.log('Touched!')}
  style={{ backgroundColor: 'dodgerblue', padding: 10, borderRadius: 5 }}
>
  <Text style={{ color: 'white' }}>Tap Me</Text>
</TouchableOpacity>
```

**Pros**:

* `Simple` to use.
* Provides `built-in` `visual feedback` (**opacity fade**).

**Cons**:

* `Less flexible than` '`Pressable`' for advanced use.

---

### 🧠 Summary

| Component          | Styling Control | Feedback Effect               | Best Use Case                        |
| ------------------ | --------------- | ----------------------------- | ------------------------------------ |
| **Button**           | ❌ `Limited`       | `Default` native button         | `Quick buttons` with `minimal setup`     |
| **Pressable**        | ✅ `Full`          | `Custom` (opacity, scale, etc.) | `Highly customized` and `interactive UI` |
| **TouchableOpacity** | ✅ `Moderate`      | `Fades opacity` **on press**        | `Custom` buttons with `simple feedback`  |