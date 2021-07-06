# Tweak document settings
You can set specific default options for documents in specific directories.
**This will only apply to newly opened documents.**

To do this, open and edit `koreader/settings/directory_defaults.lua` file.

For example, to have specific options for any document in `/mnt/us/books/[manga]/` directory and its sub-directories, add:
```
    ["/mnt/us/books/[manga]"] = {
        ["inverse_reading_order"] = true,
    },
``` 
The setting `["inverse_reading_order"] = true,` swaps tap zones and swipe directions, so the document pages are read right-to-left (implying you had left-to-right by default), which is important for manga books.

## Syntax
Make sure to follow the proper syntax as described in the file. For example, do not put the last `/` in the end of the directory, always close brackets, and so on.

Any other setting from the respective metadata file can be added here. If the book named `Book.epub` is in the `/mnt/us/books/[manga]/` directory, then its metadata file `metadata.epub.lua` is in the `/mnt/us/books/[manga]/Book1.epub.sdr/` directory. 
For example:
`["copt_block_rendering_mode"] = 0,` sets `Bottom menu - documents settings - Render mode` setting to `legacy`.

If you are unsure what setting should have what value, manually set it first in the UI and re-open the metadata file.
If you can't find a setting, most probably it is not supported by this feature. For example, `Alt Status Bar`.

## Duplicate settings
Due to engine and UI code complications, some of the settings must have two defining settings in the `directory_defaults.lua` to properly work.
For example, these two settings for `Bottom Menu - Gear - Embedded Style` and `Embedded Fonts` must always come in pairs:
```
        ["embedded_css"] = true, -- for actual applying of the setting 
        ["copt_embedded_css"] = 1, -- for bottom widget only

        ["embedded_fonts"] = true, -- for actual applying of the setting         
        ["copt_embedded_fonts"] = 1, -- for bottom widget only
```
The first one is to actually apply the setting, the second one (beginning with `copt_`) is to show the UI selection.

Remember this when you notice that some settings do not apply.
