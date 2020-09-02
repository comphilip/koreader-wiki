## Installation
You need to obtain a recent PocketBook package from [the releases page](https://github.com/koreader/koreader/releases). Then unzip the archive on your computer. There will be two directories in the unzipped directory, namely `applications` and `system`.

1. Install KOReader in the applications menu
    1. copy and merge the `applications` directory in the unzipped archive into your PocketBook's USB root directory
1. Associate file extensions so that koreader opens given file formats from main explorer
    1. Run koreader app
    2. Tap the "gear" settings menu
    3. Device->Associcate file extensions->Enable all
    4. If the menu is missing, you need to remove `system/config/extensions.cfg` as koreader refuses to overwrite your custom definitions.
1. Install Stardict dictionaries (optional)
    1. Copy Stardict format dictionary files (*.idx, *.ifo, *.dict) into the `applications/koreader/data/dict` directory.
1. Install Tesseract language data (optional)
    1. Copy Tesseract-OCR language data files (eng.*) for Tesseract 3.04 into the `applications/koreader/data/tessdata` directory. See [here](https://github.com/koreader/koreader/wiki/Dictionary-support#dictionary-lookups-in-scanned-pages) for more information.

