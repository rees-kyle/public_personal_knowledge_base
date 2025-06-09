---
id: 9gaudvl8c5wb6ttacs1vwge
title: 2 - Handling Offline Mode
desc: ''
updated: 1749505320211
created: 1749504649674
---

In React Native, you can `detect` `internet connectivity` **using the** `@react-native-community/netinfo` **library** (**or** `expo-network` if using Expo).

---

### ✅ Option 1: `@react-native-community/netinfo` (for bare React Native)

`Installation`:

```bash
npm install @react-native-community/netinfo
npx pod-install
```

**Usage**:

```js
import NetInfo from '@react-native-community/netinfo';

NetInfo.fetch().then(state => {
  console.log('Connection type:', state.type);
  console.log('Is connected?', state.isConnected);
});
```

**Subscribe to changes**:

```js
useEffect(() => {
  const unsubscribe = NetInfo.addEventListener(state => {
    console.log('Connection type:', state.type);
    console.log('Is connected?', state.isConnected);
  });

  return () => unsubscribe();
}, []);
```

---

### ✅ Option 2: `expo-network` (if using Expo)

`Install`:

```bash
npx expo install expo-network
```

**Usage**:

```js
import * as Network from 'expo-network';

const status = await Network.getNetworkStateAsync();
console.log('Is connected?', status.isConnected);
```

---

### Use Cases

* `Display` **a** `warning banner` `if offline`
* `Queue or cache` `API requests` `until back online`
* `Disable` `form submission` `when not connected`