By default ChromeOS won't allow to install an application that's not on the (Android) Play Store or the Chrome Web Store. You can workaround this using two different methods:

## 1. Install the Debian package.

You'll need to enable support for Linux apps on your chromebook. Then go to releases and download the debian package for your arch. (amd64 for Intel based Chromebooks, arm64 for arm ones)

Double clicking the "deb" file on your chromebook will prompt you to install the app.

## 2. Install the Android package.

You can follow [this guide](https://beebom.com/how-sideload-android-apps-chromebook/) and sideload the android apk. Check your chromebook arch. Most of them are based on Intel and you'll need the x86 apk.

## Which I should choose?

Some features like sharing chunks of text or doing lookups in thirdparty apps are just available on the Android app. The rest should be almost the same. The Linux/Debian version works fine in multi window mode, while the Android version will only work at fullscreen.

If you don't need these specific android features the suggestion would be the Debian package. It is easier to install and require less fiddling with your device. If you go the android install route you'll get a nasty message on the login window saying that the machine could have apps not verified by Google.