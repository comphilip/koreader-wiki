Koreader supports dictionary lookup in EPUB and even in scanned PDF/DJVU documents.
In order to use dictionary lookup function, you need to install one or more dictionaries of Stardict format first.

[![Dictionary lookup](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)

* install [Stardict dictionary](http://abloz.com/huzheng/stardict-dic/)
    * copy the directory containing the Stardict format dictionary files (`*.idx`, `*.ifo`, `*.dict`) into `koreader/data/dict directory`.

Koreader has a build-in OCR engine for recognizing words in scanned PDF/DJVU pages. In order to use OCR in scanned page, you need to install tesseract trained data for your document language.

* install [Tesseract language data](https://code.google.com/p/tesseract-ocr/downloads/list)
    * copy language data files for Tesseract 3.02 (e.g. `eng.*` in `tesseract-ocr-3.02.eng.tar.gz` for English and `spa.*` in `tesseract-ocr-3.02.spa.tar.gz` for Spanish) into `koreader/data/tessdata`
