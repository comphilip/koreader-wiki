# Pre-development:
Obtaining source code, required build tools etc are described in [readme](https://github.com/koreader/koreader/blob/master/README.md) :

* [building-prerequisites](https://github.com/koreader/koreader/blob/master/README.md#building-prerequisites)
* [getting-the-source](https://github.com/koreader/koreader/blob/master/README.md#getting-the-source)
* [for-android-devices](https://github.com/koreader/koreader/blob/master/README.md#for-android-devices)

## Build arm apk file:
`./kodev release android`

## Build x86 apk file:
`ANDROID_ARCH=x86 ./kodev build/release/run android`

Don't forget to `cd platform/android/luajit-launcher && ./mk-luajit.sh clean` when changing architectures.

More info: https://github.com/koreader/koreader/pull/3353


# Display logs
`./kodev log android`
or to see all android logs:
`adb logcat`


