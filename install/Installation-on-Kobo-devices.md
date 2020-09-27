## Which Kobo Devices? 

The full Kobo lineup is currently supported, starting from the Touch.

## Important Notes
 
NOTE: On FW >= 4.17, Nickel will attempt to index content found in hidden directories. KOReader happens to live in one of those ;).  
If you choose to install KOReader manually, *start* by double-checking that your Kobo configuration file (`.kobo/Kobo/Kobo eReader.conf`) contains:

```
[FeatureSettings]
ExcludeSyncFolders=\\.(?!kobo|adobe).*?
```
See [#5430](https://github.com/koreader/koreader/issues/5430) for more details.

----

KOReader can be installed in multiple ways, some of which will be detailed below in order of simplicity & compatibility.
Most new users should stick to the first one, which relies on a semi-automated install script.

### Semi-Automated Installation Method:

- Refer to [the dedicated forum thread](https://www.mobileread.com/forums/showthread.php?t=314220), in particular [the second post](https://www.mobileread.com/forums/showpost.php?p=3797096&postcount=2), which provides a script to automate the process, including dealing with the FW 4.17+ quirk mentioned above.  
This bundles both [**KFMon**](https://github.com/NiLuJe/kfmon) and [**NickelMenu**](https://www.mobileread.com/forums/showthread.php?t=329525), and should be the most logical choice for brand new users (with no other launcher currently installed on their device).

----

### Manual Installation Method based on KFMon:

- Download the latest [install package](http://www.mobileread.com/forums/showthread.php?t=274231) for [**KFMon**](https://github.com/NiLuJe/kfmon).
- Extract the full content of this archive into the *root* directory of your device (i.e., not under *any* subdirectory).
- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.
- Extract the `koreader` folder of the zip into the `.adds` directory of your device (a directory which may have just been created by KFMon's archive).
- You'll probably want to [prevent Nickel from scanning our custom directories](https://github.com/NiLuJe/kfmon/blob/812b7dc46eef92772c8a5f756a92a54e1c7f6c37/tools/install.sh#L85-L99), too (see [the note above](https://github.com/koreader/koreader/wiki/Installation-on-Kobo-devices#important-notes)).
- Eject & unplug your device. Nickel should then appear to be processing a book, before restarting to process an update.

You'll then be able to simply tap the KOReader icon in your Home or your Library to launch KOReader!

----

### Alternative Manual Installation Method based on NickelMenu:

*This method requires KOReader 2020.05+ and firmware 4.6+.*

- Install [**NickelMenu**](https://www.mobileread.com/forums/showthread.php?t=329525) ([KoboRoot.tgz](https://github.com/pgaskin/NickelMenu/releases/latest/download/KoboRoot.tgz), [Code](https://github.com/pgaskin/NickelMenu)).
- Download the latest KOReader [release](https://github.com/koreader/koreader/releases).
- Extract the `koreader` folder of the zip into the `.adds` directory of your device. You'll probably also want to [prevent Kobo from scanning hidden folders on 4.17+](#important-notes).
- Create a new file, `.adds/nm/koreader`, with the contents `menu_item:main:KOReader:cmd_spawn:quiet:exec /mnt/onboard/.adds/koreader/koreader.sh`.
- Eject & unplug your device. Nickel should restart, and you should have a new `KOReader` item in the main menu.

You can open KOReader directly from the main menu in the top-left of the home screen.

----

### Deprecated Alternative Manual Installation Method based on Kobo Start Menu:
- KSM is in maintenance mode. Only go this route if you *absolutely* know what you're doing.
- Install [**Kobo Start Menu**](https://www.mobileread.com/forums/showthread.php?t=293804).
- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.  
***This assumes that KSM actually supports your device, which may not be a given for recent devices, check the current KSM post first!***  
**Basically, if you have a Clara or something newer, forget it: support for those in KSM ranges from minimal to overtly broken, with a host of small wondrous broken quirks in between.**
- Extract the `koreader` folder of the zip into the `.adds` directory of your device. If you are using a version of KSM older than version 8, please extract to the `.kobo` folder instead.

Now you should be able to select KOReader in the Kobo Start Menu.

----

## Help! I'm lost. Which method should I follow?

You'll find that most long-time Kobo users with older devices had chosen KSM at the time. Part of it was because of its feature set and of its apparent convenience, part of it was historical: the original implementation of fmon was problematic in a number of fun and interesting ways, and as such, we actively discouraged users from using it.

Nowadays, the choice could be boiled down to this question: how do you actually intend to use your Kobo?  
If you have an older device and/or run an older firmware version, and spend most of your time in custom software, be it KOReader or other pieces of third-party software, then KSM might be a good fit for you, but remember that it's deprecated, so you may actually have better alternatives available to you.  
For most every other user, especially if you spend some/most of your time in Nickel, Kobo's own software, NickelMenu & KFMon will probably be a better fit, because they're much less intrusive, and integrate directly with Nickel.

On current devices, the fact that NickelMenu & KFMon are hardware-agnostic will be a plus, as KSM is currently in maintenance mode, and as such doesn't support newer devices and/or FW.

Remember that launchers (i.e., KFMon/KSM/fmon) are mutually exclusive, and while nothing really bad will happen if you mix a few of them together, it can lead to puzzling results. By design, between fmon and KFMon, only the one installed *last* will take, while KSM will always take precedence over everything else. NickelMenu should not conflict with most of them, but pairing it with KSM may lead to undefined behavior.

----

## What about manual updates?

No matter your original installation method, whenever you want to update KOReader, it should be sufficient to update your existing `koreader` folder with the content of that same folder from the new release.

We highly recommend that you stick with the in-app update mechanism, though ;).

## What about official firmware updates?

They're entirely safe to install (in fact, we highly recommend doing so, especially on newer devices).  
You just need to be aware that applying an official FW update will disable [**KFMon**](https://github.com/NiLuJe/kfmon), so, if you happen to be using it, you'll need to reinstall it (either manually, or via the automated script mentioned above).
