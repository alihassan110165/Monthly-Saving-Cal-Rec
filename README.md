# My Savings Ledger — Android APK project

This is an Android Studio project for the monthly savings calculator. It wraps the calculator in an Android WebView and enables DOM storage so the app can retain monthly entries on the device.

## Easiest build route (GitHub Actions)

1. Create a GitHub account if you do not already have one.
2. Create a new repository, e.g. `MySavingsLedger`.
3. Upload the contents of this ZIP to the repository (not the ZIP file itself). Make sure `.github/workflows/build-apk.yml` is included.
4. Open the repository's **Actions** tab. Select **Build My Savings Ledger APK**, then tap **Run workflow** (or push to `main` to trigger a build).
5. When the run finishes successfully, open that workflow run and download the artifact named `MySavingsLedger-debug-apk`.
6. Extract the downloaded artifact ZIP on your phone or computer to get `app-debug.apk`.
7. Transfer/open the APK on your Android phone and approve installation from that source if Android asks. Only install APKs you built or trust.

## Build with Android Studio instead

Open this folder as a project in Android Studio, let Gradle sync, then choose **Build > Build APK(s)**. The debug APK is normally written to `app/build/outputs/apk/debug/app-debug.apk`.

## Saving and backups

- Monthly entries are stored in the app's WebView local storage on that device.
- Use the app's **Export backup (JSON)** action regularly.
- Uninstalling the app or clearing its app data can delete saved entries.
- The included APK is a debug build workflow, not a Play Store release. A production release should be signed with a private release key and tested.

## Project files

- `app/src/main/assets/index.html`: the savings calculator UI and calculations
- `app/src/main/java/com/mysavingsledger/app/MainActivity.java`: Android WebView shell
- `.github/workflows/build-apk.yml`: cloud build workflow
