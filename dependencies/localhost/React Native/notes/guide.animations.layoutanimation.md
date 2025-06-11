---
id: 9ixmuwvpmjitiod7yo8m95t
title: 1 - 'LayoutAnimation'
desc: ''
updated: 1749568118269
created: 1749566820112
---

Animations `make` **your** `app` `feel smoother and more engaging` `by adding` `motion effects to UI elements` — **like** `fading`, `sliding`, `scaling`, **or** `moving components` on the screen.

React Native provides **several** `ways to handle animations`:

* '`LayoutAnimation`' (**simple**, declarative, for layout changes)
* `Animated API` (more **flexible**, supports **complex** animations)
* `Reanimated` (third-party, **advanced**, **performant** animations)

---

### 'LayoutAnimation'

* **What it is:**
  'LayoutAnimation' `automatically animates` `global layout changes` that happen `when the size or position of components` `change`.

* **How it works:**
  When you change the layout of elements in your app (e.g., by adding/removing a component, or changing styles that affect layout), 'LayoutAnimation' `animates those changes smoothly` `without you having to manually define` `every animation step`.

* **Why use it:**
  It’s `easy to use`, requires `minimal code`, and works well `for simple layout transitions` **such as** `expanding`/`collapsing views` `or animating list item insertion`/`removal`.

* **Limitations:**

  * `Works only` `for layout changes` (**not** for animating **opacity**, **colors**, **or transforms**).
  * `Platform differences`: **works** `out-of-the-box on iOS` **but** `on Android you have to enable it` **explicitly**.

---

### Basic example of 'LayoutAnimation':

```javascript
import React, { useState } from 'react';
import { View, Button, LayoutAnimation, Platform, UIManager, StyleSheet } from 'react-native';

// Enable 'LayoutAnimation' on Android
if (Platform.OS === 'android' && UIManager.setLayoutAnimationEnabledExperimental) {
  UIManager.setLayoutAnimationEnabledExperimental(true);
}

export default function LayoutAnimationExample() {
  const [expanded, setExpanded] = useState(false);

  const toggleExpand = () => {
    // Animate the next layout change
    LayoutAnimation.configureNext(LayoutAnimation.Presets.easeInEaseOut);
    setExpanded(!expanded);
  };

  return (
    <View style={styles.container}>
      <Button title="Toggle Box Size" onPress={toggleExpand} />
      <View style={[styles.box, expanded && styles.expandedBox]} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: { padding: 20 },
  box: { width: 100, height: 100, backgroundColor: 'blue' },
  expandedBox: { width: 200, height: 200 },
});
```

* When you **press the button**, the **blue box smoothly animates between small and large sizes**.
* The `key is calling 'LayoutAnimation.configureNext()'` right `before the state change` `that triggers a layout update`.