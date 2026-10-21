# Quick Cleaner (Android)

A minimal dark-theme Android app built with Java. It has:
- A folder-based scan for common temporary-file names/extensions.
- A system file picker for choosing a single file.
- Confirmation dialogs before deletion.
- No broad storage permission and no root requirement.

## Important limitations
- The cleanup feature scans only a folder the user explicitly chooses.
- It matches common temporary extensions (`.tmp`, `.temp`, `.bak`, `.old`, `.log`, `.cache`, `.part`, `.crdownload`, `.swp`) and files inside folders whose paths include `temp`, `tmp`, or `cache`. Review the list carefully; extension or folder names do not guarantee a file is safe to delete.
- Android's Storage Access Framework and the selected document provider decide whether deletion is allowed. Some providers do not support deletion.
- It does not clear other apps' private caches or Android system files.
- This is an unsigned debug APK suitable for personal testing, not a Play Store release.

## Build without a computer (GitHub Actions)
1. On your phone, create a new GitHub repository named `QuickCleaner`.
2. Extract this ZIP on your phone.
3. Upload the *contents* of this folder to the repository root, including the `.github/workflows/build-apk.yml` workflow file. The repository root should contain `settings.gradle`, `build.gradle`, `gradle.properties`, `app/`, and `.github/`.
4. Open the repository's **Actions** tab. If asked, enable Actions.
5. Select **Build Quick Cleaner APK** and tap **Run workflow**. You can also commit a change to `main` to trigger a build.
6. When the workflow finishes, open the run and download the `QuickCleaner-debug-apk` artifact. GitHub downloads artifacts as a ZIP; extract it to get `app-debug.apk`.
7. Tap the APK in your phone's Files app to install it. Android may ask you to allow installation from that source. Only install APKs you built and trust.

## Local build
Requires JDK 17, Android SDK 35, and Gradle 8.9. From the project root run:
`gradle assembleDebug`
The APK is at `app/build/outputs/apk/debug/app-debug.apk`.

## Package details
- Application ID: `com.quickcleaner.app`
- Minimum Android version: Android 6.0 (API 23)
- Compile/target SDK: 35
