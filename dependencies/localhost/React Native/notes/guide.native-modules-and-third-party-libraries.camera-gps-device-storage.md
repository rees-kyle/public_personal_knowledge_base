---
id: k7acjyc5yt72hfjerx77043
title: 1 - Using camera, GPS, device storage, etc.
desc: ''
updated: 1748312801311
created: 1748312202541
---

React Native provides **access to native device features through community-maintained libraries**. These libraries **bridge JavaScript with native Android and iOS APIs**.

---

**Camera (using 'react-native-camera' or 'react-native-vision-camera')**:

A **popular choice** today is '`react-native-vision-camera`'.

`Install`:

```bash
npm install react-native-vision-camera
```

`Request permission` `and open` the `camera`:

```js
import { Camera } from 'react-native-vision-camera';

const getPermission = async () => {
  const permission = await Camera.requestCameraPermission();
  if (permission === 'authorized') {
    // You can render the <Camera /> component
  }
};
```

---

**GPS / Location (using '@react-native-community/geolocation' or 'react-native-geolocation-service')**:

`Install`:

```bash
npm install @react-native-community/geolocation
```

`Usage`:

```js
import Geolocation from '@react-native-community/geolocation';

Geolocation.getCurrentPosition(
  position => {
    console.log(position);
  },
  error => {
    console.warn(error.message);
  },
  { enableHighAccuracy: true, timeout: 15000, maximumAge: 10000 }
);
```

**Don't forget to** `request` `location permission` **for iOS and Android**.

---

**Device Storage (using '@react-native-async-storage/async-storage')**:

`Install`:

```bash
npm install @react-native-async-storage/async-storage
```

`Usage`:

```js
import AsyncStorage from '@react-native-async-storage/async-storage';

await AsyncStorage.setItem('key', 'value');
const value = await AsyncStorage.getItem('key');
console.log(value);
```

---

These libraries **often** `need` `extra setup` **in** '`AndroidManifest.xml`' **and** '`Info.plist`', **depending on the platform**.