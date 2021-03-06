Koreader supports different screensaver (or device status options, i.e. suspended, powered off, rebooting).

Options for suspended status can be access through menu (Menu-Gear icon-Screensaver) and through file settings.reader.lua (in koreader's root directory, i.e. where koreader is installed).

Options with settings are:

**suspend_screensaver_type** = "random_image" or "single", "message", "cover", "bookstatus", "readingprogress", "disable",

**suspend_screensaver_dir** = "path to same as screensaver_dir or alternate dir for poweroff image(s)",

**suspend_screensaver_message** = "message to use instead of Suspended",

**poweroff_screensaver_type** = "random_image" or "single", "message", "cover", "bookstatus", "readingprogress", "disable",

**poweroff_screensaver_dir** = "path to same as screensaver_dir or alternate dir for poweroff image(s)",

**poweroff_screensaver_message** = "message to use instead of Powered off",

**reboot_screensaver_type** = "random_image" or "single", "message", "cover", "bookstatus", "readingprogress", "disable",

**reboot_screensaver_dir** = "path to same as screensaver_dir or alternate dir for reboot image(s)",

**reboot_screensaver_message** = "message to use instead of Rebooting...",

You can also use screenshot for screensaver, as it is described [here.](https://github.com/koreader/koreader/pull/4113)


***

The next ones are Kobo only:

**auto_suspend_timeout_seconds** = value in seconds

**ignore_power_sleepcover** = true/false

Before editing settings.reader.lua it is best to make backup copy. When editing follow syntax rules, as errors in syntax will cause deletion of settings.reader.lua file and creating new one with default settings.

Example settings within settings.reader.lua:

> ["auto_suspend_timeout_seconds"] = 900,

# Screensaver message with additional info

Screensaver message can have additional info, like percentage read, page number, title...

![](https://user-images.githubusercontent.com/52647914/61449321-38caba80-a987-11e9-927a-ad8833f1389d.png)

![](https://user-images.githubusercontent.com/52647914/61422734-9509ec00-a93f-11e9-93e4-0202877a1f2a.jpg)