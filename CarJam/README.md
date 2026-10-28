# Car Jam 🚗

Sliding-car puzzle (like IQ Car / Rush Hour): slide cars and trucks so the red car can exit on the right.
1000 levels across 6 tiers (Beginner → Master), every one verified solvable; level 451 📷 is the board from the photo.
Drag to move, Undo, Reset, Hint (built-in solver), stars vs. the perfect move count, progress auto-saved on device (best moves, stars, and your exact board position — it resumes where you left off).

The game itself is `app/src/main/assets/index.html` — open it in any browser to play without installing.

## Get the APK

**GitHub Actions (no local setup):** push this folder to a GitHub repo → Actions → "Build APK" →
download the `CarJam-apk` artifact → copy `app-release.apk` to the phone and install
(allow "Install unknown apps" for your file manager/browser).

**Locally:** needs JDK 17+ and the Android SDK (Android Studio installs both).
```
gradle wrapper --gradle-version 8.14.3   # once, optional
./gradlew :app:assembleRelease           # or: gradle :app:assembleRelease
adb install -r app/build/outputs/apk/release/app-release.apk
```

The release build is signed with the debug key so it installs directly. For Google Play,
add your own `signingConfigs` keystore.
