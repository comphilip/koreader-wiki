There are two configuration files that will configure initial settings for Koreader behaviors and appearences.
* 1. The `defaults.lua` located at `koreader/defaults.lua`.
* 2. The `cr3.ini` located at `koreader/data/cr3.ini`, especially for EPUB/FB2 documents.

### Basic configuration
| Settings(default) | Location | Change range | Description | Affected document types |
| ------ | ------ | ------ | ------ | ------ |
| `DRCOUNTMAX = 6` | `defaults.lua` | `1`-`99` | full refresh interval for eink devices | ALL |
| `DFULL_SCREEN = 1` | `defaults.lua` | `1` or `0` | hiding progress bar | PDF/DJVU |
| `DSCROLL_MODE = 0` | `defaults.lua` | `1` or `0` | displaying pages continuously | PDF/DJVU |
| `DSHOWOVERLAP = false` | `defaults.lua` | `false` or `true` | showing gray area to indicate page overlap | PDF/DJVU |
| `DCREREADER_VIEW_MODE = "page"` | `defaults.lua` | `page` or `scroll` | pagination in "page" mode | EPUB/FB2 |
| `DSHOWHIDDENFILES = false` | `defaults.lua` | `false` or `true` | showing hidden files in file manager | - |
| `DSHOWFILESIZE = false` | `defaults.lua` | `false` or `true` | showing file size in file manager | - |
