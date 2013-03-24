# User Guide for kindlepdfviewer

## Features

## Settings
Currently, every settings file can be edited with any text editors, from notepad to Emacs/Vim. Setting files use **Lua** syntax, so remember to add a `,` to the end of every entry.

### Reader settings
Reader settings are stored in `settings.reader.lua` under `kindlepdfviewer` folder. kindlepdfviewer supports following setting entries for reader:

* `lastfile`:
The last file you open. If you run kindlepdfviewer in command line without any arguments, it will open this file.

* `fontmap`:
Font settings in various contexts:
  * `cfont`: font for content dispaly
  * `tfont`: font for title dispaly

* `pan_overlap_vertical`:
The overlap you gain when panning vertically. Default is 30.

* `cache_max_memsize`:
The maximum memory usage for caching. The larger you set, the more pages will be cached while reading. Default to 1024*1024*5 (5mb).

* `cache_max_ttl`:
The maximum time to live for each cache entry. The larger you set, the more pages will be cached while reading. Default to 20.

* `partial_refresh_count`:
Counts of partial screen refresh before a full screen refresh. Set it to 0 if you want full screen refresh only.

* `cre_font`:
Default font for document formats supported by CREngine from Cool Reader. You have to create this entry by yourself if not found.

#### example for .reader.kpdfview.lua:
```lua
-- we can read Lua syntax here!
return {
	["cache_max_memsize"] = 5*1024*1024,
	["cache_max_ttl"] = 20,
	["lastfile"] = "/mnt/us/documents/test.djvu",
	["fontmap"] = {
		["infont"] = "droid/DroidSansMono.ttf",
		["scfont"] = "droid/DroidSansMono.ttf",
		["hpkfont"] = "droid/DroidSansMono.ttf",
		["pgfont"] = "droid/DroidSans.ttf",
		["hfont"] = "droid/DroidSans.ttf",
		["ffont"] = "droid/DroidSans.ttf",
		["cfont"] = "droid/DroidSans.ttf",
		["tfont"] = "NimbusSanL-BoldItal.cff",
		["rifont"] = "droid/DroidSans.ttf"
	},
	["partial_refresh_count"] = 5,
	["pan_overlap_vertical"] = 30
}
```

### Book settings
Each opened book will have a setting file called
`name_of_the_book.kpdfview.lua`. You can edit these files to change the
settings.


#### HighLights

Currently kindlepdfviewer supports two styles for highlights. The default style
is **underscore**. This style has two more properties to configure, namely
`line_width` and `line_color`. Or you can switch to **marker** style by changing the `drawer` entry. In fact, when you are selecting text to highlight, kindlepdfviewer is using the **marker** style.

```lua
return {
	-- ...
	-- some other settings
	-- ...
	["highlight"] = {
		[108] = {
			[1] = {
				[1] = {
					["y0"] = 3690,
					["x0"] = 360,
					["y1"] = 3776,
					["x1"] = 850
				},
				["text"] = "the equation in "
			}
		},
		["line_width"] = 2,
		["drawer"] = "underscore",
		["line_color"] = 5
	},
	-- ...
	-- some other settings
	-- ...
}
```
PS: The ranging of `line_color` is 0 to 15, you can view it as the intensity of the line to draw.


## Trouble Shooting