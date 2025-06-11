---
id: kpaeqvwxuithjf8lfl2ffum
title: 2 - Animated API
desc: ''
updated: 1749659443460
created: 1749568194995
---

The Animated API provides a `declarative` **way** `to build animations` `by using animated values` `that update UI components` **smoothly over time**.

### Core idea

**Instead of imperatively updating UI properties frame-by-frame**, you `declare`:

* `Which values` **are** `animated` ('Animated.Value')
* `How` **these** `values change` ('Animated.timing', 'Animated.spring', etc.)
* `What UI styles` `depend on` **these** `values` (using 'Animated.View', 'Animated.Text', etc.)

`React Native` `then handles updating` **the** `UI` **efficiently**.

---

### Key components

* **Animated.Value**: `Holds` a `numeric value` that can be `animated`.
* **Animated.ValueXY**: For `animating` `2D values` (**x and y position**).
* **Animated.timing(config)**: `Animates` a `value` `over a fixed duration` with easing.
* **Animated.spring(config)**: `Animates` a `value` `with spring physics` (bouncy, natural feel).
* **Animated.sequence/parallel/stagger**: `Compose` `multiple animations` `in order`, `together`, `or staggered`.

---

### How it works step-by-step

1. `Create an Animated.Value` **to hold the starting state of the animation**.

2. `Define an animation` (e.g., 'Animated.timing') **describing how the value changes**.

3. `Start the animation` (e.g., '**.start()**').

4. `Use the animated value in styles` **of animated components** ('Animated.View', etc.).

---

### Example: Simple opacity fade-in

```jsx
import React, { useRef, useEffect } from 'react';
import { Animated, View, Text } from 'react-native';

export default function FadeInExample() {
  const opacity = useRef(new Animated.Value(0)).current;

  useEffect(() => {
    Animated.timing(opacity, {
      toValue: 1,
      duration: 500,
      useNativeDriver: true,  // Use native driver for better performance
    }).start();
  }, []);

  return (
    <Animated.View style={{ opacity }}>
      <Text>Fade-in text</Text>
    </Animated.View>
  );
}
```

---

### Advantages of declarative animations with Animated API

* `Clean and readable`: You **declare *what* happens**, **not *how* to update** every frame.
* `Powerful`: Supports **complex animation sequences**, **springs**, **interpolation**.
* `Performance`: With 'useNativeDriver: true', **animations run on native thread**, avoiding JS thread lag.
* `Interpolations`: You can **map animated values to different output ranges** (e.g., opacity 0→1, translateX 0→100).

---

### Common use cases

* `Fading` **elements** in/out (opacity)
* `Moving or sliding` **components** (translateX/Y)
* `Scaling or rotating` **views**
* Creating `animated gestures` `or drag & drop` **effects**
* **Combining** `multiple animations` (parallel, sequence)