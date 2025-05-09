---
id: 4qqeyk01s9382xg1krvw76n
title: 1 - Installation
desc: ''
updated: 1746759570937
created: 1746751801737
---

Here’s what you need to know for **✅ Setup & Environment: Installing React Native CLI or using Expo** — especially as someone already comfortable with React:

---

### 🔧 Two Main Ways to Set Up React Native

#### **1. Expo (Beginner-Friendly & Fast Setup)**

* Great for `rapid` `development` **and** `prototyping`.
* Runs in a `managed environment`, `no` `native` `code editing`.
* `Simplifies` `device access` **like** `camera`, `location`, **and more**.

**Install Expo CLI:**

```bash
npm install -g expo-cli
```

**Create a project:**

```bash
npx create-expo-app MyApp
cd MyApp
npm start
```

* `Opens` `Metro Bundler in` **the** `browser`.**
* **Use** `Expo Go app` **on** your **phone** `to scan QR` `and run` **the** `app`.

#### **2. React Native CLI (More Customizable, Native Code Access)**

* Best `for production apps` **needing** `native modules` `or custom native code`.
* `Requires Android Studio` **and/or** `Xcode` **installed**.

**Install React Native CLI:**

```bash
npx react-native init MyApp
cd MyApp
npx react-native run-android   # for Android
npx react-native run-ios       # for iOS (Mac only)
```

> ⚠️ This requires proper setup of:

* `Android Studio` (Android **SDK**, **Emulator**)
* (macOS only) `Xcode` **for iOS** development

---

### 🆚 Expo vs React Native CLI

| Feature              | Expo                        | React Native CLI             |
| -------------------- | --------------------------- | ---------------------------- |
| Setup                | Easy                        | Complex                      |
| Native code support  | ❌ (Limited, unless ejected) | ✅                            |
| Over-the-air updates | ✅ (with Expo)               | ❌ (unless set up separately) |
| Best for             | Prototyping, MVPs           | Full-scale production apps   |

---

### ✅ Recommendation

Start with `Expo` **unless you** know you’ll **need to write custom native code or use libraries that don’t support Expo**.