---
id: y422jaie61hhmb9w3o8biyj
title: Passing Params between Screens
desc: ''
updated: 1747613037889
created: 1747612596147
---

## 1. `Pass params` with '`navigation.navigate`'

`When navigating to another screen`, you can `pass params as` **the** `second argument`:

```js
navigation.navigate('Details', {
  userId: 42,
  userName: 'Alice',
});
```

---

## 2. `Access params` in the target screen via '`route.params`'

```js
// DetailsScreen.js
import React from 'react';
import { View, Text } from 'react-native';

export default function DetailsScreen({ route }) {
  const { userId, userName } = route.params;

  return (
    <View>
      <Text>User ID: {userId}</Text>
      <Text>User Name: {userName}</Text>
    </View>
  );
}
```

---

### Full Example

```js
// HomeScreen.js
import React from 'react';
import { View, Text, Button } from 'react-native';

export default function HomeScreen({ navigation }) {
  return (
    <View>
      <Text>Home Screen</Text>
      <Button
        title="Go to Details"
        onPress={() =>
          navigation.navigate('Details', {
            userId: 42,
            userName: 'Alice',
          })
        }
      />
    </View>
  );
}
```

```js
// DetailsScreen.js
import React from 'react';
import { View, Text } from 'react-native';

export default function DetailsScreen({ route }) {
  const { userId, userName } = route.params;

  return (
    <View>
      <Text>User ID: {userId}</Text>
      <Text>User Name: {userName}</Text>
    </View>
  );
}
```