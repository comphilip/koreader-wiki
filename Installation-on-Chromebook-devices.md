Recent ChromeOS versions support both Debian packages and Android APKs.

## Debian package

#### Known issues

- There's no way to hide ChromeOS bottom decoration while in tablet mode.

#### Prerequisistes

Linux support enabled on your chromebook.

#### Installation

1. Go to releases and download the debian package for your arch. (amd64/arm64 for intel/arm chromebooks).
2. Open the file and confirm installation.

## Android APK

#### Known issues

- APKs are 32bits only
- Lack of keyboard support
- Lack of multiwindow support. App is fullscreen
- ~~OTA updates don't work unless you're on developer mode~~ * ()
- ~~Brightness control has no effect when the app is running on ChromeOS~~ *

`*` Disabled in https://github.com/koreader/android-luajit-launcher/pull/328

#### Prerequisistes

Linux support enabled on your chromebook or a ChromeOS device on developer mode.

#### Installation

1. Go to releases and download the android apk for your arch. (x86/arm for intel/arm chromebooks).
2. Sideload* the application (or open it directly if you're in developer mode)

* [sideload android apps on a chromebook](https://developer.android.com/topic/arc/development-environment)

## Which I should choose?

When in doubt choose the Debian version. It is easier to install and to keep updated.

If you're already on developer mode and/or want to improve the android port behaviour on ChromeOS you can try the android APK. In that case please don't open new tickets on this repo issue tracker. Just edit this wiki entry and add your issue to the list of *known issues*. Most of them need to be handled in https://github.com/koreader/android-luajit-launcher