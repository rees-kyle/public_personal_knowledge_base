---
id: gvkvly88gnt5g86jwlm86hv
title: 2 - Differences
desc: ''
updated: 1746760621955
created: 1746759888674
---

Here are the **key differences between Expo and React Native CLI**, focused on what matters most for a React developer transitioning to React Native:

---

### 🚀 **Expo vs React Native CLI – At a Glance**

| Feature                   | **Expo**                                    | **React Native CLI**                      |
| ------------------------- | ------------------------------------------- | ----------------------------------------- |
| **Setup**                 | Very `easy` (no native setup needed)          | `Complex` (requires Android Studio / Xcode) |
| **Native Code Access**    | ❌ Not by default (requires "ejecting")      | ✅ Full access to native iOS/Android code  |
| **Library Compatibility** | `Limited` to Expo-compatible libraries        | `Supports all` React Native libraries       |
| **App Size**              | `Larger` due to bundled SDK                   | `Smaller` and `more customizable`             |
| **OTA Updates**           | ✅ Built-in with Expo                        | ❌ Must configure manually                 |
| **Performance**           | Slightly `less optimized`                     | Can be `optimized more` deeply              |
| **Development Speed**     | `Faster` (hot reload, QR scan, no build time) | `Slower` (build steps for native code)      |
| **Publishing**            | `Easy` via expo publish                     | `Manual`: build APK/IPA, sign, upload       |
| **Debugging Tools**       | Expo Go app + Metro Bundler                 | Flipper, Metro Bundler, full native logs  |
| **Use Case**              | `Prototypes`, `MVPs`, `small to medium` `apps`      | `Full-featured` `production apps`             |

---

### 🧠 Key Concepts

* **Expo Go**: A `mobile app` you install on your phone `to run` **your** `app instantly` (**no building needed**).
* **Ejecting**: You can **“eject” from Expo** `if you need native modules` `not supported by Expo`. **After ejecting**, **your** `project becomes` **a** `React Native CLI project`.

---

### 📝 Summary

| Use **Expo** if...                               | Use **React Native CLI** if...           |
| ------------------------------------------------ | ---------------------------------------- |
| You want to `get started fast`                     | You need `full native code access`         |
| You don’t want to mess with Xcode/Android Studio | You’re building a `complex or large app`   |
| You’re making a `prototype or MVP`                 | You’re launching a `production-grade app`  |
| You're okay with some `limitations`                | You need `maximum control and flexibility` |