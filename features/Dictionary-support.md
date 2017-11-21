KOReader supports dictionary lookup in EPUB and even in scanned PDF/DJVU documents.

In order to use the dictionary lookup function, you first need to install one or more dictionaries in the [StarDict](https://en.wikipedia.org/wiki/StarDict) format. A list of freely available dictionaries can be found on the [Firedict site](https://tuxor1337.github.io/firedict/dictionaries.html). ([Firedict](https://tuxor1337.github.io/firedict/) "is a simple offline dictionary software for Firefox OS with support for the StarDict format.")

[![Dictionary lookup](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)

* install Stardict dictionary - copy the directory containing the StarDict format dictionary files (`*.idx`, `*.ifo` or `*.ifo.gz`, `*.dict` or `*.dict.dz`) into :
  *  `/sdcard/koreader/data/dict` directory for Android
  * `koreader/data/dict` directory for Kindle
  *  `.adds/koreader/data/dict/` directory for Kobo
  *  `applications/koreader/data/dict` directory for Pocketbook

Some freely available dictionaries can be converted to the StarDict format with [stardicter](https://blog.cihar.com/archives/2017/01/27/stardicter-011/). See also [wiktionary-to-stardict](https://gitlab.com/artefact2/wiktionary-to-stardict).

### Reusing DICT files

You can also use `DICT` files used by the [standard dictd daemon](https://manpages.debian.org/dictd) and the related [dict packages](https://packages.debian.org/search?keywords=dict-) that contain `.dict` files. Those files can be converted to `stardict` format 

### Dictionary lookups in scanned pages

KOReader has a build-in OCR engine for recognizing words in scanned PDF/DJVU pages. In order to use OCR in scanned page, you need to install tesseract trained data for your document language.

* install [Tesseract language data](https://sourceforge.net/projects/tesseract-ocr-alt/files/)
    * copy language data files for Tesseract 3.02 (e.g. `eng.*` in `tesseract-ocr-3.02.eng.tar.gz` for English and `spa.*` in `tesseract-ocr-3.02.spa.tar.gz` for Spanish) into `koreader/data/tessdata`