---
id: 7l1cromh0pp4yiha7sf6gvi
title: Drawer Navigator
desc: ''
updated: 1747611697257
created: 1747610705952
---

A `Drawer Navigator` `adds a side panel` (**usually** `from the left`) that **can** `slide in and out`, **typically** `containing navigation links`. It's great `for` **apps with** `multiple sections` **but** `limited screen space`.

---

## Install dependencies

If using **Expo**:

```bash
npx expo install @react-navigation/drawer react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context
```

For `React Native CLI` (non-Expo):

```bash
npm install @react-navigation/drawer react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context
npx pod-install
```

Also, **make sure these lines are added in your** `entry file` (**usually '`index.js`'**) `for gesture handling`:

```js
import 'react-native-gesture-handler';
```

---

## Basic usage example

```js
// App.js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import HomeScreen from './screens/HomeScreen';
import ProfileScreen from './screens/ProfileScreen';

const Drawer = createDrawerNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Drawer.Navigator initialRouteName="Home">
        <Drawer.Screen name="Home" component={HomeScreen} />
        <Drawer.Screen name="Profile" component={ProfileScreen} />
      </Drawer.Navigator>
    </NavigationContainer>
  );
}
```

---

### Example Screens

```js
// screens/HomeScreen.js
import React from 'react';
import { View, Text } from 'react-native';

export default function HomeScreen() {
  return (
    <View>
      <Text>Home Screen</Text>
    </View>
  );
}
```

```js
// screens/ProfileScreen.js
import React from 'react';
import { View, Text } from 'react-native';

export default function ProfileScreen() {
  return (
    <View>
      <Text>Profile Screen</Text>
    </View>
  );
}
```