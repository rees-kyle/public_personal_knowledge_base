---
id: t4k4lmyt03k95zsnyd7yp4w
title: 3 - Running Apps
desc: ''
updated: 1746839944565
created: 1746839314477
---

Here’s a guide on how to **run your React Native app** on **Android** and **iOS simulators/emulators**, depending on whether you’re using **Expo** or **React Native CLI**:

---

### 🚀 **Running on Android and iOS Simulators/Emulators**

#### **1. Running on Android Emulator (React Native CLI)**

**Prerequisites**:

* Install **Android Studio** (includes Android Emulator and SDK).
* Set up the **Android Virtual Device (AVD)** using Android Studio.

**Steps**:

1. **Install Android Studio**:

   * Download Android Studio [here](https://developer.android.com/studio).
   * Make sure the **Android Emulator** and **SDK** are included during installation.

2. **Set up the Android Emulator**:

   * Open **Android Studio**.
   * Go to **Tools > AVD Manager**.
   * Click **Create Virtual Device**.
   * Choose a device (e.g., Pixel 3) and follow the steps to create the emulator.

3. **Start the Android Emulator**:

   * Launch the emulator from **AVD Manager** or directly from Android Studio.

4. **Run your React Native App**:

   * Open a terminal in your project directory.

   * Run the following command to start the app on the emulator:

     ```bash
     npx react-native run-android
     ```

   * This will start the Metro Bundler and build the app on the Android emulator.

---

#### **2. Running on iOS Simulator (React Native CLI)**

**Prerequisites**:

* Install **Xcode** (for macOS users) via the Mac App Store.
* Set up the **iOS Simulator** using Xcode.

**Steps**:

1. **Install Xcode**:

   * Download and install **Xcode** from the Mac App Store.

2. **Set up iOS Simulator**:

   * Open **Xcode**.
   * Go to **Xcode > Preferences > Components**.
   * Download an **iOS Simulator** (if it isn’t already installed).

3. **Start the iOS Simulator**:

   * Open **Xcode** and navigate to **Xcode > Open Developer Tool > Simulator**.
   * This will launch the iOS Simulator.

4. **Run your React Native App**:

   * Open a terminal in your project directory.

   * Run the following command to start the app on the iOS simulator:

     ```bash
     npx react-native run-ios
     ```

   * This will build the app and launch it in the iOS Simulator.

---

#### **3. Running on Android Emulator (Expo)**

If you’re using **Expo**, setting up an Android emulator is not necessary as Expo runs directly on your physical device or using the **Expo Go** app.

**Steps**:

1. **Install Expo Go** on your Android device.

   * `Download` Expo Go `from` the `Google Play Store`.

2. **Run Expo App**:

   * `In the terminal`, `inside` your `project folder`, run:

     ```bash
     npm start
     ```

3. **Scan QR Code**:

   * The **Metro Bundler will open in the browser**.
   * **Scan the QR code** shown in the browser **using the Expo Go app on your Android device**.

**Expo will automatically open the app on your device** without needing an emulator.

---

#### **4. Running on iOS Simulator (Expo)**

For **iOS** with **Expo**, you can use the **Expo Go** app or run it directly on the iOS simulator.

**Steps**:

1. **Install Expo Go** on your iOS device.

   * Download Expo Go from the App Store.

2. **Run Expo App**:

   * In the terminal, inside your project folder, run:

     ```bash
     npm start
     ```

3. **Scan QR Code**:

   * The Metro Bundler will open in the browser.
   * Scan the QR code shown in the browser using **Expo Go** on your iOS device.

Alternatively, if you’re on **macOS**, you can run the app on the **iOS simulator**:

```bash
npm run ios
```

This will launch the iOS simulator and your app.

---

### 📱 **Summary**

* **Expo**: Use the Expo Go app on your device or simulator/emulator. Fastest method for running apps.
* **React Native CLI**: Install Android Studio for Android emulators, Xcode for iOS simulators. Use 'npx react-native run-android' or 'npx react-native run-ios' to launch your app.