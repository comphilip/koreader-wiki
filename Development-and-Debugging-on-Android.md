# Pre-development:
Obtaining source code, required build tools etc are described in [readme](https://github.com/koreader/koreader/blob/master/README.md) :

* [building-prerequisites](https://github.com/koreader/koreader/blob/master/README.md#building-prerequisites)
* [getting-the-source](https://github.com/koreader/koreader/blob/master/README.md#getting-the-source)
* [for-android-devices](https://github.com/koreader/koreader/blob/master/README.md#for-android-devices)

## setup Android paths:
add `emulator` path to your paths (to start AVD without Android Studio):
> export PATH=$PATH:'~/Android/Sdk/tools' ; 

`~/Android/Sdk/tools` that's default path to `emulator` (from Android Studio)

## Build arm apk file:
`./kodev release android`

## Build x86 apk file:
`ANDROID_ARCH=x86 ./kodev build/release/run android`

Don't forget to `cd platform/android/luajit-launcher && ./mk-luajit.sh clean && cd -` when changing architectures.

More info: https://github.com/koreader/koreader/pull/3353

# Start emulator:
```
emulator -avd {avd_name}
```
If the emulator won't start on your system, try preloading the relevant libstdc++ for your system:
```
LD_PRELOAD='/usr/$LIB/libstdc++.so.6' emulator -avd Nexus_5X_API_23
```


# Install generated apk on device:
`./kodev run android` will automatically take care of it for you, but besides installing the APK through the usual means (e.g., dragging it onto the emulator, copying it over to the device and manually installing it) you can also run ADB yourself:

```
adb install koreader-android-arm-linux-androideabi-{verison_id}.apk
```

Note: You need to have adb in system path (In ubuntu `sudo apt install android-tools-adb`.)
Emulator has to be the same architecture (ARM Koreader on ARM AVD) otherwise you will get error here complaining about inconsistent architecture.

# Display logs
`./kodev log android`
or to see all android logs:
`adb logcat`

# Debugging

TODO : can anyone help here?

# References:
* https://github.com/koreader/koreader/issues/3148#issuecomment-330079180
* https://github.com/koreader/koreader/blob/master/README.md
* https://github.com/koreader/koreader/issues/3385
