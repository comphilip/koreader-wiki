KOReader supports dictionary lookup in EPUB and even in scanned PDF/DJVU documents.
All you need to do to select a phrase for the dictionary and Wikipedia is hold on a word, or hold and drag to select multiple words for other functions.

[![Dictionary lookup](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_lookup.png)

To use the dictionary lookup function, you first need to install one or more dictionaries in the [StarDict](https://en.wikipedia.org/wiki/StarDict) format. A list of freely available dictionaries can be found on the [Firedict site](https://tuxor1337.frama.io/firedict/dictionaries.html). ([Firedict](https://tuxor1337.github.io/firedict/) "is a simple offline dictionary software for Firefox OS with support for the StarDict format.")

The dictionaries need to be installed into one of those directories:
  * `/sdcard/koreader/data/dict` directory for Android
  * `/mnt/private/koreader/data/dict` for Cervantes
  * `koreader/data/dict` directory for Kindle
  * `.adds/koreader/data/dict/` directory for Kobo
  * `applications/koreader/data/dict` directory for Pocketbook

Since *v2020.04* you can override the directory where dictionaries are installed. This is useful if your device has more than one app that can deal with stardict dictionaries to avoid duplicities.

You'll need to add the full path to `defaults.persistent.lua`

For example:
`STARDICT_DATA_DIR = "/mnt/onboard/.adds/vlasovsoft/dictionary"`

# 

The StarDict format dictionary files have suffixes `*.idx`, `*.ifo` or `*.ifo.gz`, `*.dict` or `*.dict.dz`.

### HTML encoding within StarDict dictionaries supported

You can use HTML encoded dictionaries, as described [here.](https://github.com/koreader/koreader/pull/3573)

Also, dictionaries can be tweaked with a custom CSS file, as described [here](https://github.com/koreader/koreader/pull/3585) and [here.](https://github.com/koreader/koreader/pull/3573#issuecomment-355848649) You can find sample files showing how to tweak them [here.](https://github.com/koreader/koreader/pull/3585#issuecomment-361203757) And some more discussion can be found [here](https://github.com/koreader/koreader/issues/3606).

MuPDF is used to render the HTML dictionary results. Unfortunately, MuPDF expects its input to be XHTML, that is well-formed, correct XML, balanced, all tags and attributes in lowercase... HTML.
When it is not, KOReader notices MuPDF didn't like the HTML, and falls back to stripping tags, keeping line feeds, like it used to do before, and gives it back to MuPDF. (well, perhaps it's not as good as it was before when we just stripped tags and render with TextBoxWidget...)

We can't easily fix and convert any HTML to XHTML, but one can add a .lua file in the `dict` directory with code to tweak the output before feeding it to MuPDF.

You need to be at ease with Lua, or just hack the [samples](https://github.com/koreader/koreader/pull/3585#issuecomment-361203757) @poire-z created for some french dicts. More details in #3585 (and  #3606, [#3611](https://github.com/koreader/koreader/issues/3611#issuecomment-361557060)).

#### To strip inline CSS
You can strip (or more simply make them not interpreted by MuPDF) the inline css with something like the following in the `<dictfilename>.lua`:
```lua
return function(html)
    -- html = html:gsub(' style=', ' zzztyle=')
    html = html:gsub(' [Ss][Tt][Yy][Ll][Ee]=', ' zzztyle=')
    return html
end
```
#### An example of how to apply this on a dictionary
1) Edit an `.ifo` file in the dictionary folder. There should be a parameter `sametypesequence`. To make css stripping work it should be `sametypesequence=h`.
2) Keep in mind that css stripping is a very powerful tool which can lead to enormous substitutions. To play safe, check out the output of stardict binary to find out what tags are used in the html layout. For example, from SSH or terminal on a device, go too koreader/ directory and call `sdcv -02 data/dict quaint` , where `data/dict` is the dictionary folder and `quaint` in a search query. The output should look like this:
```
[root@kindle koreader]# ./sdcv -02 data/dict/ quaint
Found 2 items, similar to quaint.
-->Longman Dictionary of Contemporary English 5th Ed. (En-En)
-->quaint

<k>quaint</k>
<c c="blue"><b>quaint</b></c> /kweɪnt/ <abr>BrE</abr> <rref>bre_quaint0205.wav</rref> <abr>AmE</abr> <rref>ame_quaint.wav</rref><i><c> adjective</c></i>
<blockquote><blockquote>[<c c="lightcoral">Date: </c><c c="darkgray">1100-1200</c>; <c c="lightcoral">Language: </c><c c="darkgray">Old French</c>; <c c="lightcoral">Origin: </c><c c="darkgray">cointe</c><c c="darkgray"> </c><i><c c="lightseagreen">&apos;clever&apos;</c></i><c c="darkgray">, from </c><c c="darkgray">Latin</c><c c="darkgray"> </c><c c="darkgray">cognitus</c><c c="darkgray"> </c><i><c c="lightseagreen">&apos;known&apos;</c></i>]</blockquote></blockquote>
<blockquote><blockquote> unusual and attractive, especially in an old-fashioned way: </blockquote></blockquote>
<blockquote><blockquote><blockquote><blockquote>  <rref>exa_p008-000464505.wav</rref> <ex>a quaint little village in Yorkshire</ex></blockquote></blockquote></blockquote></blockquote>
```
From the output, several things can be extracted. One - the main tag for paragraphs is `<blockquote>`. Two - the main tag for colored text is `<c c="color">` which is not a classical css-coloring scheme. Moreover, colors themselves are written out as text instead of html-rgb references, so they might be completely ignored by KOReader. Three - there are references to `.wav` sound files which are redundant for KOReader. In dictionary applications that support such references, these are essentially small icons of a speaker action as a button to trigger the sound. However in KOReader's dictionary they will be rendered plainly as in the html source, e.g. `bre_quaint0205.wav`. Four - there is an extra word of the query in the `<k>` tag.

3) After you find out what you would like to replace, create a `.lua` file with exactly the same name of the `.ifo` file before the file extension. Here is an example content of such a file to replace color schemes and definitions with classical ones, replaced `.wav` references with a Unicode icon of speaker (to distinguish sound examples from the word explanation), and removed `<k>` tag word:
```
return function(html)
    html = html:gsub('<rref[^>]*>[^<]*%.wav</rref>', '🔊')
    html = html:gsub('<k[^>]*>[^<]*</k>', '')
    html = html:gsub('<c>', '<span>')
    html = html:gsub('</c>', '</span>')
    html = html:gsub('<c c=\"', '<span style=\"color:')
    html = html:gsub('\"color:indigo\"', '\"color:#4B0082\"')
    html = html:gsub('\"color:darkgray\"', '\"color:#A9A9A9\"')
    html = html:gsub('\"color:lightcoral\"', '\"color:#F08080\"')
    html = html:gsub('\"color:lightseagreen\"', '\"color:#20B2AA\"')
    html = html:gsub('\"color:darkgoldenrod\"', '\"color:#B8860B\"')    
    return html
end
```
4) If you want to tweak the text output with css, create a `.css` file with the same name as `.ifo` and `.lua` files before the file extension. For this particular example, the css file looks like:
```
blockquote{
    margin-left: 1.0rem;
    margin-right: 0.5rem;
    text-align: justify;
}
```
Here is the screenshot of how it was before with `sametypesequence=x` by default, and after making it `sametypesequence=h` and adding `.lua` and `.css`:
![](https://i.imgur.com/0PViowR.png)

### Converting from other sources

Some freely available dictionaries can be converted to the StarDict format with [stardicter](https://blog.cihar.com/archives/2017/01/27/stardicter-011/). See also [wiktionary-to-stardict](https://gitlab.com/artefact2/wiktionary-to-stardict).

You may also be able to use `DICT` files used by the [standard dictd daemon](https://manpages.debian.org/dictd) and the related [dict packages](https://packages.debian.org/search?keywords=dict-) that contain `.dict` files. Those files can be converted to `stardict` format using the `/usr/lib/stardict-tools/dictd2dic` command provided in the `stardict-tools` package, although it seems to fail to create the necessary metadata files like the `.ifo` file.

### Dictionary lookups in scanned pages

KOReader has a built-in OCR engine for recognizing words in scanned PDF/DJVU pages. In order to use OCR in scanned pages, you need to install Tesseract trained data for your document language.

* install [Tesseract language data](https://github.com/tesseract-ocr/tessdoc/blob/a28acb1ca0b89942ed3e4fbd6601b942e9234c54/Data-Files.md#data-files-for-version-304305)
    * copy the language data files for Tesseract 3.04 (e.g. `eng.*` in `tesseract-ocr-3.02.eng.tar.gz` for English and `spa.*` in `tesseract-ocr-3.04.spa.tar.gz` for Spanish) into `koreader/data/tessdata`


### Dictionaries can be downloaded from the internet

You can download dictionaries from the internet as shown [here.](https://github.com/koreader/koreader/wiki/Dictionary-download)

### Sorting how dictionaries are displayed

Dictionaries are shown in the order as they were placed in `data/dict` folder. To sort them, you need to move them out of this directory and then place them again back in order you want them to be displayed.

The safest procedure is:

1. First rename the `dict` folder to some new name (e.g. `dict.old`).
2. Then create a new `dict` directory.
3. Start moving dictionaries back into the new `dict` directory one by one, in the order you want them to appear.

More info can be found [here.](https://github.com/koreader/koreader/issues/4504#issuecomment-457388178)

### Tips and tricks

To look up a word in the dictionary, press and hold on the word. If you press and hold for more than 3s, it will open a menu with more options, as described [here](https://github.com/koreader/koreader/pull/3199).

The dictionary supports a history of searched words, accessible through the menu. More info can be found [here](https://github.com/koreader/koreader/pull/3161) (with images).

You can cancel (too) long, or any, search by tap. More on this [here.](https://github.com/koreader/koreader/pull/3228)