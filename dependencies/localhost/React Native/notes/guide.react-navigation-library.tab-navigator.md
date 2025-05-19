---
id: ocbl0kuayutrq43cua8tov7
title: Tab Navigator
desc: ''
updated: 1747609746601
created: 1747608665192
---

Tab navigation **lets users** `switch between screens` **using** `a row of tabs`, **usually at the** `bottom of the screen`. It’s **commonly used** `for main app sections` **like** `Home`, `Search`, `Profile`, **etc**.

---

## `Installing` the required packages:

If using **Expo**:

```bash
npx expo install @react-navigation/bottom-tabs react-native-screens react-native-safe-area-context react-native-vector-icons
```

If using `React Native CLI`:

```bash
npm install @react-navigation/bottom-tabs react-native-screens react-native-safe-area-context react-native-vector-icons
npx pod-install
```

**You’ll also want to** `configure vector icons` **for proper tab icons** (especially outside of Expo).

---

Basic usage **example**:

```js
// App.js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import HomeScreen from './screens/HomeScreen';
import ProfileScreen from './screens/ProfileScreen';

const Tab = createBottomTabNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Tab.Navigator>
        <Tab.Screen name="Home" component={HomeScreen} />
        <Tab.Screen name="Profile" component={ProfileScreen} />
      </Tab.Navigator>
    </NavigationContainer>
  );
}
```

---

**Example** screen components:

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

---

**Optional**: `Add icons` to tabs using '`tabBarIcon`':

```js
// App.js
<Tab.Screen
  name="Home"
  component={HomeScreen}
  options={{
    tabBarIcon: ({ color, size }) => (
      <Ionicons name="home" color={color} size={size} />
    ),
  }}
/>
```