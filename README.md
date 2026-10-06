# Haylur Organics mobile beta

Native React Native / Expo app for Android and iOS. Four screens, bundled Haylur images, category filtering, mock sign-in, sample bag with quantities, and external contact links. No backend, registration or payments. The bag is in memory and resets on restart.

## Validation

Android and iOS JavaScript bundles exported successfully with Expo SDK 57. Native installation and device testing are separate checks; an export alone is not an APK or IPA.

## Android beta

Install the declared dependencies with npm install. Then either build locally with npm run android, or log in to an Expo account and run:

```
npx eas-cli build --platform android --profile preview
```

The preview profile produces an installable APK. Keep the same signing key for later client beta updates. The Android project is included. A debug-signed APK is suitable only for the pitch demo, not a production release.

## iPhone beta through TestFlight

1. Enrol in the Apple Developer Program: https://developer.apple.com/programs/enroll/
2. Choose an individual account using your legal name, or enrol the legal organization that will own the app. Organization enrolment requires additional verification, including a D-U-N-S number.
3. Apple lists membership as USD 99 per year; the local price is shown during enrolment. Enter your Apple login, identity information, legal agreements and payment yourself.
4. Once active, sign in to Expo and configure this project with EAS. Confirm the bundle identifier and account ownership before registering the app in App Store Connect.
5. Build and submit:

```
npx eas-cli build --platform ios --profile testflight
npx eas-cli submit --platform ios --profile testflight
```

6. In App Store Connect, provide the requested beta information and invite the client as an external tester. External testing may require Apple's beta review. The client installs Apple's TestFlight app and accepts the invitation.

Never send passwords or signing secrets through chat. Native iOS building requires a Mac/Xcode or an authenticated cloud build service.

## Files

App.js contains the native UI and local sample data. app.json contains branding and app identifiers. eas.json defines the Android APK and iPhone TestFlight build profiles. All imagery is bundled in assets.
