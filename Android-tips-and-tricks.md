## Customize keys

You can override key mappings by creating koreader/settings/event_map.lua with the things to override.

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

For more information see https://github.com/koreader/koreader/issues/5558#issuecomment-548993898