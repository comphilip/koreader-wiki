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

#### example 3: add support for the custom keys used on the [Nook Glowlight 3](https://www.mobileread.com/forums/showpost.php?p=3922840&postcount=23) (top keys as page back and bottom keys as page forward)

```lua
return {
   [139] = "LPgBack", -- Nook Left Page Back (left lower button)
   [140] = "LPgFwd",  -- Nook Left Page Forward (left upper button)
   [141] = "LPgFwd",  -- Nook Right Page Forward (right upper button)
   [142] = "LPgBack", -- Nook Right Page Back (right lower button)
}
```

For more information see https://github.com/koreader/koreader/issues/5558#issuecomment-548993898