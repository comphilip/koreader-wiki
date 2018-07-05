There are two configuration files that contain the initial settings for KOReader's behavior and appearance. However, the easiest way to set global default settings is actually to **long press** the option you wish to make the default.

* 1. The `defaults.lua` located at `koreader/defaults.lua`.
* 2. The `cr3.ini` located at `koreader/data/cr3.ini`, especially for EPUB/FB2 documents.

### Basic configuration
| Settings(default) | Location | Change range | Description | Affected parts |
| ------ | ------ | ------ | ------ | ------ |
| `DRCOUNTMAX = 6` | `defaults.lua` | `1` - `99` | full refresh interval for eink devices | ALL |
| `DFULL_SCREEN = 1` | `defaults.lua` | `1` or `0` | hiding progress bar | PDF/DJVU |
| `DSCROLL_MODE = 0` | `defaults.lua` | `1` or `0` | displaying pages continuously | PDF/DJVU |
| `DSHOWOVERLAP = false` | `defaults.lua` | `false` or `true` | showing gray area to indicate page overlap | PDF/DJVU |
| `DHINTCOUNT = 2` | `defaults.lua` | `0` - `3` | number of pages to render ahead in background | PDF/DJVU |
| `DCREREADER_VIEW_MODE = "page"` | `defaults.lua` | `"page"` or `"scroll"` | pagination in "page" mode, no pagination in "scroll" mode | EPUB/FB2 |
| `DCREREADER_PROGRESS_BAR = 1` | `defaults.lua` | `1` or `0` | progress bar style: `1` for "mini", `0` for "full" | EPUB/FB2 |
| `DCREREADER_CONFIG_DEFAULT_FONT_SIZE = 22` | `defaults.lua` | `16` - `44` | default font size | EPUB/FB2 |
| `DCREREADER_CONFIG_MARGIN_SIZES` | `defaults.lua` | `5` - `50` | page margins {left, top, right, bottom} in pixels | EPUB/FB2 |
| `DSHOWHIDDENFILES = false` | `defaults.lua` | `false` or `true` | showing hidden files (name begins with a ".") | FileManager |

Note that configuration changes to the `koreader/defaults.lua` file will be overridden by nightly releases / OTA updates automatically without notification. To make configuration changes persist between updates,you need to move your changes into `koreader/defaults.persistent.lua`.



# Advanced

Settings for `settings.reader.lua` file, located in `koreader` directory:

### FILE BROWSER RELATED
~~**home_dir_display_name** used by filemanagerutil.abbreviate(path) to shorten directory in title bar
    I like it, we could make it a toggle (true => "~", false => nil)
**show_file_in_bold** filemanager items in bold : true/false/"opened" https://github.com/koreader/koreader/pull/2457
**autoremove_deleted_items_from_history** https://github.com/koreader/koreader/pull/2583#issuecomment-282509524~~
 ^ available in menu since 20170825 (#3129)
**fm_screen_mode** : save of this setting was disabled by https://github.com/koreader/koreader/pull/2347
**debug** : could be added to _Developer's options_ ?

### READER RELATED

~~**auto_book_status** (nilOrTrue): show book status onEndOfBook (this annoyed me, so it could be nice for others to be able to toggle) https://github.com/koreader/koreader/issues/2363~~
 ^ available in menu since 20180130 (#3642)
**enable_back_history** (isFalse): disabled back history (#3862)
**page_gap_color** ,  **page_gap_height** ,  **page_gap_width** page separator in scroll mode https://github.com/koreader/koreader/pull/2318
**copt_overlap_lines** crengine in scoll mode with overlap enabled: number of line from bottom of previous page to show on top of next page (#3870)
**txt_preformatted** crengine plain text read mode https://github.com/koreader/koreader/pull/2702
**followed_link_marker** (false: no marker shown, true: maker shown and not auto removed, `<number>`: removed after <number> seconds) crengine link markers (#3669)
**cre_compress_cached_data** (nilOrTrue): set to false to not compress cache file, ~~speeds up loading and usage of big books~~ (#3670) - not really useful anymore
**cre_storage_size_factor** increase crengine in-memory cache size, default is 20 (#3700, #3732)
**cre_disk_cache_max_size** crengine max disk space usable for storing book caches and allow fast re-openings, default is 64 MB (#3760)
**cre_header_status_font_size** font size of the top (_full_) status bar (#3996)
~~**cre_min_space_condensing_percent** how much we can decrease a space width to make text fit on a line, default is 50, increase to 70 or 80 if words looks too stuck together on some lines (#4023)~~ now available thru bottom config (#4026)

### DICTIONARY AND WIKIPEDIA RELATED

~~**dict_justify** (nilOrTrue) : https://github.com/koreader/koreader/pull/2470 to be added to a _Dictionary settings_ submenu, with _Disable fuzzy search_
**wikipedia_languages**  : https://github.com/koreader/koreader/issues/2393 _Wikipedia settings / Set Wikipedia languages_ ~~ now available in menu
**wikipedia_save_dir** : https://github.com/koreader/koreader/pull/2507 _Wikipedia settings / Set Wikipedia 'Save as EPUB' directory_~~
 ^ available in menu since 20170822 (#3121)
**wikipedia_prettify** (nilOrTrue) : https://github.com/koreader/koreader/pull/2507 probably not useful enough to be included as a menu item 
~~(I have work ongoing to add this _Wikipedia settings_ submenu).~~

### SUSPEND, SLEEP, POWER, SCREENSAVER related
~~**poweroff_screensaver** , **reboot_screensaver** , **suspend_screensaver** :  https://github.com/koreader/koreader/pull/2349#issuecomment-261726070 a few variations related to screensaver folder/file/path/message, with many alternatives, so probably not easily configurable via menus~~ Obsoleted: replaced with the following ones (https://github.com/koreader/koreader/pull/3572):
**poweroff_screensaver_type** = "random_image" or "message", "cover", "bookstatus", "readingprogress", "disable",
**poweroff_screensaver_dir** = "path to same as screensaver_dir or alternate dir for poweroff image(s)",
**poweroff_screensaver_message** = "message to use instead of Powered off",
**reboot_screensaver_type** = "random_image" or "message", "cover", "bookstatus", "readingprogress", "disable",
**reboot_screensaver_dir** = "path to same as screensaver_dir or alternate dir for reboot image(s)",
**reboot_screensaver_message** = "message to use instead of Rebooting...",

The next ones are Kobo only:
**auto_suspend_timeout_seconds** : autosuspend.koplugin, should be available in menu, with a checkmark if 0 vs > 0 (like _Read timer_ menu item), to be added to Screen submenu ?
**ignore_power_sleepcover** https://github.com/koreader/koreader/pull/1982
_**frontlight_sync_with_nickel** : not yet implemented, https://github.com/koreader/koreader/issues/3103_

### OTHERS that can probably be ignored

**fontmap** (reader.lua) : allow for overriding fonts defined in _frontend/ui/font.lua_ ?
**show_advanced** : removed in https://github.com/koreader/koreader/pull/2610
**extra_plugin_paths** : platform stuff, probably not for endusers https://github.com/koreader/koreader/pull/2693
**trans_server** : translator_servers (not useful enough)
**kobo_touch_switch_xy** : _tools/kobo_touch_probe.lua_ ?

### ENGINE OPTIONS
**copt_embedded_css**
**copt_font_gamma**
**copt_font_size**
**copt_font_weight**
**copt_line_spacing**
**copt_page_margins**
**copt_screen_mode**
**kopt_contrast**
**kopt_screen_mode**
  engine options, either old settings, or available for custom override

There may also be a few other interesting options in https://github.com/koreader/koreader/blob/master/defaults.lua

  
  