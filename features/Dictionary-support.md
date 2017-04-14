KOReader supports dictionary lookup in EPUB and even in scanned PDF/DJVU documents.
In order to use the dictionary lookup function, you first need to install one or more dictionaries in the StarDict format.

[![Dictionary lookup](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)

* install Stardict dictionary - copy the directory containing the StarDict format dictionary files (`*.idx`, `*.ifo`, `*.dict`) into :
    * `koreader/data/dict` directory for Kindle,
 *  `/sdcard/koreader/data/dict` directory for Android,
 *  `applications/koreader/data/dict` directory for Pocketbook.
 *  `.adds/koreader/data/dict/` directory for Kobo.

* some freely available dictionaries can be converted to the StarDict format with [stardicter](https://blog.cihar.com/archives/2016/10/11/stardicter-010/).

KOReader has a build-in OCR engine for recognizing words in scanned PDF/DJVU pages. In order to use OCR in scanned page, you need to install tesseract trained data for your document language.

* install [Tesseract language data](https://sourceforge.net/projects/tesseract-ocr-alt/files/)
    * copy language data files for Tesseract 3.02 (e.g. `eng.*` in `tesseract-ocr-3.02.eng.tar.gz` for English and `spa.*` in `tesseract-ocr-3.02.spa.tar.gz` for Spanish) into `koreader/data/tessdata`