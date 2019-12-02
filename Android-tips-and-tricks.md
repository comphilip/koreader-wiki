## Customize keys

You can customize key mappings by creating koreader/settings/event_map.lua with the things to override.

#### example 1: override the camera key with a page forward event:

```lua
return {
   [27] = "LPgFwd",
}
```

#### example 2: use key 200 as the back key

```lua
return {
   [200] = "Back",
}
```

#### example 3: add support for the custom keys used on the [Nook Glowlight 3](https://www.mobileread.com/forums/showpost.php?p=3922756&postcount=18) (top keys as page back and bottom keys as page forward)

```lua
return {
   [139] = "LPgBack",
   [140] = "LPgFwd",
   [141] = "LPgBack",
   [142] = "LPgFwd",
}
```

For more information see https://github.com/koreader/koreader/issues/5558#issuecomment-548993898