---
id: q4ksonyztjii9sdqvahoery
title: 3 - Publishing to Play Store / App Store
desc: ''
updated: 1750198629656
created: 1750093251120
---

Publishing is **the final step** that `makes` **your** `app` `publicly available to users` `through official app stores`: Google Play for Android and App Store for iOS.

---

### 📤 Publish to Google Play Store (`Android`)

#### 1. **Prepare Your App**

* `Use './gradlew bundleRelease'` **to generate a '.aab'** (Android App Bundle)
* `Sign the app` **using a keystore**
* `Set up` `app versioning` **in 'android/app/build.gradle'**:

  ```groovy
  versionCode 1
  versionName "1.0"
  ```

#### 2. **Create a Google Play Developer Account**

* `Go to` [play.google.com/console](https://play.google.com/console)
* `One-time fee`: **\$25 USD**

#### 3. **Create a New App**

* `Add` `app details`: **name, description, icon, screenshots, etc.**
* `Choose` a `release track`: **internal, closed, open, or production**

#### 4. **Upload AAB**

* Upload your '.aab' file `under "Releases > Production"`
* `Complete` `content ratings`, `privacy policy`, `data safety` section

#### 5. **Submit for Review**

* `After` `passing checks and review`, your `app is published`.

---

### 📤 Publish to Apple App Store (`iOS`)

#### 1. **Prepare Your App**

* **Use** `Xcode` `to Archive` the `app` (**release build**)
* `Requires`:

  * `Apple Developer Account` (**$99/year**)
  * `Signing certificate`
  * `Provisioning profile`

#### 2. **Create App in App Store Connect**

* `Go to` [appstoreconnect.apple.com](https://appstoreconnect.apple.com/)
* `Register your app’s` `bundle ID`, `name`, **and** `metadata`

#### 3. **Upload via Xcode or Transporter**

* From **Xcode**: `Product > Archive > Distribute App`
* **Or** use the **Transporter** app to `upload '.ipa'`

#### 4. **Complete App Info**

* Fill out app `description`, `screenshots`, `icons`, `privacy practices`, `age rating`

#### 5. **Submit for Review**

* `Apple reviews` your app (**usually** `1–3 days`)
* Once approved, it becomes available on the App Store