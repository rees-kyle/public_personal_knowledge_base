---
id: 0zyw4d4h8hzti4be0y6s0mf
title: 4 - Platform Specific Styling
desc: ''
updated: 1747200802881
created: 1747199858658
---

**React Native lets you** `write` `different styles` `for iOS and Android`, **so your** `app` `looks and feels native` `on each platform`.

There are `3 main ways` **to handle platform-specific styling**:

---

### ✅ 1. `Platform` Module

React Native provides a `'Platform' module` `to check` **the** `platform` **dynamically**.

```js
import { Platform, StyleSheet } from 'react-native';

const styles = StyleSheet.create({
  text: {
    fontSize: Platform.OS === 'ios' ? 20 : 18,
    color: Platform.OS === 'android' ? 'green' : 'blue',
  },
});
```

---

### ✅ 2. `Platform.select()`

`Cleaner way` `to write different styles` `in one block`.

```js
const styles = StyleSheet.create({
  container: {
    ...Platform.select({
      ios: {
        paddingTop: 40,
      },
      android: {
        paddingTop: 20,
      },
    }),
  },
});
```

---

### ✅ 3. Separate Files (`.ios.js` / `.android.js`)

`Create` `platform-specific versions of` `a file`:


- Button.ios.js
- Button.android.js


`React Native` `will automatically pick` **the** `correct file` **based on the platform**. Great **for clean separation of logic and styling**.

---

### 📝 Example

```js
import { Platform, StyleSheet, Text, View } from 'react-native';

const styles = StyleSheet.create({
  title: {
    fontSize: 24,
    fontWeight: Platform.OS === 'ios' ? '600' : 'bold',
    color: Platform.OS === 'android' ? 'darkred' : 'navy',
  },
});

<View>
  <Text style={styles.title}>Platform-specific Style</Text>
</View>
```

---

### 🔁 Summary

| Method              | Best For                          |
| ------------------- | --------------------------------- |
| **'Platform.OS'**       | `Quick` `conditional tweaks`          |
| **'Platform.select()'** | `Cleaner` `multi-platform handling`   |
| **Separate files**      | `Clean separation of` `logic + style` |