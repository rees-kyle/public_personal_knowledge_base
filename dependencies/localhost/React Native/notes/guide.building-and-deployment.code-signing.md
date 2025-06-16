---
id: 0esc8tys8trj51xobrboxsj
title: 2 - Code Signing
desc: ''
updated: 1750092584234
created: 1750090804900
---

Code signing is **the** `process of` `digitally signing` **your** `app's code or binary` `to prove it comes from` `a trusted source` (**you**) **and hasn't been tampered with**. It's `mandatory` `for releasing apps on` both `Android` **and** `iOS` **platforms**.

### Why Code Signing is Important:

* `Verifies` the `authenticity of` the `app`S
* `Ensures` `integrity` (**code hasn’t been modified after signing**)
* `Required by` `Google Play Store` **and** `Apple App Store`
* `Enables` `secure communication` **and** `user trust`

---

### Android Code Signing

**Uses** `a keystore file` **with** `a key alias` **and** `password`:

1. `Generate` **a** `keystore` **using** '`keytool`'
2. `Store it` **in 'android/app/'**
3. `Define keystore config` **in 'gradle.properties'**
4. `Android Gradle plugin` `handles signing` **during assembleRelease' or 'bundleRelease'**

`Signed APKs/AABs` **are** `required` `to publish on` the `Play Store`.

---

### iOS Code Signing

**Uses a** `signing certificate` `and provisioning profile` `linked to` **your** `Apple Developer account`:

1. `Xcode` **manages** `signing` `via Apple certificates`
2. `Select` **your** `team` `and provisioning profile`
3. `Configure` `automatic or manual signing`
4. `Required` **to** `build an '.ipa'` **for App Store/TestFlight or physical device**

`Without signing`, **you** `can't install` the `app on` `a real device` `or publish it`.