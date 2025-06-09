---
id: cafhegfrnnyo1i36o191arz
title: 1 - Reuse React Knowledge
desc: ''
updated: 1749481042900
created: 1749479425991
---

`React Native` **supports the** `same` **state management patterns** `as React` for the web. There’s **no need to learn anything new** here—just apply what you already know.

### useState (Local Component State)

Works the same way:

```js
import React, { useState } from 'react';
import { Text, Button, View } from 'react-native';

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <View>
      <Text>Count: {count}</Text>
      <Button title="Increase" onPress={() => setCount(count + 1)} />
    </View>
  );
}
```

---

### useEffect (Side Effects)

Identical usage `for fetching data` `or reacting to lifecycle changes`:

```js
useEffect(() => {
  console.log('Component mounted');
}, []);
```

---

### useContext (Global State/Theme)

Works the same way:

```js
const ThemeContext = React.createContext();

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Screen />
    </ThemeContext.Provider>
  );
}

function Screen() {
  const theme = useContext(ThemeContext);
  return <Text>Current theme: {theme}</Text>;
}
```

---

### Redux / Zustand / Recoil (if applicable)

**These libraries can also be used in React Native without change**. Just `make sure` `to integrate them into` **your** `component tree` as usual.

Example Redux setup will be the same:

```js
import { Provider } from 'react-redux';
import store from './store';

export default function App() {
  return (
    <Provider store={store}>
      <MainApp />
    </Provider>
  );
}
```