KOReader supports dictionary lookup in EPUB and even in scanned PDF/DJVU documents.
All you need to do to select a phrase for the dictionary and Wikipedia is hold on a word, or hold and drag to select multiple words for other functions.

[![Dictionary lookup](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)

In order to use the dictionary lookup function, you first need to install one or more dictionaries in the [StarDict](https://en.wikipedia.org/wiki/StarDict) format. A list of freely available dictionaries can be found on the [Firedict site](https://tuxor1337.frama.io/firedict/dictionaries.html). ([Firedict](https://tuxor1337.github.io/firedict/) "is a simple offline dictionary software for Firefox OS with support for the StarDict format.")

The dictionaries need to be installed into one of those directories:
  *  `/sdcard/koreader/data/dict` directory for Android
  * `koreader/data/dict` directory for Kindle
  *  `.adds/koreader/data/dict/` directory for Kobo
  *  `applications/koreader/data/dict` directory for Pocketbook

The StarDict format dictionary files have suffixes `*.idx`, `*.ifo` or `*.ifo.gz`, `*.dict` or `*.dict.dz`.

### HTML encoding within StarDict dictionaries supported

You can use HTML encoded dictionaries, as described [here.](https://github.com/koreader/koreader/pull/3573)

Also, dictionaries could be tweaked with custom css file, as described [here](https://github.com/koreader/koreader/pull/3585) and [here.](https://github.com/koreader/koreader/pull/3573#issuecomment-355848649) You can find sample files how to tweak them [here.](https://github.com/koreader/koreader/pull/3585#issuecomment-361203757) And some more discussion can be found [here](https://github.com/koreader/koreader/issues/3606).

We use MuPDF to render the HTML dictionary results. Unfortunately, MuPDF expects its input to be XHTML, that is totally correct XML, balanced, all tags and attributes in lowercase... HTML.
When it is not, KOReader noticed MuPDF didn't like it, and falls back to stripping tags, keeping line feeds, like it used to do before, and give it back to MuPDF (well, may be it is not as good as it was before when we just stripped tags and render with TextBoxWidget...)

We can't easily fix and convert any HTML to XHTML, but one can add a .lua file in the dict directory with code to tweak the output before feeding it to MuPDF.

You need to be at ease with lua, or just hack the [samples](https://github.com/koreader/koreader/pull/3585#issuecomment-361203757) @poire-z created for some french dicts. More details in #3585 (and  #3606, #3611).

### Converting from other sources

Some freely available dictionaries can be converted to the StarDict format with [stardicter](https://blog.cihar.com/archives/2017/01/27/stardicter-011/). See also [wiktionary-to-stardict](https://gitlab.com/artefact2/wiktionary-to-stardict).

You may also be able to use `DICT` files used by the [standard dictd daemon](https://manpages.debian.org/dictd) and the related [dict packages](https://packages.debian.org/search?keywords=dict-) that contain `.dict` files. Those files can be converted to `stardict` format using the `/usr/lib/stardict-tools/dictd2dic` command provided in the `stardict-tools` package, although it seems to fail to create the necessary metadata files like the `.ifo` file.

### Dictionary lookups in scanned pages

KOReader has a build-in OCR engine for recognizing words in scanned PDF/DJVU pages. In order to use OCR in scanned page, you need to install tesseract trained data for your document language.

* install [Tesseract language data](https://sourceforge.net/projects/tesseract-ocr-alt/files/)
    * copy language data files for Tesseract 3.02 (e.g. `eng.*` in `tesseract-ocr-3.02.eng.tar.gz` for English and `spa.*` in `tesseract-ocr-3.02.spa.tar.gz` for Spanish) into `koreader/data/tessdata`


### Dictionaries can be downloaded from the internet

You can download dictionaries from the internet as shown [here.](https://github.com/koreader/koreader/wiki/Dictionary-download)

### Sorting how dictionaries are displayed

Dictionaries are shown in the order as they were placed in `data/dict` folder. To sort them, you need to move them out of this directory and then place them again back in order you want them to be displayed.

Safest procedure is:

1. First rename dict folder to some new name (e.g. dict.old).
2. Then create new dict directory.
3. Start moving back in new dict directory dictionaries one by one in order you want them to appear.

More info can be found [here.](https://github.com/koreader/koreader/issues/4504#issuecomment-457388178)

### Tips and tricks

To open word in dictionary, press and hold. But, press and hold for more than 3s, it opens menu with more options, as described [here](https://github.com/koreader/koreader/pull/3199).

Dictionary supports history of searched words, accessible through menu. More info can be found [here](https://github.com/koreader/koreader/pull/3161) (with images).

You can cancel (too) long, or any, search by tap. More on this [here.](https://github.com/koreader/koreader/pull/3228)