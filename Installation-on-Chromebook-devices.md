By default ChromeOS won't allow to install an application that's not on the (Android) Play Store or the Chrome Web Store. You can workaround this using two different methods:

## 1. Install the Debian package.

You'll need to enable support for Linux apps on your chromebook. Then go to releases and download the debian package for your arch. (amd64 for Intel based Chromebooks, arm64 for arm ones)

Double clicking the "deb" file on your chromebook will prompt you to install the app.

### 1.1 Known limitations:

- Battery will report 0% of charge (unable to fix, SDL doesn't know we're running on ChromeOS)

## 2. Install the Android package.

You can follow [this guide](https://beebom.com/how-sideload-android-apps-chromebook/) and sideload the android apk. Check your chromebook arch. Most of them are based on Intel and you'll need the x86 apk.

### 2.1 Known limitations:

- OTA updates are broken unless you're on Developer mode.
- Certain UI features have no effect when the app is running on ChromeOS (ie: brightness control)


## Which I should choose?

When in doubt choose the Debian version. It is easier to install and to keep updated, works on multiwindow mode and you can type with your physical keyboard.

If you're already on developer mode and/or want to improve the android port behaviour on ChromeOS you can try the android APK. In that case please don't open new tickets on this repo issue tracker. Just edit this wiki entry and add your issue to the list of *known limitations*