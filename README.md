# Word Bubble Pop (Android + iOS)

A spelling game for kids: look at the picture, pop the letter bubbles in the correct order, and complete the word within 20 seconds.

- App ID: `com.deeksha.wordbubblepop`
- Game code: `www/index.html` (HTML + CSS + JavaScript)
- Android project: `android/` | iOS project: `ios/`
- Built with **Capacitor**: the same web game packaged inside a native app.

## Prerequisites (one-time setup)

Node.js 22+ must be installed on your Mac. Then open Terminal in this folder and run:

```
npm install
```

After making any change to the game (`www/index.html`), run the following so both apps are updated:

```
npx cap sync
```

## Android APK — Method 1: Via GitHub (no Android Studio needed)

1. Create a new **private** repository on github.com and upload/push this entire folder to it.
2. In the repo, open the **Actions** tab → **Build Android APK** → **Run workflow**.
3. After 5–8 minutes the run will finish. Open the run, scroll down to **Artifacts**, and download `word-bubble-pop-apk`.
4. Inside the zip is `app-debug.apk`. Send it to an Android phone (WhatsApp/Drive) and install it
   (the phone will ask for "unknown apps" permission — allow it).

## Android APK — Method 2: Via Android Studio

1. Install Android Studio (**Mac with Apple chip** version).
2. Run `npm run android` — the project will open in Android Studio.
3. Press ▶ **Run** at the top (emulator or a USB-connected phone).
4. If you only need the APK: **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.

## iOS App (iPhone)

iOS apps can only be built on a Mac with **Xcode** (Apple's requirement).

1. Install **Xcode** from the App Store and open it at least once.
2. Run `npm run ios` — the project will open in Xcode.
3. On the left, select the **App** project → **Signing & Capabilities** → choose your Apple ID under **Team**
   (a free Apple ID is enough to run it on your own phone).
4. Connect your iPhone via USB, select your iPhone as the device at the top, and press ▶ **Run**.
5. First time on iPhone: go to **Settings → General → VPN & Device Management** and **Trust** the developer.
   (On iOS 16+, also enable **Settings → Privacy & Security → Developer Mode**.)

An app signed with a free Apple ID works for 7 days, after which you need to Run again from Xcode.
Publishing to the App Store requires the Apple Developer Program ($99/year).

## Before publishing to the stores

- For Google Play you need to build a **signed release** (AAB): Android Studio → **Build → Generate Signed App Bundle**.
- This is a kids' app, so follow the **Families policy** on Play Console and the **Kids category** rules on the App Store.
- App icon and splash screen are in the `assets/` folder. To replace them, drop new PNG files there and run:
  `npx capacitor-assets generate --android --ios`
