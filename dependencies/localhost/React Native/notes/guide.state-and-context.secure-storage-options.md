---
id: 2x9n9deiv2ebfwlc15uq9xy
title: 3 - Secure Storage Options
desc: ''
updated: 1749482736718
created: 1749481590037
---

Here’s a breakdown of secure storage options in React Native `for sensitive data` **like** `tokens` **or** `passwords`:

### Why not use AsyncStorage for sensitive data?

`AsyncStorage` **is** `not encrypted`, so it’s **not safe for** storing sensitive information (e.g., **auth tokens**, **passwords**, **banking data**).

---

### Recommended Secure Storage Options

#### 1. **expo-secure-store** (Expo apps)

* Uses '`Keychain`' `on iOS` **and** '`Keystore`' `on Android`
* `Easy to implement`, **provide** `built-in encryption`, **and** are `safe for` **securely** `storing sensitive data`.

`Install`:

```bash
npx expo install expo-secure-store
```

**Usage**:

```js
import * as SecureStore from 'expo-secure-store';

await SecureStore.setItemAsync('token', 'abc123');

const token = await SecureStore.getItemAsync('token');
console.log(token);

await SecureStore.deleteItemAsync('token');
```

---

#### 2. **react-native-keychain** (non-Expo / bare React Native)

* `Native module` `for encrypted credential storage`
* **Uses** '`Keychain`' (`iOS`) **and** '`Keystore`' (`Android`)
* `Supports` `biometric auth`

`Install`:

```bash
npm install react-native-keychain
```

`Link` (`if needed`):

```bash
npx pod-install
```

**Usage**:

```js
import * as Keychain from 'react-native-keychain';

await Keychain.setGenericPassword('username', 'secretToken');

const credentials = await Keychain.getGenericPassword();
if (credentials) {
  console.log('Token:', credentials.password);
}

await Keychain.resetGenericPassword();
```

---

### Which should you use?

* **Using Expo?** → '`expo-secure-store`'
* **Using bare React Native?** → '`react-native-keychain`'

`Both` **are** `production-safe` options `for handling` `sensitive data` **securely**.