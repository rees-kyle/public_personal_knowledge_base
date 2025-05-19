---
id: l73at7v9je1bn2n5oit2rin
title: 1 - Stack Navigator
desc: ''
updated: 1747608078833
created: 1747606608437
---

## What is `React Navigation`?

React Navigation is the **most popular** `routing and navigation` `library` `for React Native` **apps**.
It **helps you** `switch between screens`, `pass data`, **and** `manage app history`.

---

### `Installing` React Navigation (for Expo and CLI)

If you're using **Expo**:

```bash
npx expo install @react-navigation/native
npx expo install react-native-screens react-native-safe-area-context
npx expo install @react-navigation/native-stack
```

If you're using `React Native CLI`:

```bash
npm install @react-navigation/native
npm install react-native-screens react-native-safe-area-context
npm install @react-navigation/native-stack
npx pod-install
```

---

## `Stack Navigator`

A stack navigator **lets you** `move forward and backward` `through a stack of screens` — **like web browser history**.

**Example**: Basic Stack Navigation

```js
// App.js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import HomeScreen from './screens/HomeScreen';
import DetailsScreen from './screens/DetailsScreen';

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

**Example Screens**:

```js
// screens/HomeScreen.js
import React from 'react';
import { View, Text, Button } from 'react-native';

export default function HomeScreen({ navigation }) {
  return (
    <View>
      <Text>Home Screen</Text>
      <Button
        title="Go to Details"
        onPress={() => navigation.navigate('Details')}
      />
    </View>
  );
}
```

```js
// screens/DetailsScreen.js
import React from 'react';
import { View, Text } from 'react-native';

export default function DetailsScreen() {
  return (
    <View>
      <Text>Details Screen</Text>
    </View>
  );
}
```

---

## Key Stack Navigator `Features`

* **navigation.navigate('ScreenName')** – `move to` `a screen`
* **navigation.goBack()** – `go back` `one screen`
* `Pass parameters` via **navigation.navigate('Screen', { param: 'value' })**
* `Access` **them** `in the target screen` via **route.params**