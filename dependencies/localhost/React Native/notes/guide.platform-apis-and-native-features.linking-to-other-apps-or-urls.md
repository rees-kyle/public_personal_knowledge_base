---
id: c7ao5t2n73k4afh3ltke1g0
title: 2 - Linking to Other Apps or URLs
desc: ''
updated: 1747885627734
created: 1747885379001
---

React Native’s `Linking module` **lets you**:

* `Open URLs in` the `device’s web browser`
* `Deep link into` `other apps`
* `Check if` **a** `URL` `can be handled`

---

`Import` the `module`:

```js
import { Linking } from 'react-native';
```

---

`Opening` a `URL in` the `browser`:

```js
Linking.openURL('https://example.com')
  .catch(err => console.error('Failed to open URL:', err));
```

---

`Opening` `other apps` **via** `deep links`:

```js
Linking.openURL('mailto:support@example.com');
Linking.openURL('tel:1234567890');
Linking.openURL('sms:1234567890?body=Hello');
```

---

`Checking if` a `URL` `can be opened`:

```js
Linking.canOpenURL('https://example.com').then(supported => {
  if (supported) {
    Linking.openURL('https://example.com');
  } else {
    console.log("Don't know how to open URI: " + url);
  }
});
```

---

`Listening to` `deep links`:

```js
useEffect(() => {
  const handleDeepLink = (event) => {
    const url = event.url;
    console.log('Received deep link:', url);
    // You can navigate based on the URL
  };

  const subscription = Linking.addEventListener('url', handleDeepLink);

  return () => {
    subscription.remove();
  };
}, []);
```