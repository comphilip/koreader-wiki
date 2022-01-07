KOReader 2021.11 and later has improved support for Japanese dictionary lookups and word selection through the Japanese Support plugin.

This plugin requires you to have a Japanese dictionary installed in KOReader's stardict `data/dicts` directory. It doesn't matter whether it is a bilingual (Japanese-to-Another-Language) or monolingual (Japanese-to-Japanese) dictionary. [JMDict](https://www.edrdg.org/wiki/index.php/JMdict-EDICT_Dictionary_Project) is a freely licensed Japanese-to-English dictionary.

This plugin can be configured through the Language support plugins menu (Settings Cog > Document > Language support plugins > Japanese). 

## "Word" Selection ##

In contrast to most languages, in Japanese words are slightly hard to define. However, the most reasonable definition of a word (for the purposes of selecting words to do dictionary lookups) is "the longest set of characters which (after deinflection) appear in the dictionary". And this is how KOReader's word selection works. This means that longer phrases will also be selected as a single word if the longer phrase appears in any of your installed dictionaries.

When you select the first character of a word, the Japanese Support plugin will try a series of deinflections and lookups to find the longest string of characters that are in an installed dictionary. KOReader will then default your hold-selection to that set of characters, and if you release the hold you will (by default) get a dictionary lookup popup for the selected word. You can always adjust the selection by hold and panning.

In order to make lookups efficient enough on lower-powered hardware, there is a configurable lookahead limit which defaults to 20 characters (though it should be noted that due to how crengine counts characters this includes furigana as well as some other things). In addition, we will stop looking ahead once we hit any punctuation or non-CJK characters. You can configure the lookahead limit in the plugin submenu.

Note that some dictionaries (notably JMDict) like to create entries for phrases or multi-word compounds which probably shouldn't be considered "words". This means sometimes we will select a longer word than is appropriate -- in which case you'll need to either disable the offending dictionary or manually correct the selection. Luckily this doesn't happen very often.

Please also note there is a [known bug](https://github.com/koreader/koreader/issues/8619) in KOReader which makes selecting the first character slightly more cumbersome than necessary (you often have to tap and hold slightly to the left of the character you are trying to select). This issue should be fixed in a future KOReader version.

## Deinflection ##

Japanese verbs can be highly inflected in a way that most dictionary lookup programs cannot handle. Most StarDict dictionaries for Japanese instead have workarounds (using the synonym database) to make looking up Japanese words somewhat tolerable with StarDict-powered readers. 

However, the Japanese Support plugin knows how to deinflect verbs and can take text like 食わせられている and figure out that the dictionary form is 食う (食わせられている -> 食わせられる -> 食わせる -> 食う). This works both in conjunction with the word selection quick dictionary lookup (which will correctly select Japanese verbs in full) and manual lookups.

In addition, the deinflector can handle apply conversions (between katakana and hiragana, half-width to full-width kana, and removing emotive markers like 〜, ー, ッ, っ, and so on). The set of enabled conversions can be configured in the plugin submenu.

Please note that unfortunately KOReader doesn't have a built in IME (meaning you cannot input kanji using the keyboard), so if you look up words using the keyboard you'll probably have to scroll through several pages of results to find the word you were looking for. However if you type in an inflected verb, it will be deinflected correctly.

The deinflection code in KOReader is very heavily based on [Yomichan](https://github.com/FooSoft/yomichan) (in fact we use the same [inflection rules table](https://github.com/FooSoft/yomichan/blob/master/ext/data/deinflect.json)). This means if you find that a particular inflection is not being handled properly, this is likely also a bug in Yomichan.