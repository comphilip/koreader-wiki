# Readme first

Developers are suggested to use the KOReader emulator on linux and mac. The only reason to develop against an android emulator is to fix or enhance the platform support.

While the minimum API supported is 14 (Ice Cream Sandwitch) there's no way to test changes on anything below API17 using emulators. So please check your changes in a real device instead.

# Pre-development:
Obtaining source code, required build tools etc are described in [readme](https://github.com/koreader/koreader/blob/master/README.md) :

* [building-prerequisites](https://github.com/koreader/koreader/blob/master/README.md#building-prerequisites)
* [getting-the-source](https://github.com/koreader/koreader/blob/master/README.md#getting-the-source)
* [for-android-devices](https://github.com/koreader/koreader/blob/master/README.md#for-android-devices)

## setup Android paths:
add `emulator` path to your paths (to start AVD without Android Studio):
> export PATH=$PATH:'~/Android/Sdk/tools' ; 

`~/Android/Sdk/tools` that's default path to `emulator` (from Android Studio)

# Build APK

Release APKs are not signed. You need to sign them before install. See [apksigner](https://developer.android.com/studio/command-line/apksigner). Debug packages are signed with AOSP test keys and are recommended for development and debugging.

## Build arm apk file:

### release
`./kodev release android`

### debug
`./kodev release --debug android`

## Build x86 apk file:

### release
`ANDROID_ARCH=x86 ./kodev release android`

### debug
`ANDROID_ARCH=x86 ./kodev release --debug android`

Don't forget to `cd platform/android/luajit-launcher && ./mk-luajit.sh clean && cd -` when changing architectures.

More info: https://github.com/koreader/koreader/pull/3353

## Lint for kotlin:

```
cd platform/android/luajit-launcher
make lint
```

# Start emulator:
```
emulator -avd {avd_name}
```
If the emulator won't start on your system, try preloading the relevant libstdc++ for your system:
```
LD_PRELOAD='/usr/$LIB/libstdc++.so.6' emulator -avd Nexus_5X_API_23
```

**Note:** Some emulators are broken for different reasons. Please check known working emulator at the end of this document.

# Install generated apk on device:
`./kodev run android` will automatically take care of it for you, but besides installing the APK through the usual means (e.g., dragging it onto the emulator, copying it over to the device and manually installing it) you can also run ADB yourself:

```
adb install koreader-android-arm-linux-androideabi-{version_id}.apk
```

Note: You need to have adb in system path (In ubuntu `sudo apt install android-tools-adb`.)
Emulator has to be the same architecture (ARM Koreader on ARM AVD) otherwise you will get error here complaining about inconsistent architecture.

# Display logs
`./kodev log android`
or to see all android logs:
`adb logcat`

# Debugging

Basic principle explained in https://mhandroid.wordpress.com/2011/01/25/how-cc-debugging-works-on-android/

See some notes on using gdb [here](https://github.com/koreader/koreader/issues/3385#issuecomment-453240707).

Run `ndk-gdb` from `platform/android/luajit-launcher`. You'll need that in your `$PATH`:

```sh
export PATH=$PATH:whatever/android-ndk-r15c/prebuilt/linux-x86_64/bin
```

Diff to work around error:
```diff
--- android-ndk-r15c-orig/build/gmsl/__gmsl     2017-07-21 11:03:50.000000000 +0200
+++ android-ndk-r15c/build/gmsl/__gmsl  2019-01-10 21:20:16.847568638 +0100
@@ -509,7 +509,7 @@
 # Arguments: 1: A number in human-readable integer form
 # Returns:   Returns the integer encoded as a string of x's
 # ----------------------------------------------------------------------------
-int_encode = $(__gmsl_tr1)$(wordlist 1,$1,$(__gmsl_input_int))
+int_encode = $(__gmsl_tr1)$(wordlist 1,$(words $1),$(__gmsl_input_int))
 
 # The arithmetic library functions come in two forms: one form of each
 # function takes integers as arguments and the other form takes the
```

Without a rooted device you can't browse around in /data but you can execute commands like this:
```
adb exec-out run-as org.koreader.launcher ls /data/user/0/org.koreader.launcher/files/
```

# Android Background

## API levels

We try to maintain compatibility with API level 14.

Android version | API level | Working x86 emulator
--- | --- | ---
Android 11.0 | 30 | Yes
Android 10.0 | 29 | No
Android 9.0 | 28 | No
Android 8.0 | 26 | No
Android 7.1 | 25 | Yes
Android 6.0 | 23 | Yes
Android 5.0 | 21 | No
Android 4.3 | 18 | No
Android 4.2 | 17 | Yes
Android 4.1 | 16 | No
Android 4.0.3, 4.0.4| 15 | No
Android 4.0, 4.0.1, 4.0.2 | 14 | No

https://developer.android.com/guide/topics/manifest/uses-sdk-element.html#ApiLevels

# References:
* https://github.com/koreader/koreader/issues/3148#issuecomment-330079180
* https://github.com/koreader/koreader/blob/master/README.md
* https://github.com/koreader/koreader/issues/3385
