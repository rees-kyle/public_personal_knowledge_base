---
id: 814rktwyrftx86h9giuc7c4
title: 2 - AsyncStorage
desc: ''
updated: 1749481281155
created: 1749481093720
---

### What is AsyncStorage?

'AsyncStorage' is a **simple**, `unencrypted`, `asynchronous`, `persistent key-value storage system` — **similar to 'localStorage'** in web apps, but made for React Native.

It's **useful** `for`:

* `Caching data` `locally`
* `Saving` `user settings`
* `Storing` **small amounts of** `app state`

---

### Installation

If you’re `not using Expo`:

```bash
npm install @react-native-async-storage/async-storage
```

For `iOS`:

```bash
npx pod-install
```

If you are using `Expo`:

```bash
npx expo install @react-native-async-storage/async-storage
```

---

### Basic Usage

```js
import AsyncStorage from '@react-native-async-storage/async-storage';

// Saving data
await AsyncStorage.setItem('username', 'kyle');

// Retrieving data
const username = await AsyncStorage.getItem('username');
console.log(username);

// Removing data
await AsyncStorage.removeItem('username');
```

---

### Example: Load data when component mounts

```js
import React, { useEffect, useState } from 'react';
import { View, Text } from 'react-native';
import AsyncStorage from '@react-native-async-storage/async-storage';

export default function Example() {
  const [name, setName] = useState('');

  useEffect(() => {
    const loadName = async () => {
      const storedName = await AsyncStorage.getItem('username');
      if (storedName) {
        setName(storedName);
      }
    };
    loadName();
  }, []);

  return (
    <View>
      <Text>Stored Name: {name}</Text>
    </View>
  );
}
```