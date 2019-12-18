# google_signin

Steps to remember:

- [Also generate and configure the release keystore](https://flutter.dev/docs/deployment/android)
- Make sure to add both SHA-1 and SHA-256 fingerprints for both the debug and release configs to the "settings" close to the project overview button.

## Commands to generate keystores and fingerprints

For Keystore generation:
Debug: (Do not try to generate your own)
It is located in the following directories

Linux: ~/.android/debug.keystore
Windows: C:/Users/USERNAME/.android/debug.keystore

Release:

```bash
keytool -genkey -v -keystore ~/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key
```

For Fingerprint generation:
Debug: (Do not change passwords/name/alias of the keystore)

```bash
keytool -list -v -keystore <keystore path> -alias <alias-name> -storepass <storepass> -keypass <keypass>
```

Specific to the debug fingerprints for default values

```bash
keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android
```

Release:

```bash
keytool -list -v -alias <your-key-name> -keystore <path-to-production-keystore>
```

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
