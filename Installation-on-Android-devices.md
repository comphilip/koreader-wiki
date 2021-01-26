KOReader isn't currently available on the Google Playstore. It will need to be installed from other sources.

1. Enable [installation from unknown sources](https://www.androidcentral.com/unknown-sources)

2. Install KOReader

    2.1 **From F-Droid**: if you have F-Droid installed, you can install KOReader just by searching for the package inside Fdroid.

    **Note:** Stable releases only

    2.2 **From your device**: download the latest release package using the browser on your device and open the package once downloaded. It will prompt you to start the installation.

    2.3 **From your computer**: download the latest release package to your computer. Once it is downloaded you can install it using `adb` with the command `adb install koreader-*.apk`


## Err, there are two Android packages to choose from, which one should I pick?

The Android package names indicate the architecture supported by the binaries. Unless you have a specific reason not to, you should choose ARM.

If you have `adb` installed, you can get that information with the command `adb shell cat /proc/cpuinfo`