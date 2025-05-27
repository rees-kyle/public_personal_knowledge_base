---
id: 7gee37ntj5lrde17z4ki21a
title: 2 - Installing native dependencies via 'npm'/'yarn' and linking
desc: ''
updated: 1748313702438
created: 1748313053067
---

`React Native libraries` `that use native code` (Java/Kotlin for Android or Objective-C/Swift for iOS) `must be linked to` your `project` **so they work correctly on both platforms**.

### Installing Native Dependencies

`Use` either `'npm' or 'yarn'`:

```bash
npm install <package-name>
# or
yarn add <package-name>
```

**Example**:

```bash
npm install react-native-device-info
```

---

### Auto-Linking (React Native 0.60+)

**React Native** now `supports` `auto-linking`, so you **usually** `don’t need to` `manually link` **libraries**:

```bash
npx pod-install
```

**This installs native dependencies for iOS by updating the 'ios/Podfile'**.

---

### Manual Linking (for older versions or special cases)

If you're using an **older React Native version** (**< 0.60**) **or a library that requires manual steps**, `use`:

```bash
npx react-native link <package-name>
```

**For example**:

```bash
npx react-native link react-native-device-info
```

`Some libraries` **also** `require edits in` `native files` (**like 'AndroidManifest.xml', 'MainApplication.java', or 'Info.plist'**).

---

### Verifying Installation

`After` `installing and linking`:

* `Rebuild` the `app`:

  * **iOS**: '`npx react-native run-ios`'
  * **Android**: '`npx react-native run-android`'
* `Check` the `library is working` `by importing and using it` `in a simple test screen`