The easiest way to set a global default setting is from within the KOReader application &mdash; **long press** the option you wish to make the default. KOReader will ask you to confirm the new default.

For users who wish to edit config files directly, there are two such files that contain the initial settings for KOReader's behavior and appearance:

* 1. The `defaults.lua` located at `koreader/defaults.lua`.
* 2. The `cr3.ini` located at `koreader/data/cr3.ini`, especially for EPUB/FB2 documents.

### Basic configuration

A very few examples (some of these settings are actually available in the UI, too).

| Settings(default) | Location | Change range | Description | Affected parts |
| ------ | ------ | ------ | ------ | ------ |
| `DSHOWOVERLAP = false` | `defaults.lua` | `false` or `true` | showing gray area to indicate page overlap | PDF/DJVU |
| `DHINTCOUNT = 1` | `defaults.lua` | `0` - `3` | number of pages to render ahead in background | PDF/DJVU |
| `DCREREADER_VIEW_MODE = "page"` | `defaults.lua` | `"page"` or `"scroll"` | pagination in "page" mode, no pagination in "scroll" mode | EPUB/FB2 |
| `DCREREADER_CONFIG_DEFAULT_FONT_SIZE = 22` | `defaults.lua` | `16` - `44` | default font size | EPUB/FB2 |
| `DSHOWHIDDENFILES = false` | `defaults.lua` | `false` or `true` | showing hidden files (name begins with a ".") | FileManager |

Note that configuration changes to the `koreader/defaults.lua` file will be overridden by nightly releases/OTA updates automatically without notification. To make configuration changes persist between updates, you need to move your changes into `koreader/defaults.persistent.lua`.

Alternatively, you can lookup or modify these settings from within KOReader, via the *Tools* > *More tools* > *Advanced settings* menu (top menu, in the File Manager). The modifications will be properly (i.e., in `defaults.persistent.lua`) stored on exit.

# Advanced

A (very) few settings, not (yet) available in menus, can be manually added to `settings.reader.lua`. They are documented at https://github.com/koreader/koreader/issues/2589#issuecomment-323927682