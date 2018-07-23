Koreader supports different screensaver (or device status options, i.e. suspended, powered off, rebooting).

Options for suspended status can be access through menu (Menu-Gear icon-Screensaver) and through file settings.reader.lua (in koreader's root directory, i.e. where koreader is installed).

Options with settings are:

suspend_screensaver_type = "random_image" or "single", "message", "cover", "bookstatus", "readingprogress", "disable",

suspend_screensaver_dir = "path to same as screensaver_dir or alternate dir for poweroff image(s)",

suspend_screensaver_message = "message to use instead of Suspended",

poweroff_screensaver_type = "random_image" or "single", "message", "cover", "bookstatus", "readingprogress", "disable",

poweroff_screensaver_dir = "path to same as screensaver_dir or alternate dir for poweroff image(s)",

poweroff_screensaver_message = "message to use instead of Powered off",

reboot_screensaver_type = "random_image" or "single", "message", "cover", "bookstatus", "readingprogress", "disable",

reboot_screensaver_dir = "path to same as screensaver_dir or alternate dir for reboot image(s)",

reboot_screensaver_message = "message to use instead of Rebooting...",

The next ones are Kobo only:
auto_suspend_timeout_seconds = value in seconds
ignore_power_sleepcover = true/false

Before editing settings.reader.lua it is best to make backup copy. When editing follow syntax rules, as errors in syntax will cause deletion of settings.reader.lua file and creating new one with default settings.