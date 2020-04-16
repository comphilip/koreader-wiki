## Which Kobo Devices ? 

These instructions apply to the following devices:

Touch, Mini, Glo, Aura, Glo HD, Aura HD, Aura H2O, Touch 2.0, Aura One, Aura Edition 2, Aura H2O Edition 2, Clara HD, Forma, Libra H2O

## Important Notes

NOTE1: For proper Kobo **Libra H2O support**, you'll need to use KOReader version *2019.10* or newer.
 
NOTE2: Remember that since FW 4.17, Nickel will attempt to index content found in hidden directories. Whatever your choosen installation method double check your kobo configuration file, that is  ".kobo/Kobo/Kobo eReader.conf" . It should contain:

	[FeatureSettings]
	ExcludeSyncFolders=\\.(?!kobo|adobe).*?

NOTE3: Remember that a new released Kobo Firmware update, will disable the launcher (Kfmon or KSM), so you'll have to reinstall it


## Method to choose from

### Semi-Automated Installation Method:

This should be the most logical choice for brand new users (with no other launcher currently installed on their device).
You'll be using the so called "one-click" install packages, a zip archive bundling:
- Koreader and/or Plato
- [**KFMon**](https://github.com/NiLuJe/kfmon)

There are two options to choose from:

#### Option 1: manually extract the zip archive 

Refer to [the dedicated forum thread](https://www.mobileread.com/forums/showthread.php?t=314220)

#### Option 2: run a small script to automate the process

Refer to [the second post it the dedicated forum thread](https://www.mobileread.com/forums/showpost.php?p=3797096&postcount=2).


### Manual Installation Method based on KFMon:

- Download the latest [install package](http://www.mobileread.com/forums/showthread.php?t=274231) for [**KFMon**](https://github.com/NiLuJe/kfmon).
- Extract the full content of this archive into the *root* directory of your device (i.e., not under *any* subdirectory).
- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.
- Extract the `koreader` folder of the zip into the `.adds` directory of your device (a directory which may have just been created by KFMon's archive).
- You'll probably want to [prevent Nickel from scanning our custom directories](https://github.com/NiLuJe/kfmon/blob/812b7dc46eef92772c8a5f756a92a54e1c7f6c37/tools/install.sh#L85-L99), too.
- Eject & unplug your device. Nickel should then appear to be processing a book, before restarting to process an update.

You'll then be able to simply tap the KOReader icon in your Home or your Library to launch KOReader!


### Alternative Manual Installation Method based on Kobo Start Menu:
- Install [**Kobo Start Menu**](https://www.mobileread.com/forums/showthread.php?t=293804).
- Download the latest [release](https://github.com/koreader/koreader/releases) of KOReader.  
***This assumes that KSM actually supports your device, which may not be a given for recent devices, check the current KSM post first!***
- Extract the `koreader` folder of the zip into the `.adds` directory of your device. If you are using a version of KSM older than version 8, please extract to the `.kobo` folder instead.

Now you should be able to select KOReader in the Kobo Start Menu.

#### Help! I'm lost. Should I choose KSM or KFmon ?

You'll find that most Kobo users have chosen KSM. Part of it is because of its feature set and of its convenience, part of it is historical: the original implementation of fmon was problematic in a number of fun and interesting ways, and as such, we actively discouraged users from using it.

Nowadays, the choice could be boiled down to this question: how do you actually intend to use your Kobo?
If you spend most of your time in custom software, be it KOReader or other pieces of third-party software, you'll probably want to go with KSM.
If you spend most of your time in Nickel, Kobo's own software, KFMon will probably appeal to you, because it's much less intrusive, and works in tandem with Nickel.

On current devices, the fact that KFMon is hardware-agnostic will be a plus, as KSM is currently in maintenance mode, and as such doesn't support newer devices.

Remember that launchers (i.e., KFMon/KSM/fmon) are mutually exclusive, and while nothing really bad will happen if you mix a few of them together, it can lead to puzzling results. By design, between fmon and KFMon, only the one installed *last* will take, while KSM will always take precedence over everything else.



## What about manual updates?

No matter your original installation method, whenever you want to update KOReader, it should be sufficient to update your existing `koreader` folder with the content of that same folder from the new release.

We highly recommend that you stick with the in-app update mechanism, though ;).
