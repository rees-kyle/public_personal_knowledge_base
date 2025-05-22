---
id: eqqpb3zyccobs5y7iahv3zg
title: 1 - Permissions and the 'PermissionsAndroid' API
desc: ''
updated: 1747885227772
created: 1747884558889
---

In Android, certain `features` **like accessing the** `camera`, `location`, **or** `storage` `require runtime permissions`. React **Native provides the** '`PermissionsAndroid`' `API` **to handle these**.

---

`Importing` the API:

```js
import { PermissionsAndroid, Platform } from 'react-native';
```

---

`Requesting permission`:

```js
async function requestCameraPermission() {
  try {
    const granted = await PermissionsAndroid.request(
      PermissionsAndroid.PERMISSIONS.CAMERA,
      {
        title: 'Camera Permission',
        message: 'This app needs access to your camera.',
        buttonNeutral: 'Ask Me Later',
        buttonNegative: 'Cancel',
        buttonPositive: 'OK',
      }
    );

    if (granted === PermissionsAndroid.RESULTS.GRANTED) {
      console.log('Camera permission granted');
    } else {
      console.log('Camera permission denied');
    }
  } catch (err) {
    console.warn(err);
  }
}
```

---

`When to call` it:

You typically call this `on component mount` (**e.g. inside a useEffect**) `or just before` **using** `a permission-restricted feature` (**like camera access**).

---

**iOS note**:

**PermissionsAndroid is Android-only**.
**For iOS**, `permissions` **are** `handled through` `native configuration` '`Info.plist`' `and third-party libraries` **like** '`react-native-permissions`'.