There are two configuration files that will configure initial settings for Koreader behaviors and appearences.
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
| `DSHOWFILESIZE = false` | `defaults.lua` | `false` or `true` | showing file size in MB | FileManager |