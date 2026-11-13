# rasa — The Future Project (Android starter)

This is a real, editable first implementation of rasa's offline-first app shell.

## What's working
- English interface and dark forest-green / muted-gold visual direction
- Home dashboard and weight-to-goal progress
- Meal journal (food, meal, grams, cooking method, notes)
- Workout mission logging with low/normal/high energy choices
- Weekly weigh-in and separate body measurements
- Profile settings and basic avatar preference selectors
- XP and levels
- Local JSON backup export/import
- Service worker cache for offline use when served/installed as a PWA

## Important limitations of this first build
- It is not a finished commercial fitness app.
- Calorie calculation, exercise video library, advanced 3D avatar, cinematic sound assets, photo tracking, charts, reminders and the full 100-chapter story are not implemented yet.
- XP currently records simple actions and is a prototype system.
- Local data lives in app/browser storage. Export backups regularly. Clearing app data can erase it.
- No account, cloud sync, subscription, paid API or analytics is included.

## Build an Android APK
This folder contains the web app and Capacitor configuration. To create the native Android wrapper, use a computer with Node.js 20+, Java 17 and Android SDK installed:

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

APK output:
`android/app/build/outputs/apk/debug/app-debug.apk`

For a signed release APK, configure your own signing key securely; never commit passwords or keystore files.

## GitHub Actions option
Upload this folder to a GitHub repository. The included workflow installs dependencies, creates the Android project, and builds a debug APK. Download it from the workflow run's Artifacts section. GitHub account/workflow availability and usage limits are controlled by GitHub.

## PWA fallback
Serve the `www` folder over HTTPS (or localhost) and use your Android browser's "Install app" / "Add to Home screen" command. Service worker offline caching requires a secure context.
