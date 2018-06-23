## Touch, Mini, Glo, Glo HD, Aura HD, H2O, Aura One, Aura Edition 2, H2O²

__Recommended installation method based on Start Menu:__
- Install [**Kobo Start Menu**](https://www.mobileread.com/forums/showthread.php?t=293804).
- Download either the latest [stable version](https://github.com/koreader/koreader/releases/tag/v2015.11-stable) or one of the regular [nightly builds](https://github.com/koreader/koreader/releases) of KOReader.
**NB: For the Kobo Aura One and the Kobo Aura Edition 2, use a nightly build dated newer than October 2017. As for the Kobo H2O², you'll need one dated newer than March 2018. And for the Clara HD, you'll need something newer than mid June 2018. Assuming that KSM supports your device, which may not be a given for recent devices, check the current KSM post first!**
- Extract the `koreader` folder of the zip into the `.adds` directory of your device. If you are using a version of KSM older than version 8, please extract to the `.kobo` folder instead.

Now you should be able to select KOReader in the Kobo Start Menu.

----

__Alternate installation method based on KFMon:__

- Download the latest [install package](http://www.mobileread.com/forums/showthread.php?t=274231) for [**KFMon**](https://github.com/NiLuJe/kfmon).
- Extract the full content of this archive into the *root* directory of your device (i.e., not under *any* subdirectory).
- Download a recent [nightly build](https://github.com/koreader/koreader/releases) of KOReader.
- Extract the `koreader` folder of the zip into the `.adds` directory of your device (which may just have been created by KFMon's archive).
- Eject & unplug your device. Nickel should then appear to be processing a book, before restarting to process an update.

You'll then be able to simply select the KOReader icon in your Home or your Library to launch KOReader!

**NB:** You can also use a safe implementation of [fmon](https://github.com/baskerville/fmon) instead of KFMon, if you so desire. More detailed instructions on how to do so are available [here](https://github.com/koreader/koreader/blob/master/platform/kobo/fmon/README.txt#L12).

----

No matter your original installation method, whenever you want to update KOReader, it should be sufficient to extract the `koreader` folder, overwriting the previously installed version.

----

## Help! I'm lost. Which method should I follow?

You'll find that most Kobo users have chosen KSM. Part of it is because of its feature set and of its convenience, part of it is historical: the original implementation of fmon was problematic in a number of fun and interesting ways, and as such, we actively discouraged users from using it.

Nowadays, the choice could be boiled down to this question: how do you actually intend to use your Kobo?
If you spend most of your time in custom software, be it KOReader or other pieces of third-party software, you'll probably want to go with KSM.
If you spend most of your time in Nickel, Kobo's own software, KFMon will probably appeal to you, because it's much less intrusive, and works in tandem with Nickel.

On a device that just recently came out, the fact that KFMon is hardware-agnostic may be an interesting design feature ;). (And the same applies to fmon).