# Idol Insight for Android

A fully offline, source-transparent Swedish companion for public information about Idol 2026. This repository contains the complete Java WebView wrapper and bundled HTML/CSS/JavaScript/research source used by the app; it does not depend on a prebuilt APK.

- Package: `se.savagelions.idolinsight`
- Version: `1.0.0` (`versionCode 1`)
- Minimum Android: 7.0 / API 24
- Target/compile SDK: 35
- Runtime permissions: none
- Network permission: none
- Dependencies: Android Gradle Plugin only; no Google Play Services, ads, analytics, trackers, or non-free libraries

## Build

Install a free/open JDK 17 and Android SDK platform/build-tools 35. With `ANDROID_HOME` set:

```sh
./gradlew --no-daemon clean assembleRelease
```

The unsigned output is `app/build/outputs/apk/release/app-release-unsigned.apk`. F-Droid supplies its own signing process. No keystore or signing secret belongs in this repository.

For a cleaner, repeatable environment, set `GRADLE_USER_HOME` to an empty directory and use the versions pinned in `build.gradle` and the Gradle wrapper. Bit-for-bit reproducibility still requires independent verification with F-Droid's exact build image; see the readiness report distributed beside this source package.

## Architecture

`MainActivity.java` configures a locked-down local WebView and serves only `file:///android_asset/index.html`. The complete web app is under `app/src/main/assets/`. External HTTPS source links are delegated to the system browser.

## Licensing

Code and original authored text: GPL-3.0-or-later. Original project artwork/store graphics: CC BY-SA 4.0. Public facts, third-party trademarks, source URLs and third-party material are not relicensed; see `COPYING`, `NOTICE`, and `SOURCE-LICENSE-INVENTORY.md`.
