---
id: br41zukzpxnetvvisp989vj
title: 3 - Expo APIs for sensors, media, notifications (if using Expo)
desc: ''
updated: 1748320691298
created: 1748316455281
---

`Expo` `provides built-in APIs` that make it easier `to access native features` `without needing to write native code` `or install extra dependencies manually`.

### Sensors

Expo has **modules like**:

* `expo-sensors`
  **Includes** `accelerometer`, `gyroscope`, `magnetometer`, **and** `barometer`.



<!-- start of 'accelerometer' section -->
<details>
    <summary>Definition: accelerometer</summary>

#
`Measures` `how fast something is` `moving or changing direction` (`movement` **and** `tilt`).

---
</details>
<!-- end of 'accelerometer' section -->



<!-- start of 'gyroscope' section -->
<details>
    <summary>Definition: gyroscope</summary>

#
`Measures` `how something is` `rotating or turning` (`spinning motion`).

---
</details>
<!-- end of 'gyroscope' section -->



<!-- start of 'magnetometer' section -->
<details>
    <summary>Definition: magnetometer</summary>

#
`Detects` `magnetic fields`, **like a** `compass` (`shows direction` `using Earth's magnetism`).

---
</details>
<!-- end of 'magnetometer' section -->



<!-- start of 'barometer' section -->
<details>
    <summary>Definition: barometer</summary>

#
`Measures` `air pressure` (helps tell `altitude` **or** `weather changes`).

---
</details>
<!-- end of 'barometer' section -->



####
`Install`:

```bash
npx expo install expo-sensors
```

**Example** (**Accelerometer**):

```js
import { Accelerometer } from 'expo-sensors';

Accelerometer.addListener(accelerometerData => {
  console.log(accelerometerData);
});

Accelerometer.setUpdateInterval(1000); // update every 1 second
```

---

### Media

**Use** '`expo-image-picker`' `to access` `the camera roll` `or take photos`.

`Install`:

```bash
npx expo install expo-image-picker
```

**Example**:

```js
import * as ImagePicker from 'expo-image-picker';

const pickImage = async () => {
  const result = await ImagePicker.launchImageLibraryAsync({
    mediaTypes: ImagePicker.MediaTypeOptions.All,
    allowsEditing: true,
    quality: 1,
  });

  if (!result.canceled) {
    console.log(result.assets[0].uri);
  }
};
```

---

### Notifications

**Use** '`expo-notifications`' `for local and push notifications`.



<!-- start of 'local notification' section -->
<details>
    <summary>Definition: local notification</summary>

#
`Sent by` **the** `app` **itself** `on your device` `without` **using the** `internet` (**e.g. a** `reminder from` **your** `alarm` **app**).

---
</details>
<!-- end of 'local notification' section -->



<!-- start of 'push notification' section -->
<details>
    <summary>Definition: push notification</summary>

#
`Sent from a server` `to your device` `over the internet` (**e.g. a** `new message alert` `from WhatsApp`).

---
</details>
<!-- end of 'push notification' section -->



####
`Install`:

```bash
npx expo install expo-notifications
```

**Example** (**Local Notification**):

```js
import * as Notifications from 'expo-notifications';

await Notifications.scheduleNotificationAsync({
  content: {
    title: 'Hello!',
    body: 'This is a test notification.',
  },
  trigger: { seconds: 5 },
});
```

You’ll also **need to** `ask for permission`:

```js
const { status } = await Notifications.requestPermissionsAsync();
```

---

`Expo handles` **most of** `the linking` `and native setup` **for you**. This makes it **ideal** `for beginners` `or for apps that don’t require` `deep native customization`.