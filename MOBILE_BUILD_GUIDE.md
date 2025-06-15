# Building the Flutter Mobile App

This guide explains how to build an APK for the Blog Platform mobile app.

## Prerequisites

- Flutter SDK installed and configured
- Android Studio or Visual Studio Code with Flutter extensions
- Android SDK installed
- A connected Android device or emulator

## Build Steps

### 1. Navigate to the mobile directory

```bash
cd /Users/krish/Desktop/Blog-Platform/mobile
```

### 2. Make sure all dependencies are up to date

```bash
flutter pub get
```

### 3. Build the APK

For a debug APK:

```bash
flutter build apk --debug
```

For a release APK:

```bash
flutter build apk --release
```

### 4. Locate the built APK

The APK will be located at:

```
/Users/krish/Desktop/Blog-Platform/mobile/build/app/outputs/flutter-apk/app-release.apk
```

### 5. Create an APK directory in the project root (optional)

```bash
mkdir -p /Users/krish/Desktop/Blog-Platform/apk
cp /Users/krish/Desktop/Blog-Platform/mobile/build/app/outputs/flutter-apk/app-release.apk /Users/krish/Desktop/Blog-Platform/apk/
```

## Installing the APK on a Device

### Via USB

1. Connect your Android device to your computer via USB
2. Enable USB debugging on your device
3. Run:

```bash
flutter install
```

### Manual Installation

1. Transfer the APK to your Android device
2. Navigate to the APK file on your device
3. Tap on it and follow the installation prompts

## Troubleshooting

### Build Errors

If you encounter build errors, try:

```bash
flutter clean
flutter pub get
flutter build apk
```

### Signing Issues

For release builds, you may need to configure signing:

1. Create a keystore:

```bash
keytool -genkey -v -keystore ~/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key
```

2. Create a `key.properties` file in the `android` directory:

```
storePassword=<password>
keyPassword=<password>
keyAlias=key
storeFile=<path to key.jks>
```

3. Update `android/app/build.gradle` to use the signing configuration

### Device Compatibility

Ensure your app's `minSdkVersion` in `android/app/build.gradle` is compatible with your target devices.