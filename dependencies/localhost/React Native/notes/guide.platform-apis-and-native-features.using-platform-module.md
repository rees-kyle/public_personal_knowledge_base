---
id: 16rcm8p3iqle3kazf0xqwh6
title: 3 - Using 'Platform' Module
desc: ''
updated: 1747886079829
created: 1747885840524
---


The Platform module **lets you** `detect` **the** `current platform` (**iOS**, **Android**, or **Web**) `and write` `conditional code` **based on it**.

---

`Import` the `module`:

```js
import { Platform } from 'react-native';
```

---

`Check` the `platform`:

```js
if (Platform.OS === 'ios') {
  // iOS-specific code
} else if (Platform.OS === 'android') {
  // Android-specific code
}
```

---

**Example usage in a style object**:

```js
const styles = {
  paddingTop: Platform.OS === 'android' ? 25 : 0
};
```

---

Use '`Platform.select`' `for cleaner` `conditional logic`:

```js
const instructions = Platform.select({
  ios: 'Press Cmd+R to reload, Cmd+D or shake for dev menu',
  android: 'Double tap R on your keyboard to reload, Shake or press menu button for dev menu',
});
```

---

You can also `check` the `platform version`:

```js
console.log(Platform.Version); // e.g., 30 on Android or '14.4' on iOS
```