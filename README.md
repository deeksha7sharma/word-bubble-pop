# Word Bubble Pop (Android + iOS)

Bachon ke liye spelling game: picture dekho, letter bubbles sahi order mein phodo, 20 second mein word poora karo.

- App ID: `com.deeksha.wordbubblepop`
- Game ka code: `www/index.html` (HTML + CSS + JavaScript)
- Android project: `android/` | iOS project: `ios/`
- Bana hai **Capacitor** se: wahi web game, app ke andar pack kiya hua.

## Shuru karne se pehle (ek baar)

Mac pe Node.js 22+ hona chahiye. Phir is folder mein Terminal kholo aur chalao:

```
npm install
```

Game mein koi bhi change karo (`www/index.html`) toh uske baad ye chalao, taaki dono apps update ho jaayein:

```
npx cap sync
```

## Android APK — Tarika 1: GitHub se (Android Studio ki zaroorat nahi)

1. github.com pe naya **private** repository banao, aur ye poora folder usme upload/push karo.
2. Repo mein **Actions** tab kholo → **Build Android APK** → **Run workflow**.
3. 5–8 minute baad run khatam hoga. Run kholo, neeche **Artifacts** mein `word-bubble-pop-apk` download karo.
4. Zip ke andar `app-debug.apk` hai. Use Android phone pe bhejo (WhatsApp/Drive) aur install karo
   (phone "unknown apps" ki permission maangega — allow karna).

## Android APK — Tarika 2: Android Studio se

1. Android Studio (**Mac with Apple chip** version) install karo.
2. `npm run android` chalao — project Android Studio mein khul jayega.
3. Upar ▶ **Run** dabao (emulator ya USB se juda phone).
4. Sirf APK chahiye toh: **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.

## iOS app (iPhone)

iOS app sirf Mac + **Xcode** se banti hai (Apple ka rule).

1. App Store se **Xcode** install karo aur ek baar kholo.
2. `npm run ios` chalao — project Xcode mein khul jayega.
3. Bayein taraf **App** project → **Signing & Capabilities** → **Team** mein apni Apple ID chuno
   (free Apple ID se bhi apne phone pe chal jaata hai).
4. iPhone USB se jodo, upar device mein apna iPhone chuno, ▶ **Run** dabao.
5. Pehli baar iPhone pe: **Settings → General → VPN & Device Management** mein developer ko **Trust** karo.
   (iOS 16+ pe **Settings → Privacy & Security → Developer Mode** bhi ON karna padega.)

Free Apple ID wali app 7 din chalti hai, phir Xcode se dobara Run karna padta hai.
App Store pe daalne ke liye Apple Developer Program ($99/saal) chahiye.

## Store pe publish karne se pehle

- Google Play ke liye **signed release** (AAB) banana hoga: Android Studio → **Build → Generate Signed App Bundle**.
- Bachon ki app hai, toh Play Console mein **Families policy** aur App Store mein **Kids category** ke rules follow karne honge.
- App icon aur splash `assets/` folder mein hain. Badalne ho toh wahan nayi PNG daalo aur chalao:
  `npx capacitor-assets generate --android --ios`
