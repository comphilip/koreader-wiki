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

Check the [default list](https://github.com/koreader/koreader/blob/master/frontend/device/android/dictionaries.lua#L8-L17) and create your own based on your preferences.

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

