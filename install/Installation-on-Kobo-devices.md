## Touch, Mini, Glo, Aura, Glo HD, Aura HD, H2O, Touch 2.0, Aura One, Aura Edition 2, H2O Edition 2, Clara HD, Forma

NOTE: **For proper Kobo Forma support, you'll need to use KOReader version *2019.01* or newer.**  

### Semi-Automated Installation Method:
- Refer to [the dedicated forum thread](https://www.mobileread.com/forums/showthread.php?t=314220).

This bundles KFMon, and should be the most logical choice for brand new users (with no other launcher currently installed on their device).

----

### Manual Installation Method based on Kobo Start Menu:
- Install [**Kobo Start Menu**](https://www.mobileread.com/forums/showthread.php?t=293804).
- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.  
***This assumes that KSM actually supports your device, which may not be a given for recent devices, check the current KSM post first!***
- Extract the `koreader` folder of the zip into the `.adds` directory of your device. If you are using a version of KSM older than version 8, please extract to the `.kobo` folder instead.

Now you should be able to select KOReader in the Kobo Start Menu.

----

### Alternative Manual Installation Method based on KFMon:

- Download the latest [install package](http://www.mobileread.com/forums/showthread.php?t=274231) for [**KFMon**](https://github.com/NiLuJe/kfmon).
- Extract the full content of this archive into the *root* directory of your device (i.e., not under *any* subdirectory).
- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.
- Extract the `koreader` folder of the zip into the `.adds` directory of your device (a directory which may have just been created by KFMon's archive).
- Eject & unplug your device. Nickel should then appear to be processing a book, before restarting to process an update.

You'll then be able to simply tap the KOReader icon in your Home or your Library to launch KOReader!

**NB:** You can also use a safe implementation of [fmon](https://github.com/baskerville/fmon) instead of KFMon, if you so desire. More detailed instructions on how to do so are available [here](https://github.com/koreader/koreader/blob/master/platform/kobo/fmon/README.txt#L12).

----

### What about manual updates?

No matter your original installation method, whenever you want to update KOReader, it should be sufficient to extract the `koreader` folder, overwriting the previously installed version.

----

## Help! I'm lost. Which method should I follow?

You'll find that most Kobo users have chosen KSM. Part of it is because of its feature set and of its convenience, part of it is historical: the original implementation of fmon was problematic in a number of fun and interesting ways, and as such, we actively discouraged users from using it.

Nowadays, the choice could be boiled down to this question: how do you actually intend to use your Kobo?
If you spend most of your time in custom software, be it KOReader or other pieces of third-party software, you'll probably want to go with KSM.
If you spend most of your time in Nickel, Kobo's own software, KFMon will probably appeal to you, because it's much less intrusive, and works in tandem with Nickel.

On a device that just recently came out, the fact that KFMon is hardware-agnostic may be an interesting design feature ;). (And the same applies to fmon).