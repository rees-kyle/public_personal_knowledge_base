---
id: 1wpbfhvkvniz81nrs5mfmrz
title: 1 - Building APK/IPA (Android/iOS binaries)
desc: ''
updated: 1749862723568
created: 1749859951435
---

####
**Creating an APK (Android) or IPA (iOS) is how you** `turn` **your** `React Native app into` `an installable file` that **users can download** or you can **test on real devices**.

> APK: Android Package

> IPA: iOS App Store Package

## Why Build APK or IPA?

* `APK` **and** `AAB` (**Android App Bundle**) are needed `to install` **your** `app on Android` `or publish it to` the `Google Play Store`.
* `IPA` is needed `to install or publish` your `app on Apple devices` **via the** `App Store` **or** `TestFlight`.
* **These are the** `production-ready` `binary files of` **your** `app`.

---

## Android: Build APK or AAB

### 1. `Generate` a `Keystore` (**for release**)

```bash
keytool -genkey -v -keystore my-key.keystore \
  -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000
```

`Place` **the** `'.keystore' file in` '`android/app/`'.

### 2. `Add to` `Gradle`

**In** '`android/gradle.properties`':

```txt
MYAPP_RELEASE_STORE_FILE=my-key.keystore
MYAPP_RELEASE_KEY_ALIAS=my-key-alias
MYAPP_RELEASE_STORE_PASSWORD=*****
MYAPP_RELEASE_KEY_PASSWORD=*****
```

### 3. `Build` the `APK`

```bash
cd android
./gradlew assembleRelease
```

**Output file**:
'`android/app/build/outputs/apk/release/app-release.apk`'

### `Build` an `AAB` (for **Play Store**)

```bash
./gradlew bundleRelease
```

Output file:
`android/app/build/outputs/bundle/release/app-release.aab`

---

## iOS: Build IPA (Mac + Xcode Required)

### 1. `Install` `CocoaPods` (if not already)

```bash
cd ios
pod install
```

### 2. `Open` Project `in Xcode`

```bash
open ios/YourProject.xcworkspace
```

* `Select` a `device target`
* `Set` `build configuration to` '`Release`'

### 3. `Archive and Export` **IPA**

* **In Xcode**: `Product > Archive`
* `Use` the `Organizer` `to export` **IPA** `or upload` **to TestFlight / App Store**

You’ll `need`:

* An `Apple Developer Account`
* A `Provisioning Profile` **and** `Signing Certificate`

---

## Summary

| Platform | File Type | Tool       | Needed For                    |
| -------- | --------- | ---------- | ----------------------------- |
| Android  | `.apk`    | Gradle CLI | **Local** `install/testing`         |
| Android  | `.aab`    | Gradle CLI | **Play Store** `upload`             |
| iOS      | `.ipa`    | Xcode      | **TestFlight / App Store** `upload` |