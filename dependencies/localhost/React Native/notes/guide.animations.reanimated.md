---
id: 5yk4ipi16jwnbqo9t4ocu7p
title: 3 - Reanimated
desc: ''
updated: 1749661140028
created: 1749659556513
---

### What is Reanimated?

React Native Reanimated is **an** `advanced` `animation library` built `for creating` `high-performance`, `complex animations` `that run` **directly** `on the UI thread`. `By offloading animations` `from the JavaScript thread`, it **ensures** `smooth`, `jank-free performance` **even** `under heavy load`. It's an `optional` tool, **ideal** `for gesture-based interactions` `and demanding animation scenarios`.

It **provides** `more control`, `performance`, `and flexibility` **than the basic Animated API**.

---

### Why use Reanimated?

* `Runs animations synchronously` **on the native UI thread using a custom worklet system**
* `Smooth` even **during complex gesture-based animations**
* `Works well with 'react-native-gesture-handler'`
* `Enables gesture-driven animations` (e.g. **draggable bottom sheets**, **swipes**, **snapping transitions**)
* **Supports** `layout animations`, `shared transitions`, **and** `complex chaining`

---

### Installation (bare RN or Expo)

If using `bare React Native`:

```bash
npm install react-native-reanimated
npx pod-install
```

If using `Expo`:

```bash
npx expo install react-native-reanimated
```

**Also** `add this line` `to 'babel.config.js'`:

```js
plugins: ['react-native-reanimated/plugin']
```

---

### Key Features

* '**useSharedValue()**' — `store` `animatable values on` the `UI thread`
* '**useAnimatedStyle()**' — `bind styles` `to shared values`
* '**withTiming()**', '**withSpring()**', '**withDelay()**' — `animate` `shared values`
* `Worklets` — `lightweight JS functions` `that run on` the `UI thread`

---

### Example: Fade in a view using Reanimated 2

```jsx
import React, { useEffect } from 'react';
import { View, Text } from 'react-native';
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  withTiming,
} from 'react-native-reanimated';

export default function FadeInReanimated() {
  const opacity = useSharedValue(0); // Initial opacity

  const animatedStyle = useAnimatedStyle(() => {
    return {
      opacity: opacity.value,
    };
  });

  useEffect(() => {
    opacity.value = withTiming(1, { duration: 500 }); // Animate to 1
  }, []);

  return (
    <Animated.View style={animatedStyle}>
      <Text>Reanimated Fade-In</Text>
    </Animated.View>
  );
}
```

---

### When to Use Reanimated

✅ You’re `building`:

* `Gesture-heavy` `apps` (**drag**, **swipe**, **pan**)
* `Smooth animations` `tied to user input`
* `Performance-critical` `interfaces`
* `Animated components` `that must not drop frames`

🚫 `Skip it if`:

* **You** `only need` **simple** `opacity`, `translate`, **or** `scale animations`
* **You’re** `fine with` `'Animated' or 'LayoutAnimation'`