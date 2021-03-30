Koreader supports keymapping (i.e. defining different commands to physical buttons on devices with them).

To do this, you need to create document (if it doesn't already exist) `koreader/settings/event_map.lua` and there you can edit key bindings.

One example is shown [here,](https://github.com/koreader/koreader/pull/3862#issue-181100453) with example below.

`return {
   [42] = "Back"
}`

Number 42 is key value, you need to know values for physical keys. Example for Kobo Forma can be found [here.](https://github.com/koreader/koreader/issues/4446#issuecomment-451639442) Back is command you want that button to execute.

Default keymapping is in file [koreader/frontend/device/kobo/device.lua](https://github.com/koreader/koreader/blob/ea424e621ea88ef0519e86112b0373adb5b6efa2/frontend/device/kobo/device.lua#L240-L250)

```    -- NOTE: For the Forma, with the buttons on the right, 193 is Top, 194 Bottom.
    self.input = require("device/input"):new{
        device = self,
        event_map = {
            [59] = "SleepCover",
            [90] = "LightButton",
            [102] = "Home",
            [116] = "Power",
            [193] = "RPgBack",
            [194] = "RPgFwd",
        },
```

For inverting button function you change button commands like this:

```
return {
            [194] = "RPgBack",
            [193] = "RPgFwd",
 }
```

More info on this can be found [here.](https://github.com/koreader/koreader/issues/4446)