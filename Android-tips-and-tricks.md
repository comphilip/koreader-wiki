## Customize keys

KOReader supports [keymappings](https://github.com/koreader/koreader/wiki/Keymapping). While most phones and tablets use common keycodes defined by AOSP, some "closed-android" e-ink vendors use their own scheme.

**NOTE:** it is impossible for a non-launcher app to override the behaviour of the home key. The rest of physical/virtual keys can be mapped.

#### example 1: add support for the custom keys used on the [Nook Glowlight 3](https://www.mobileread.com/forums/showpost.php?p=3922840&postcount=23) (top keys as page back and bottom keys as page forward)

```lua
return {
   [139] = "LPgBack", -- Nook Left Page Back (left lower button)
   [140] = "LPgFwd",  -- Nook Left Page Forward (left upper button)
   [141] = "LPgFwd",  -- Nook Right Page Forward (right upper button)
   [142] = "LPgBack", -- Nook Right Page Back (right lower button)
}
```

#### example 2: add support for the custom keys used on the [Tolino Epos 2](https://github.com/koreader/koreader/issues/5761#issuecomment-573358732)

```lua
return {
   [21] = "LPgBack",
   [22] = "LPgFwd",
}
```

To know which keycodes are being emmited by your device please follow [this link](https://github.com/koreader/koreader/issues/5761#issuecomment-573345775)


## Customize dictionary list

Since v2019.11.69 you can customize your third party dictionary list by creating koreader/dictionaries.lua

Check the [default list](https://github.com/koreader/koreader/blob/master/frontend/device/android/device.lua#L49-L63) and create your own based on your preferences.

You can also configure an action without a specific package. In that case the application picker will be shown with all the available options.

#### example 1: a simple list with 2 dicts, the first one  will show the app picker with all the apps that can manage the "send" action. The second one will open the query in Colordict if the app is installed.

```lua
return {
    { "Generic", "App picker", true, nil, "send" },
    { "ColorDict", "ColorDict", false, "com.socialnmobile.colordict", "colordict" },
}
```

#### example 2: like example 1 but without checking if Colordict is available each time the app runs

```lua
return {
    { "Generic", "App picker", true, nil, "send" },
    { "ColorDict", "ColorDict", true, "com.socialnmobile.colordict", "colordict" },
}
```

#### example 3: open the app picker for each kind of generic intent

```lua
return {
    { "Send", "App picker (send)", true, nil, "send" },
    { "Search", "App picker (search)", true, nil, "search" },
    { "TextProcessing", "App picker (text processing)", true, nil, "text" },
}
```

## Using scripts at startup/install to apply different hyphenation patterns

From v2020.7 on KOReader can run scripts after an update and on every start.

KOReader comes in two *flavors* depending on its installation method: *fdroid* or *rocks*.

Only the *rocks* flavor can execute scripts on android. So for this trick you need to install KOReader from https://github.com/koreader/koreader/releases -> look under **assets**.

For this trick two folders on the sdcard are used:
1. If it is the first startup after an update all ```*.sh``` scripts in ```koreader/scripts.afterupdate/``` are executed.
2. On every start of KOReader all ```*.sh``` scripts in ```koreader/scripts.always/``` are executed.

#### Use different hyphenation patterns (e.g. German.pattern)

It is **important**, that your file has the same name as an existing pattern file!

1. Place your desired ```German.pattern``` file on the sdcard in the ```koreader/hyph``` directory (e.g. ```/sdcard/koreader/hyph/German.pattern```). If the ```hyph``` subdirectory does not exist, create it.

Copy the following script to ```/sdcard/koreader/scripts.afterupdate/update-pattern-afterupdate.sh```
```
#!/system/bin/sh

# $1 is the koreader user directory
# $2 is the koreader system directory

SYSTEM_DIR="$2"

# copy pattern files from user to system directory
if  [ -d "$1"/hyph ]; then
	for i in $(ls "$1"/hyph/*.pattern); do
		[[ -e "$i" ]] || break
		cp "$i" "$SYSTEM_DIR"/data/hyph/
	done
fi
```

2. If you want that KOReader updates its pattern files with newer patterns, place you new pattern file to ```/sdcard/koreader/hyp/``` and copy the following script to ```/sdcard/koreader/scripts.always/update-pattern-always.sh```

```
#!/system/bin/sh

# $1 is the koreader user directory
# $2 is the koreader system directory

HYPH_DIR="$2"/data/hyph/

#copy newer patterns from user to system directory
if [ -d "$1"/hyph ]; then
	cd "$1"/hyph/ 
	for i in $(ls *.pattern); do
		[ "$i" -nt "$HYPH_DIR"/"$i" ] && cp "$i" "$HYPH_DIR"/
	done
fi

exit 0
```